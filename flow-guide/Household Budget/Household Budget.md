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

Where the month's money went, against the plan in [[Budget Profile]]. Drop a
bank statement in `statements/` and the page redraws — the moment Flow
notices it, or overnight if Flow was closed: the totals, the categories
against their budgets, the merchants that add up, and the lines no rule has
caught yet. The Night Shift keeps the inventory of statements current, redraws
from the newest summary, and shows you the exact diff when the profile
changes.

Everything stays on this Mac. No statement is sent anywhere; the refresh reads
the CSV files beside this page and writes a summary next to them.

## The month at a glance

```chart data: data/spending-*.json#summary
chartType: KPI Card
title: This month against the plan
subtitle: Dollars, except the savings rate
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

Every budgeted category, with what the month has spent against its limit. A
category past its line is the one to look at first.

```chart data: data/spending-*.json#byCategory
chartType: Bullet Chart
title: Spent against budget, by category
subtitle: This month, $
source: data/spending-*.json, newest capture
data:
  - {category: "Housing", spent: 2950, budget: 2950}
  - {category: "Groceries", spent: 446, budget: 900}
  - {category: "Dining", spent: 198, budget: 450}
  - {category: "Transport", spent: 196, budget: 420}
  - {category: "Utilities", spent: 334, budget: 320}
  - {category: "Health", spent: 294, budget: 350}
  - {category: "Subscriptions", spent: 40, budget: 120}
  - {category: "Shopping", spent: 336, budget: 400}
  - {category: "Kids", spent: 1350, budget: 1400}
  - {category: "Travel", spent: 0, budget: 300}
  - {category: "Giving", spent: 100, budget: 200}
  - {category: "Uncategorized", spent: 409, budget: 0}
semantic_types: {category: Category, spent: Amount, budget: Amount}
encodings:
  y: {field: category}
  x: {field: spent}
  goal: {field: budget}
```

## The last months, stacked

```chart data: data/spending-*.json#byMonth
chartType: Stacked Bar Chart
title: Spending by month and category
subtitle: Up to six months, $
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
  color: {field: category}
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

Each of these needs a `rules` line in [[Budget Profile]]. Add it, run the
refresh, and the line moves into its category.

<!-- data: data/spending-*.json#uncategorized -->
| Date | Description | Amount |
| --- | --- | ---: |
| 2026-08-16 | VENMO PAYMENT 1023 | -85 |
| 2026-08-24 | SQ *CORNER BAKERY | -23.75 |
| 2026-08-27 | ZELLE TO J. ALVAREZ | -300 |

## The plan

Read from the front matter of [[Budget Profile]] each night: change a limit
there and this table is current in the morning, with no refresh at all.

<!-- data: Budget Profile.md#budgets -->
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

The Night Shift keeps this inventory current, so a statement you dropped in
the evening is named in the morning.

```flow-folder statements
| File | Size | Modified | Digest |
| --- | ---: | --- | --- |
| 2026-07 Checking — Example.csv | 1594 | 2026-09-03T04:39:33Z | afa99801b7dd |
| 2026-08 Checking — Example.csv | 1561 | 2026-09-03T04:39:33Z | 60b9e2f2e0ab |
```

## What you will see in the morning

- **A statement landed.** The inventory grew by one file and the Briefing
  names it. If Flow was open when it landed, every chart above had already
  redrawn and the Briefing says so; if not, the night redrew them.
- **The plan changed.** You raised the groceries budget; the Briefing shows
  the diff of the profile and *The plan* table carries the new number.
- **Nothing moved.** An honest empty morning, and the run is in Receipts.

## Make it yours

1. Edit the front matter of [[Budget Profile]]: your income, your targets,
   your categories and rules.
2. Export a month from your bank as CSV into `statements/` and delete the two
   example files.
3. Use Run now (the moon in the title bar). Flow reads [[Budget Refresh]],
   the gather definition for this folder: it takes every statement in
   `statements/`, sorts the lines with the profile's rules and writes the
   month's summary into `data/`, then redraws the page. Nothing runs, so
   there is nothing to allow. Every night after that it reads the same
   definition, so a statement you dropped in is in the morning's page.
4. Turn the Night Shift on: the moon in the title bar, or Settings ▸ Night
   Shift.

## How this page is built

| Block | Construct | Bound to | Redrawn by |
| --- | --- | --- | --- |
| At a glance | KPI Card | `data/spending-*.json#summary` | refresh, then the night |
| Categories | Bullet Chart | `#byCategory` | refresh, then the night |
| Last months | Stacked Bar Chart | `#byMonth` | refresh, then the night |
| Accumulated | Sparkline | `#cumulative` | refresh, then the night |
| Where it went | table | `#topMerchants` | refresh, then the night |
| Uncaught lines | table | `#uncategorized` | refresh, then the night |
| The plan | table | `Budget Profile.md#budgets` | the night alone |
| Statements | `flow-folder` inventory | `statements/` | the night alone |

## Overnight notes
<!-- night: notes -->
<!-- /night: notes -->
