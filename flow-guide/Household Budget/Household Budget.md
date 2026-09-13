---
title: Household Budget
tags: [budget, dashboard, personal, night-shift]
jobs:
  - kind: gather
    definition: Budget Refresh.md
    as: spending
  - kind: keep-sources-fresh
    watch: [Budget Profile.md, statements]
  - kind: reconcile-against-folder
    folder: statements
  - kind: overnight-notes
---
# Household Budget

**Close the month by resolving unexplained spending, then decide whether next month's plan needs changing.**

> Illustrative household · August 2026 review · USD · two fictional statements, 79 rows. The saved output is dated; it is not a connection to your bank.

In the supplied snapshot, the sample is below its $7,810 spending plan, but $408.75 in three uncategorized transactions still needs explanation. The recorded cash-flow surplus is 32.1% of income; only $1,500 is identified as a transfer to savings. Those are different facts.

**Next action:** identify the Venmo and Zelle recipients before assigning a category. A merchant rule is your classification, not proof of what a transaction purchased. Review refunds, transfers and duplicate/overlapping statements before interpreting the totals. No automatic reconciliation is claimed.

[[Budget Profile]] owns the plan and matching rules; the two local CSVs own the transactions. [[Budget Refresh]] computes the amounts when its Gather job runs. Bound views redraw from the resulting capture. Optional Overnight notes use the configured local model to describe the available tables; they do not validate your bank records.

## The month at a glance

```chart data: data/spending-*.json#summary
chartType: KPI Card
title: This month against the plan
subtitle: USD; savings rate is recorded cash-flow surplus / income
source: data/spending-*.json, newest capture
data:
  - {metric: "Spent in August 2026", value: 6652, goal: 7810}
  - {metric: "Income received", value: 9800, goal: 9800}
  - {metric: "Savings rate, %", value: 32.1, goal: 20}
  - {metric: "Moved to savings", value: 1500, goal: 1960}
semantic_types: {metric: Category, value: Quantity, goal: Quantity}
encodings:
  metric: {field: metric}
  value: {field: value}
  goal: {field: goal}
```

## Categories against their budgets

Two bars compare recorded spending with each category's monthly budget. Colors distinguish the two series. Spending above budget calls for review; Uncategorized has no assigned budget.

```chart data: data/spending-*.json#categoryComparison
chartType: Grouped Bar Chart
title: Spending and budget by category
subtitle: Latest statement month, USD
source: data/spending-*.json, newest capture
data:
  - {category: "Housing", series: "Spent", amount: 2950}
  - {category: "Housing", series: "Budget", amount: 2950}
  - {category: "Groceries", series: "Spent", amount: 446}
  - {category: "Groceries", series: "Budget", amount: 900}
  - {category: "Dining", series: "Spent", amount: 198}
  - {category: "Dining", series: "Budget", amount: 450}
  - {category: "Transport", series: "Spent", amount: 196}
  - {category: "Transport", series: "Budget", amount: 420}
  - {category: "Utilities", series: "Spent", amount: 334}
  - {category: "Utilities", series: "Budget", amount: 320}
  - {category: "Health", series: "Spent", amount: 294}
  - {category: "Health", series: "Budget", amount: 350}
  - {category: "Subscriptions", series: "Spent", amount: 40}
  - {category: "Subscriptions", series: "Budget", amount: 120}
  - {category: "Shopping", series: "Spent", amount: 336}
  - {category: "Shopping", series: "Budget", amount: 400}
  - {category: "Kids", series: "Spent", amount: 1350}
  - {category: "Kids", series: "Budget", amount: 1400}
  - {category: "Travel", series: "Spent", amount: 0}
  - {category: "Travel", series: "Budget", amount: 300}
  - {category: "Giving", series: "Spent", amount: 100}
  - {category: "Giving", series: "Budget", amount: 200}
  - {category: "Uncategorized", series: "Spent", amount: 409}
  - {category: "Uncategorized", series: "Budget", amount: 0}
semantic_types: {category: Category, series: Category, amount: Amount}
encodings:
  y: {field: category}
  x: {field: amount}
  group: {field: series, scheme: tableau10}
```

## The last months, stacked

