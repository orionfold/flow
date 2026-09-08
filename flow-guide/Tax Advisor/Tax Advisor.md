---
title: Tax Advisor
tags: [tax, dashboard, personal, night-shift]
jobs:
  - kind: gather
    definition: Tax Refresh.md
    into: data
    as: estimate
  - kind: keep-sources-fresh
    watch: [Tax Profile.md, inputs, data/tax-figures.json, https://www.irs.gov/newsroom, https://www.irs.gov/filing/individuals/when-to-file, https://www.irs.gov/newsroom/irs-releases-tax-inflation-adjustments-for-tax-year-2026-including-amendments-from-the-one-big-beautiful-bill, https://www.irs.gov/newsroom/working-families-tax-cuts-tax-deductions-for-working-americans-and-seniors, https://www.irs.gov/credits-deductions/individuals/child-tax-credit]
  - kind: reconcile-against-folder
    folder: inputs
  - kind: overnight-notes
---
# Tax Advisor

Your federal year on one page: what the return will roughly look like, what is still to do, the figures the estimate rests on, and the IRS pages that change them. It reads [[Tax Profile]] and the W-2 forms in `inputs/`, and the Night Shift watches the IRS pages listed above, so a new figure or a moved deadline reaches you the morning after it is published, as the exact text that changed.

An estimate, not advice. The refresh applies the figures the IRS has published for the year, with the simplifications listed at the end. The return itself is your preparer's or your software's.

## The return, roughly

```chart data: data/estimate-*.json#summary
chartType: KPI Card
title: The estimate at a glance
subtitle: Dollars; the effective rate against the marginal one
source: data/estimate-*.json, newest capture
data:
  - {metric: "Estimated refund", value: 12774}
  - {metric: "Taxable income", value: 107900, goal: 147500}
  - {metric: "Effective rate, %", value: 6.2, goal: 22}
  - {metric: "Federal tax after credits", value: 9166, goal: 21940}
semantic_types: {metric: Category, value: Quantity, goal: Quantity}
encodings:
  metric: {field: metric}
  value: {field: value}
  goal: {field: goal}
```

## From wages to taxable income

```chart data: data/estimate-*.json#bridge
chartType: Waterfall Chart
title: How income becomes taxable income
subtitle: Whole dollars
source: data/estimate-*.json, newest capture
data:
  - {step: "W-2 wages", change: 148600}
  - {step: "Other income", change: 7450}
  - {step: "Adjustments", change: -8550}
  - {step: "Itemized deduction", change: -39600}
  - {step: "Taxable income", change: 107900}
semantic_types: {step: Category, change: Amount}
encodings:
  x: {field: step}
  y: {field: change}
```

## Tax by bracket

Only the brackets the income reaches. The last row is the marginal rate.

```chart data: data/estimate-*.json#taxByBracket
chartType: Bar Chart
title: Tax owed in each bracket
subtitle: Income taxed at each rate, and the tax it produces, $
source: data/estimate-*.json, newest capture
data:
  - {bracket: "10%", income: 23850, tax: 2385}
  - {bracket: "12%", income: 73100, tax: 8772}
  - {bracket: "22%", income: 10950, tax: 2409}
semantic_types: {bracket: Category, income: Amount, tax: Amount}
encodings:
  x: {field: bracket}
  y: {field: tax}
```

## Withheld against owed

The bar is what has been withheld and paid; the marker is the estimated tax after credits. Past the marker is a refund; short of it, a balance due.

```chart data: data/estimate-*.json#withholding
chartType: Bullet Chart
title: Payments against the estimated liability
subtitle: Federal, $
source: data/estimate-*.json, newest capture
data:
  - {metric: "Federal withheld and paid", actual: 21940, goal: 9166}
semantic_types: {metric: Category, actual: Amount, goal: Amount}
encodings:
  y: {field: metric}
  x: {field: actual}
  goal: {field: goal}
```

## Standard or itemized

<!-- data: data/estimate-*.json#deductionChoice -->
| Route | Amount | Chosen |
| --- | ---: | --- |
| Standard deduction | 31500 |  |
| Itemized: mortgage interest | 14200 |  |
| Itemized: state and local taxes, capped at 40000 | 21800 |  |
| Itemized: charitable | 3600 |  |
| Itemized: medical above 7.5% of AGI | 0 |  |
| Itemized total | 39600 | yes |

## Room left in the tax-advantaged accounts

<!-- data: data/estimate-*.json#headroom -->
| Account | Contributed | Limit | Headroom |
| --- | ---: | ---: | ---: |
| 401(k) deferrals (box 12 D) | 16400 | 23500 | 7100 |
| HSA (payroll plus your own) | 8550 | 8550 | 0 |
| Traditional IRA (deductible) | 0 | 7000 | 7000 |

## Forms received

One row per W-2 in `inputs/`, read from each file's front matter every night. Add a form in the evening and it is here in the morning, before any refresh.

<!-- data: inputs/*.md -->
| Employer | Tax year | Box1 wages | Box2 federal withheld | Box12 D 401k |
| --- | ---: | ---: | ---: | ---: |
| Example Employer Inc. | 2025 | 148600 | 21940 | 16400 |

## Actions

Your tracker, read from [[Tax Profile]] each night. Change a status there; it is current here in the morning.

<!-- data: Tax Profile.md#actions -->
| id | action | due | status |
| --- | --- | --- | --- |
| T1 | Confirm every W-2 and 1099 has arrived | 2026-02-15 | done |
| T2 | Max the HSA for the year | 2026-04-15 | done |
| T3 | Gather property tax and mortgage interest statements | 2026-03-01 | in progress |
| T4 | Decide standard versus itemized from the estimate below | 2026-03-15 | open |
| T5 | Fund the IRA if still deductible | 2026-04-15 | open |
| T6 | File, or request the extension | 2026-04-15 | open |
| T7 | Raise 401(k) deferral to the 2026 limit | 2026-01-31 | open |

## Deadlines

<!-- data: data/tax-figures.json#deadlines -->
| What | When | Source |
| --- | --- | --- |
| 2025 return due (or extension request) | 2026-04-15 | irs.gov/filing/individuals/when-to-file |
| 2025 return due with extension | 2026-10-15 | irs.gov/filing/individuals/when-to-file |
| 2026 estimated tax, third payment | 2026-09-15 | Form 1040-ES |
| 2026 estimated tax, fourth payment | 2027-01-15 | Form 1040-ES |
| W-2 and 1099 forms due to you | 2027-02-01 | irs.gov (January 31 falls on a Sunday in 2027) |
| 2026 return due | 2027-04-15 | irs.gov/filing/individuals/when-to-file |

## The figures the estimate uses

Verified against the IRS pages named in each row on 2 September 2026. When the IRS publishes new figures, edit `data/tax-figures.json`; the refresh uses it and this table redraws.

<!-- data: data/tax-figures.json#figures -->
| Item | 2025 | 2026 | Source |
| --- | ---: | ---: | --- |
| Standard deduction, single | 15750 | 16100 | IR-2025-103; Rev. Proc. 2025-32 §2.15 |
| Standard deduction, married filing jointly | 31500 | 32200 | IR-2025-103; Rev. Proc. 2025-32 §2.15 |
| Standard deduction, married filing separately | 15750 | 16100 | Rev. Proc. 2025-32 §2.15 |
| Standard deduction, head of household | 23625 | 24150 | IR-2025-103; Rev. Proc. 2025-32 §2.15 |
| Additional standard deduction, 65 or blind, married (each) | 1600 | 1650 | Rev. Proc. 2024-40; Rev. Proc. 2025-32 §2.15 |
| Additional standard deduction, 65 or blind, unmarried | 2000 | 2050 | Rev. Proc. 2024-40; Rev. Proc. 2025-32 §2.15 |
| Senior deduction, 65 or older (each), 2025–2028 | 6000 | 6000 | irs.gov/newsroom/working-families-tax-cuts-tax-deductions-for-working-americans-and-seniors |
| Senior deduction phase-out begins, MAGI, single | 75000 | 75000 | irs.gov/newsroom/working-families-tax-cuts-tax-deductions-for-working-americans-and-seniors |
| Senior deduction phase-out begins, MAGI, joint | 150000 | 150000 | irs.gov/newsroom/working-families-tax-cuts-tax-deductions-for-working-americans-and-seniors |
| Child tax credit, per qualifying child under 17 | 2200 | 2200 | irs.gov/credits-deductions/individuals/child-tax-credit |
| Credit for other dependents, each | 500 | 500 | irs.gov/credits-deductions/individuals/child-tax-credit |
| Child tax credit phase-out begins, single and head of household | 200000 | 200000 | irs.gov/credits-deductions/individuals/child-tax-credit |
| Child tax credit phase-out begins, joint | 400000 | 400000 | irs.gov/credits-deductions/individuals/child-tax-credit |
| State and local tax deduction cap | 40000 | 40400 | Pub. L. 119-21 §70120 (the cap rises 1% a year through 2029; phases down above $500,000 MAGI, $505,000 in 2026, to a $10,000 floor) |
| 401(k), 403(b), most 457 elective deferral limit | 23500 | 24500 | irs.gov/newsroom/401k-limit-increases-to-24500-for-2026-ira-limit-increases-to-7500 |
| 401(k) catch-up, age 50 and over | 7500 | 8000 | irs.gov/newsroom/401k-limit-increases-to-24500-for-2026-ira-limit-increases-to-7500 |
| 401(k) catch-up, ages 60 to 63 | 11250 | 11250 | irs.gov/newsroom/401k-limit-increases-to-24500-for-2026-ira-limit-increases-to-7500 |
| IRA contribution limit | 7000 | 7500 | irs.gov/newsroom/401k-limit-increases-to-24500-for-2026-ira-limit-increases-to-7500 |
| IRA catch-up, age 50 and over | 1000 | 1100 | irs.gov/newsroom/401k-limit-increases-to-24500-for-2026-ira-limit-increases-to-7500 |
| HSA contribution limit, self-only coverage | 4300 | 4400 | Rev. Proc. 2024-25; Rev. Proc. 2025-19 |
| HSA contribution limit, family coverage | 8550 | 8750 | Rev. Proc. 2024-25; Rev. Proc. 2025-19 |
| HSA catch-up, age 55 and over | 1000 | 1000 | 26 U.S.C. §223(b)(3) |
| Student loan interest deduction, maximum | 2500 | 2500 | 26 U.S.C. §221 |
| Annual gift exclusion | 19000 | 19000 | IR-2025-103 |
| Estate basic exclusion | 13990000 | 15000000 | IR-2025-103 |

## What the estimate leaves out

<!-- data: data/tax-figures.json#notComputed -->
| Item | Why | Source |
| --- | --- | --- |
| No tax on tips, deduction up to $25,000 (2025–2028) | Needs the qualified-tip amount from the W-2; enter it as a note for now. | irs.gov/newsroom/working-families-tax-cuts-tax-deductions-for-working-americans-and-seniors |
| No tax on overtime, deduction up to $12,500 ($25,000 joint), 2025–2028 | Needs the qualified-overtime amount from the W-2. | irs.gov/newsroom/working-families-tax-cuts-tax-deductions-for-working-americans-and-seniors |
| Car loan interest deduction up to $10,000 (2025–2028) | Needs the loan's interest statement and the vehicle's assembly location. | irs.gov/newsroom/working-families-tax-cuts-tax-deductions-for-working-americans-and-seniors |
| Long-term capital gains and qualified dividends at 0/15/20% | The estimate taxes all income at ordinary rates, which overstates the tax when gains are long-term. A conservative simplification. | 26 U.S.C. §1(h) |
| State income tax | Federal only. The profile's state is kept for your own record. |  |
| Alternative minimum tax, net investment income tax, self-employment tax | Outside this estimate. |  |

## Your inputs folder

```flow-folder inputs
| File | Size | Modified | Digest |
| --- | ---: | --- | --- |
| W-2 — Example Employer.md | 1718 | 2026-09-03T04:41:07Z | 00838655fc3b |
```

## What you will see in the morning

- **The IRS moved.** A watched page changed: a new deadline, a new figure, a new release in the newsroom. The Briefing shows the text that changed, and you decide whether `data/tax-figures.json` needs a new number.
- **A form arrived.** You dropped a second W-2 in `inputs/`: the inventory names it, *Forms received* has its row, and the next refresh adds it to the estimate.
- **You ticked an action off.** The tracker above shows it done.

## Make it yours

1. Fill in the front matter of [[Tax Profile]].
2. Copy `inputs/W-2 — Example Employer.md` once per employer and type the boxes. Delete the example when yours are in.
3. Use Run now (the moon in the title bar). Flow works the estimate out from [[Tax Refresh]] — the profile, your forms and the year's figures — writes it into `data/` and redraws the page. Every night after that it does the same before the page redraws, so a changed form is in the morning's page.
4. Turn the Night Shift on: the moon in the title bar, or Settings ▸ Night Shift.

## How this page is built

| Block | Construct | Bound to | Redrawn by |
| --- | --- | --- | --- |
| At a glance | KPI Card | `data/estimate-*.json#summary` | refresh, then the night |
| Income bridge | Waterfall Chart | `#bridge` | refresh, then the night |
| By bracket | Bar Chart | `#taxByBracket` | refresh, then the night |
| Withheld against owed | Bullet Chart | `#withholding` | refresh, then the night |
| Standard or itemized, headroom | tables | `#deductionChoice`, `#headroom` | refresh, then the night |
| Forms received | table over a glob | `inputs/*.md` | the night alone |
| Actions | table | `Tax Profile.md#actions` | the night alone |
| Deadlines, figures, left out | tables | `data/tax-figures.json#…` | the night, when you edit the file |
| Inputs folder | `flow-folder` inventory | `inputs/` | the night alone |

## Overnight notes
<!-- night: notes -->
<!-- /night: notes -->
