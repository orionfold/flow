---
title: Budget Profile
tags: [budget, parameters, night-shift]
currency: USD
income_monthly: 9800
savings_target_pct: 20
budgets:
  - {category: Housing, monthly: 2950}
  - {category: Groceries, monthly: 900}
  - {category: Dining, monthly: 450}
  - {category: Transport, monthly: 420}
  - {category: Utilities, monthly: 320}
  - {category: Health, monthly: 350}
  - {category: Subscriptions, monthly: 120}
  - {category: Shopping, monthly: 400}
  - {category: Kids, monthly: 1400}
  - {category: Travel, monthly: 300}
  - {category: Giving, monthly: 200}
rules:
  - {match: "PAYROLL", category: Income}
  - {match: "TRANSFER TO SAVINGS", category: Savings}
  - {match: "RENT", category: Housing}
  - {match: "WHOLE FOODS", category: Groceries}
  - {match: "TRADER JOE", category: Groceries}
  - {match: "SAFEWAY", category: Groceries}
  - {match: "COSTCO", category: Groceries}
  - {match: "CHIPOTLE", category: Dining}
  - {match: "STARBUCKS", category: Dining}
  - {match: "BLUE BOTTLE", category: Dining}
  - {match: "SWEETGREEN", category: Dining}
  - {match: "DOORDASH", category: Dining}
  - {match: "CHEVRON", category: Transport}
  - {match: "SHELL OIL", category: Transport}
  - {match: "UBER", category: Transport}
  - {match: "CLIPPER", category: Transport}
  - {match: "PG&E", category: Utilities}
  - {match: "COMCAST", category: Utilities}
  - {match: "VERIZON", category: Utilities}
  - {match: "KAISER", category: Health}
  - {match: "CVS", category: Health}
  - {match: "24 HOUR FITNESS", category: Health}
  - {match: "NETFLIX", category: Subscriptions}
  - {match: "SPOTIFY", category: Subscriptions}
  - {match: "APPLE.COM/BILL", category: Subscriptions}
  - {match: "AMAZON", category: Shopping}
  - {match: "TARGET", category: Shopping}
  - {match: "LITTLE OAKS", category: Kids}
  - {match: "UNITED AIRLINES", category: Travel}
  - {match: "AIRBNB", category: Travel}
  - {match: "RED CROSS", category: Giving}
---
# Budget Profile

The one file you edit. The front matter is the household's plan: the income you expect each month, the savings rate you are aiming for, a budget per category, and the rules that sort a bank statement's lines into those categories. [[Household Budget]] reads the budgets from here each night, and the refresh script uses the rules to categorize whatever statements you drop in `statements/`.

## What each field means

| Field | What it is | Example |
| --- | --- | --- |
| `income_monthly` | What lands in the account in a normal month, after tax. The savings rate is measured against it. | `9800` |
| `savings_target_pct` | The share of income you mean to keep. | `20` |
| `budgets` | One line per category with its monthly limit. A category with no line is charted with no limit. | `{category: Groceries, monthly: 900}` |
| `rules` | One line per merchant pattern. `match` is compared to the statement's description, case-insensitive; the first rule that matches wins. `Income` and `Savings` are the two names the refresh treats specially. | `{match: "WHOLE FOODS", category: Groceries}` |

## Make it yours

- **Add a category.** Add a `budgets` line; it is in the morning's table with no refresh at all.
- **Teach it a merchant.** The dashboard's *Uncategorized* table lists every line no rule caught. Add a `rules` line for each and run the refresh.
- **Use your own statements.** Export a month from your bank as CSV, with a date, a description and an amount column, and put it in `statements/`. Debit and credit columns are read too. The two example statements are made up; delete them when yours are in.

Nothing in this folder is sent anywhere. The refresh reads the statements on this Mac and writes a summary beside them.