```chart data: data/spending-*.json#byMonth
chartType: Stacked Bar Chart
title: Spending by month and category
subtitle: All supplied months, USD
source: data/spending-*.json, newest capture
data:
  - {month: "2026-07", category: "Dining", spent: 201}
  - {month: "2026-07", category: "Giving", spent: 100}
  - {month: "2026-07", category: "Groceries", spent: 707}
  - {month: "2026-07", category: "Health", spent: 294}
  - {month: "2026-07", category: "Housing", spent: 2950}
  - {month: "2026-07", category: "Kids", spent: 1350}
  - {month: "2026-07", category: "Shopping", spent: 415}
  - {month: "2026-07", category: "Subscriptions", spent: 40}
  - {month: "2026-07", category: "Transport", spent: 122}
  - {month: "2026-07", category: "Travel", spent: 1098}
  - {month: "2026-07", category: "Uncategorized", spent: 109}
  - {month: "2026-07", category: "Utilities", spent: 380}
  - {month: "2026-08", category: "Dining", spent: 198}
  - {month: "2026-08", category: "Giving", spent: 100}
  - {month: "2026-08", category: "Groceries", spent: 446}
  - {month: "2026-08", category: "Health", spent: 294}
  - {month: "2026-08", category: "Housing", spent: 2950}
  - {month: "2026-08", category: "Kids", spent: 1350}
  - {month: "2026-08", category: "Shopping", spent: 336}
  - {month: "2026-08", category: "Subscriptions", spent: 40}
  - {month: "2026-08", category: "Transport", spent: 196}
  - {month: "2026-08", category: "Uncategorized", spent: 409}
  - {month: "2026-08", category: "Utilities", spent: 334}
semantic_types: {month: Category, category: Category, spent: Amount}
encodings:
  x: {field: month}
  y: {field: spent}
  color: {field: category, scheme: oranges}
```

## How the month accumulated

```chart data: data/spending-*.json#cumulative
chartType: Sparkline
title: Cumulative spend through the month
source: data/spending-*.json, newest capture
data:
  - {day: "2026-08-01", spent: 2950}
  - {day: "2026-08-02", spent: 3047}
  - {day: "2026-08-03", spent: 4397}
  - {day: "2026-08-04", spent: 4607}
  - {day: "2026-08-05", spent: 4807}
  - {day: "2026-08-06", spent: 4930}
  - {day: "2026-08-07", spent: 4985}
  - {day: "2026-08-08", spent: 5075}
  - {day: "2026-08-09", spent: 5098}
  - {day: "2026-08-10", spent: 5171}
  - {day: "2026-08-11", spent: 5282}
  - {day: "2026-08-12", spent: 5428}
  - {day: "2026-08-14", spent: 5437}
  - {day: "2026-08-15", spent: 5437}
  - {day: "2026-08-16", spent: 5703}
  - {day: "2026-08-18", spent: 5904}
  - {day: "2026-08-19", spent: 5931}
  - {day: "2026-08-20", spent: 6131}
  - {day: "2026-08-21", spent: 6141}
  - {day: "2026-08-22", spent: 6229}
  - {day: "2026-08-23", spent: 6277}
  - {day: "2026-08-24", spent: 6328}
  - {day: "2026-08-27", spent: 6628}
  - {day: "2026-08-28", spent: 6652}
semantic_types: {day: Date, spent: Amount}
encodings:
  x: {field: day}
  y: {field: spent}
```

## Where it went

The twelve merchants that took the most this month.

<!-- data: data/spending-*.json#topMerchants -->
| Merchant | Category | Count | Spent |
| --- | --- | ---: | ---: |
| RENT PAYMENT PARKSIDE APARTMENTS | Housing | 1 | 2950 |
| LITTLE OAKS DAYCARE | Kids | 1 | 1350 |
| ZELLE TO J. ALVAREZ | Uncategorized | 1 | 300 |
| KAISER PERMANENTE PREMIUM | Health | 1 | 210 |
| COSTCO WHSE | Groceries | 3 | 209 |
| WHOLE FOODS MARKET | Groceries | 1 | 160 |
| TARGET | Shopping | 2 | 148 |
| PG&E ELECTRIC AND GAS | Utilities | 1 | 132 |
| VERIZON WIRELESS PAYMENT | Utilities | 1 | 112 |
| AMAZON MKTPLACE PMTS | Shopping | 1 | 100 |
| AMERICAN RED CROSS DONATION | Giving | 1 | 100 |
| COMCAST CABLE COMM | Utilities | 1 | 90 |

