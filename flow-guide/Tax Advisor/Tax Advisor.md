---
title: Tax Advisor
category: personal-money
summary: "Tax-year inputs, a bounded estimate and questions for your preparer."
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

**Prepare the evidence and questions needed to finish a federal return.** The useful decision is whether the inputs are complete enough for a preparer to rely on the estimate.

> Fictional household · 2025 return review · reference snapshot 2 September 2026. The supplied snapshot’s $12,774 refund is an illustrative estimate from entered data, not an approved return or a current refund claim.

**Next action:** reconcile the missing mortgage/property-tax evidence and confirm whether a filing extension was actually submitted. Do not infer a filing deadline from an unfinished checklist.

[[Tax Profile]] owns the household facts; `inputs/` holds the forms; [[Tax Refresh]] selects matching-year W-2s and applies the local figures. [[Tax Estimate Basis]] names the scope, uncomputed items and official rule sources. Contributions and deductible amounts are different inputs.

**Before using 2026 figures:** `charitable` must be an already-reviewed allowable itemized deduction, after applicable limits including the 0.5% of AGI floor. The calculation does not apply the new overall limit on itemized deductions or the separate deduction for eligible cash gifts when taking the standard deduction. A 2026 estimate affected by those omitted rules remains incomplete; changing the tax-year field does not resolve them. See [[Tax Estimate Basis]].

## Input basis before the result

<!-- data: data/estimate-*.json#inputCoverage -->
| Item | Value |
| --- | --- |
| Tax year | 2025 |
| Matching W-2 forms | 1 |
| Basis | Entered income and matching-year forms; completeness is not verified |

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
  color: {field: bracket, scheme: purples}
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

## Taxpayer contribution amounts and annual caps

These annual caps do not establish contribution or deduction eligibility. W-2 contribution rows include only forms whose `employee` is `Taxpayer`; wages and withholding include all matching-year forms. A spouse's account and shared HSA-limit allocation need a separate review; this HSA example assumes no spouse contributions.

<!-- data: data/estimate-*.json#headroom -->
| Account | Contributed | Limit | Headroom |
| --- | ---: | ---: | ---: |
| Taxpayer 401(k) contributions | 16400 | 23500 | 7100 |
| Taxpayer HSA contributions | 8550 | 8550 | 0 |
| Taxpayer IRA contributions (not deduction eligibility) | 0 | 7000 | 7000 |

## Forms received

Inventory of supplied forms, including other years. Only matching-year W-2s enter the estimate. Keep `employee: Taxpayer` or `employee: Spouse` explicit; a form with a missing year is not silently assigned to the selected year.

<!-- data: inputs/*.md#tables:Record -->
| Employer | Tax year | Box1 wages | Box2 federal withheld | Box12 D 401k |
| --- | ---: | ---: | ---: | ---: |
| Example Employer Inc. | 2025 | 148600 | 21940 | 16400 |

## Actions

Your tracker, read from [[Tax Profile]] each night. Change a status there; it is current here in the morning.

<!-- data: Tax Profile.md#table:Actions -->
| id | action | due | status |
| --- | --- | --- | --- |
| T1 | Confirm every W-2 and 1099 has arrived | 2026-02-15 | done |
| T2 | Max the HSA for the year | 2026-04-15 | done |
| T3 | Gather property tax and mortgage interest statements | 2026-03-01 | in progress |
| T4 | Decide standard versus itemized from the estimate below | 2026-03-15 | open |
| T5 | Confirm the eligibility of any IRA contribution already made | 2026-04-15 | open |
| T6 | File, or request the extension | 2026-04-15 | open |
| T7 | Review the separate 2026 contribution plan | 2026-01-31 | open |

## Source inventory

```flow-folder inputs
| File | Size | Modified | Digest |
| --- | ---: | --- | --- |
| W-2 — Example Employer.md | 2138 |  |  |
```

Bundled file list; the inventory job fills timestamps and digests in your working copy.

## What changes on a run

The local Gather recalculates from entered inputs, writes the dated estimate and refreshes its bound views. Source watches can report changes to the explicitly named IRS pages; they do **not** update or validate the tax figures. Optional Overnight notes interpret the available tables with the configured local model; inspect them against the source rows. Review a changed rule with your preparer before editing [[Tax Estimate Basis]] or the figures.

## Make it yours

1. Copy the whole **Tax Advisor** folder into your own location and add it to Flow. Keep the local forms, figures, saved output and both supporting documents together.
2. Before the first run, choose **File ▸ Night Shift Jobs…** on this document and remove the named IRS web watches if you want local-only work. The estimate itself uses local files. **Settings ▸ Night Shift ▸ Run now** runs the jobs you retained; enable Night Shift only for scheduled updates.
3. Open [[Tax Profile]], choose **View ▸ Edit Table**, change the **Settings** value for `estimated_payments` from 0 to 100, and save. Open [[Tax Refresh]], then choose **File ▸ Edit Definition…**. Return to this Tax Advisor document to review its saved job with **File ▸ Night Shift Jobs…**. A completed run should increase this sample refund from 12,774 to 12,874 without changing liability.
4. Replace the fictional W-2; use its **Record** table to enter the actual tax year and `Taxpayer` or `Spouse` in the `employee` column. Replace every sample profile amount. Other-year forms may stay in the inventory but are excluded from the calculation. No forms still yields an entered-income-only estimate.
5. Review the scope in [[Tax Estimate Basis]]. Enter only verified deductible IRA/student-loan amounts; do not copy a contribution limit into a deduction field. Review the capture, result and source changes before treating the document as current.

## Overnight notes
<!-- night: notes -->
<!-- /night: notes -->
