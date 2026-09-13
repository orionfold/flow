---
title: Tax Profile
tags: [tax, parameters, night-shift]
---
# Tax Profile

**Illustrative business inputs.** Edit the named table using its **Open in the table editor** control. **View ▸ Edit Table** opens the first table. Save the input document, then run the Jobs on [[Tax Advisor]]; its refreshed views read these saved rows.

## Settings

| key | value |
| --- | --- |
| tax_year | 2025 |
| filing_status | married_jointly |
| state | CA |
| age | 41 |
| spouse_age | 39 |
| dependents_under_17 | 2 |
| other_dependents | 0 |
| hsa_coverage | family |
| interest_income | 1850 |
| dividend_income | 2400 |
| capital_gains | 3200 |
| other_income | 0 |
| ira_contributions | 0 |
| ira_deductible | 0 |
| hsa_contributions | 8550 |
| student_loan_interest | 0 |
| student_loan_deductible | 0 |
| spouse_itemizes | false |
| estimated_payments | 0 |
| mortgage_interest | 14200 |
| state_local_taxes | 21800 |
| charitable | 3600 |
| medical_expenses | 0 |

## Actions

| id | action | due | status |
| --- | --- | --- | --- |
| T1 | Confirm every W-2 and 1099 has arrived | 2026-02-15 | done |
| T2 | Max the HSA for the year | 2026-04-15 | done |
| T3 | Gather property tax and mortgage interest statements | 2026-03-01 | in progress |
| T4 | Decide standard versus itemized from the estimate below | 2026-03-15 | open |
| T5 | Confirm the eligibility of any IRA contribution already made | 2026-04-15 | open |
| T6 | File, or request the extension | 2026-04-15 | open |
| T7 | Review the separate 2026 contribution plan | 2026-01-31 | open |

## About these inputs

Illustrative household for tax year 2025, reviewed 12 September 2026. This is one of the inputs you edit. The input tables contain your situation for the year: who is filing, who depends on you, the income that does not arrive on a W-2, the deductions you could itemize, and the actions you are tracking. [[Tax Advisor]] reads it each night for the actions table, and [[Tax Refresh]] reads it, with the W-2 forms in `inputs/`, to estimate the federal return.

## What each field means

| Field | What it is | Values |
| --- | --- | --- |
| `tax_year` | Selects the reference figures and matching-year forms. For 2026, review the uncomputed deduction rules in [[Tax Estimate Basis]] before relying on a result. | `2025`, `2026` |
| `filing_status` | How you file. | `single`, `married_jointly`, `married_separately`, `head_of_household` |
| `state` | Kept for your record. State tax is not estimated. | `CA` |
| `age`, `spouse_age` | Ages at the end of the year; 65 and over changes the deduction. | `41` |
| `dependents_under_17` | Children who qualify for the child tax credit. | `2` |
| `other_dependents` | Dependents who qualify for the $500 credit instead. | `0` |
| `hsa_coverage` | Taxpayer-owned HSA, assuming eligible coverage all year. Medicare, partial-year coverage and spouse catch-up allocation are outside this example. | `none`, `self`, `family` |
| `interest_income`, `dividend_income`, `capital_gains`, `other_income` | Income that does not come on a W-2, whole dollars. Gains and dividends are treated as ordinary income here; this is not a total-tax upper bound. | `1850` |
| `ira_contributions` | Taxpayer contributions across traditional and Roth IRAs; compared with the annual contribution cap, not eligibility. | `0` |
| `ira_deductible` | Allowed traditional IRA deduction already checked against workplace coverage and MAGI; Flow does not determine it. | `0` |
| `student_loan_deductible` | Allowed student-loan deduction after MAGI and other eligibility checks. Defaults to zero; MFS is always zero here. | `0` |
| `spouse_itemizes` | For married filing separately: true removes the standard deduction. | `false` |
| `hsa_contributions` | What you put into the HSA outside payroll. Payroll HSA amounts are already out of W-2 wages. | `8550` |
| `student_loan_interest` | Interest paid. The deduction is entered separately after eligibility and MAGI review. | `0` |
| `estimated_payments` | Quarterly payments already made for the year. | `0` |
| `mortgage_interest`, `state_local_taxes`, `medical_expenses` | Eligible itemized inputs. The estimate compares itemized and standard; state and local taxes are capped. The 2026 overall itemized limit is not applied. | `14200` |
| `charitable` | Already-reviewed allowable itemized charitable deduction, after contribution limits and the 2026 0.5% of AGI floor where applicable. Recheck when income or gifts change; do not enter total gifts or a non-itemizer deduction here. | `3600` |
| `actions` | Your tracker. Edit `status` as you go: `open`, `in progress`, `done`. | see above |

## Make it yours

- **Add a W-2.** Copy `inputs/W-2 — Example Employer.md`, name it for the employer, and edit its **Record** table with **View ▸ Edit Table**. Each file is one W-2. The night lists them in the morning; the refresh adds them up.
- **Change the year.** Review the uncomputed 2026 deduction rules in [[Tax Estimate Basis]], then change the `tax_year` row in **Settings** to 2026 only with 2026 forms and income. Forms from other years remain in the inventory but do not enter the calculation. A forecast requires explicitly entered forecast inputs; changing the year does not project income.
- **Track a task.** Open **Actions** in the Table editor and add a row with the next `id`.

An estimate, not advice. It uses the figures the IRS has published and the limitations recorded in [[Tax Estimate Basis]]. Your preparer or your software decides the return.