## Lines no rule caught

Identify these transactions first. Then add the appropriate rule in [[Budget Profile]] and run the refresh. Transfers and refunds require review before classifying them as spending.

<!-- data: data/spending-*.json#uncategorized -->
| Date | Description | Amount |
| --- | --- | ---: |
| 2026-08-16 | VENMO PAYMENT 1023 | -85 |
| 2026-08-24 | SQ *CORNER BAKERY | -23.75 |
| 2026-08-27 | ZELLE TO J. ALVAREZ | -300 |

## The plan

This view reads the **Budgets** table in [[Budget Profile]]. Edit and save the input table; the next completed refresh updates this view.

<!-- data: Budget Profile.md#table:Budgets -->
| Category | Monthly |
| --- | ---: |
| Housing | 2950 |
| Groceries | 900 |
| Dining | 450 |
| Transport | 420 |
| Utilities | 320 |
| Health | 350 |
| Subscriptions | 120 |
| Shopping | 400 |
| Kids | 1400 |
| Travel | 300 |
| Giving | 200 |

## Statements in this folder

The Night Shift keeps this inventory current, when its inventory job runs.

```flow-folder statements
| File | Size | Modified | Digest |
| --- | ---: | --- | --- |
| 2026-07 Checking — Example.csv | 1594 |  |  |
| 2026-08 Checking — Example.csv | 1561 |  |  |
```

Bundled file list; the inventory job fills timestamps and digests in your working copy.

## What changes on a run

The opening assessment remains authored text; review its amounts after changing inputs.

Gather reads the supplied statements, writes a new spending capture and refreshes the bound views. The inventory and source-watch jobs record changes to the files you named. Unchanged inputs may produce no new document change. Review the run result and dated capture before calling a page current; saving a CSV is not evidence that a refresh has completed.

## Make it yours

1. Copy the entire **Household Budget** folder to your own location and add that folder in Flow. Keep its profile, definition, statements and data together.
2. Open [[Budget Profile]] and choose **View ▸ Edit Table**. In **Budgets**, change the Groceries monthly limit from 900 to 950, then save. Open [[Budget Refresh]] in the Definition editor only if you want to inspect the calculation. After a run, the category target should be 950 and total budget 7,860; actual spending should be unchanged.
3. Replace both fictional CSVs with non-overlapping exports using exactly `Date,Description,Amount`, ISO dates and signed amounts. Map debit/credit exports first. Confirm account/period coverage yourself.
4. Choose **File ▸ Night Shift Jobs…** on this document to review its saved jobs, then use **Settings ▸ Night Shift ▸ Run now**. Scheduling can stay off for a manual run. These Gather inputs are local. Inspect the capture and run result; subsequent scheduled work depends on Night Shift being enabled and available.
5. Set your expected income, targets and rules. When there is no positive recorded income, the savings rate is unavailable. Positive refunds are outside this simple outflow calculation; reconcile them before treating it as a complete expense ledger.

## How this page is built

| Block | Construct | Bound to | Redrawn by |
| --- | --- | --- | --- |
| At a glance | KPI Card | `data/spending-*.json#summary` | refresh, then the night |
| Categories | Grouped Bar Chart | `#categoryComparison` | refresh, then the night |
| Last months | Stacked Bar Chart | `#byMonth` | refresh, then the night |
| Accumulated | Sparkline | `#cumulative` | refresh, then the night |
| Where it went | table | `#topMerchants` | refresh, then the night |
| Uncaught lines | table | `#uncategorized` | refresh, then the night |
| The plan | table | `Budget Profile.md#table:Budgets` | the night alone |
| Statements | `flow-folder` inventory | `statements/` | the night alone |

## Overnight notes
<!-- night: notes -->
<!-- /night: notes -->
