---
title: Budget Refresh
tags: [budget, definition, night-shift]
sources:
  profile: Budget Profile.md
  budgets: Budget Profile.md#budgets
  rules: Budget Profile.md#rules
  statements: statements/*.csv
derive:
  lines:
    from: statements
    steps:
      - {calculate: "Date", as: date}
      - {calculate: "Description", as: description}
      - {calculate: "number(Amount)", as: amount}
      - {rules: description, as: category, using: rules, otherwise: Uncategorized}
      - {timeunit: date, unit: month, as: month}
  spending:
    from: lines
    steps:
      - {filter: "amount < 0 && category != 'Savings'"}
      - {calculate: "-amount", as: spent}
  thisMonth:
    from: spending
    steps:
      - {filter: "month == latest"}
  spentByDate:
    from: thisMonth
    steps:
      - {aggregate: date, sum: spent, as: spent}
  monthDays:
    from: lines
    steps:
      - {filter: "month == latest"}
      - {aggregate: date, count: date, as: dayLines}
  spentByCategory:
    from: thisMonth
    steps:
      - {aggregate: category, sum: spent, as: spent}
  observedCategories:
    from: spentByCategory
    steps:
      - {filter: "category != 'Income' && category != 'Savings'"}
      - {calculate: "0", as: budget}
  income:
    from: lines
    steps:
      - {filter: "month == latest && category == 'Income'"}
  savings:
    from: lines
    steps:
      - {filter: "month == latest && category == 'Savings' && amount < 0"}
      - {calculate: "-amount", as: moved}
let:
  latest: {max: month, of: lines}
  statementCount: {distinct: source, of: statements}
  lineCount: {count: lines, of: lines}
  spentThisMonth: {sum: spent, of: thisMonth}
  incomeReceived: {sum: amount, of: income}
  saved: {sum: moved, of: savings}
  totalBudget: {sum: monthly, of: budgets}
  incomeExpected: {max: value, of: profile, where: "key == 'income_monthly'"}
  savingsTarget: {max: value, of: profile, where: "key == 'savings_target_pct'"}
  savingsRate: "incomeReceived > 0 ? round((incomeReceived - spentThisMonth) / incomeReceived * 100, 1) : 0"
emit:
  month: "{latest}"
  statements: "{statementCount}"
  lines: "{lineCount}"
  summary:
    - {metric: "{'Spent in ' + monthName(latest)}", value: "{round(spentThisMonth, 0)}", goal: "{round(totalBudget, 0)}"}
    - {metric: Income received, value: "{round(incomeReceived, 0)}", goal: "{round(incomeExpected, 0)}"}
    - {metric: "Savings rate, %", value: "{savingsRate}", goal: "{savingsTarget}"}
    - {metric: Moved to savings, value: "{round(saved, 0)}", goal: "{round(incomeExpected * savingsTarget / 100, 0)}"}
  byCategory:
    from: budgets
    steps:
      - {calculate: "monthly", as: budget}
      - {concat: observedCategories, unlessPresent: category}
      - {lookup: category, from: spentByCategory, on: category, fields: [spent]}
      - {calculate: "round(coalesce(spent, 0), 0)", as: spent}
  byMonth:
    from: spending
    steps:
      - {filter: "category != 'Income' && category != 'Savings'"}
      - {aggregate: [month, category], sum: spent, as: spent}
      - {calculate: "round(spent, 0)", as: spent}
      - {filter: "spent > 0"}
      - {sort: month}
  cumulative:
    from: monthDays
    steps:
      - {lookup: date, from: spentByDate, on: date, fields: [spent]}
      - {calculate: "coalesce(spent, 0)", as: spent}
      - {sort: date}
      - {window: "", sum: spent, as: running}
      - {calculate: "date", as: day}
      - {calculate: "round(running, 0)", as: spent}
  topMerchants:
    from: thisMonth
    steps:
      - {trimTrailing: description, as: Merchant, drop: [digits, statecode]}
      - {aggregate: Merchant, sum: spent, as: Spent}
      - {calculate: "round(Spent, 0)", as: Spent}
      - {sort: Spent, descending: true}
      - {sample: 12}
  uncategorized:
    from: thisMonth
    steps:
      - {filter: "category == 'Uncategorized'"}
      - {calculate: "date", as: Date}
      - {calculate: "description", as: Description}
      - {calculate: "round(-spent, 2)", as: Amount}
---
# How this budget refreshes itself

This is the definition [[Household Budget]] runs each night. It is **data, not code** — every line is something you can read and change, and Flow runs it itself rather than running a program. It can read the files in this folder and nothing else, and it can only work things out and write the capture.

## The four blocks

| Block | What it is for |
| --- | --- |
| `sources:` | What to read: this folder's statements, and the settings in [[Budget Profile]] |
| `derive:` | Row sets worked out once and used by several tables below |
| `let:` | Single values — a total, a count, the latest month |
| `emit:` | The tables and values the capture holds, one per block in the document |

## `derive:` — the work done once

`lines` is every statement line with two columns added: the `category` its description matches, and the `month` its date falls in. Everything else is built from that, so the categorisation happens once rather than in each table.

`rules` reads the list you keep in [[Budget Profile]]. It is tried in order and the **first match wins**, so a more specific line goes above a more general one. The match ignores capitals and looks anywhere in the description.

## `let:` — the single values

`latest` is the newest month any statement mentions, which is what every table below is filtered to. `savingsRate` shows the shape of a calculation: the `? :` guards against dividing by zero, so a month with no income shows 0 rather than nothing.

## Two things worth knowing

**Month names are English.** `monthName(latest)` turns `2026-08` into `August 2026` from a fixed list, not from your Mac's language settings — so the same statements produce the same capture on any machine, which is what lets Flow tell a real change from a re-run.

**Merchant names are trimmed, not pattern-matched.** `trimTrailing` drops a trailing store number and a trailing two-letter state code, so `STARBUCKS #1123 SF` and `STARBUCKS #4471 CA` count as one merchant. Those two things are all it removes: there is no pattern language here, because a pattern is code you would have to read as a program instead of as a sentence.

## Making it yours

Edit [[Budget Profile]] rather than this file for anything ordinary — your categories, your budgets, your matching rules. Come back here to add a table, change what a summary row measures, or read from somewhere else.
