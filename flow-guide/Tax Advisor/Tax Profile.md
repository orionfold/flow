---
title: Tax Profile
tags: [tax, parameters, night-shift]
tax_year: 2025
filing_status: married_jointly
state: CA
age: 41
spouse_age: 39
dependents_under_17: 2
other_dependents: 0
hsa_coverage: family
interest_income: 1850
dividend_income: 2400
capital_gains: 3200
other_income: 0
ira_deductible: 0
hsa_contributions: 8550
student_loan_interest: 0
estimated_payments: 0
mortgage_interest: 14200
state_local_taxes: 21800
charitable: 3600
medical_expenses: 0
actions:
  - {id: T1, action: Confirm every W-2 and 1099 has arrived, due: 2026-02-15, status: done}
  - {id: T2, action: Max the HSA for the year, due: 2026-04-15, status: done}
  - {id: T3, action: Gather property tax and mortgage interest statements, due: 2026-03-01, status: in progress}
  - {id: T4, action: Decide standard versus itemized from the estimate below, due: 2026-03-15, status: open}
  - {id: T5, action: Fund the IRA if still deductible, due: 2026-04-15, status: open}
  - {id: T6, action: "File, or request the extension", due: 2026-04-15, status: open}
  - {id: T7, action: Raise 401(k) deferral to the 2026 limit, due: 2026-01-31, status: open}
---
# Tax Profile

The one file you edit. The front matter is your situation for the year: who is filing, who depends on you, the income that does not arrive on a W-2, the deductions you could itemize, and the actions you are tracking. [[Tax Advisor]] reads it each night for the actions table, and the refresh script reads it, with the W-2 forms in `inputs/`, to estimate the federal return.

## What each field means

| Field | What it is | Values |
| --- | --- | --- |
| `tax_year` | The year being estimated. Figures for 2025 and 2026 ship in `data/tax-figures.json`. | `2025`, `2026` |
| `filing_status` | How you file. | `single`, `married_jointly`, `married_separately`, `head_of_household` |
| `state` | Kept for your record. State tax is not estimated. | `CA` |
| `age`, `spouse_age` | Ages at the end of the year; 65 and over changes the deduction. | `41` |
| `dependents_under_17` | Children who qualify for the child tax credit. | `2` |
| `other_dependents` | Dependents who qualify for the $500 credit instead. | `0` |
| `hsa_coverage` | Whether your health plan lets you contribute to an HSA, and at which limit. | `none`, `self`, `family` |
| `interest_income`, `dividend_income`, `capital_gains`, `other_income` | Income that does not come on a W-2, whole dollars. Gains are taxed at ordinary rates in this estimate, which is conservative. | `1850` |
| `ira_deductible` | Traditional IRA contributions you can deduct. | `0` |
| `hsa_contributions` | What you put into the HSA outside payroll. Payroll HSA amounts are already out of W-2 wages. | `8550` |
| `student_loan_interest` | Interest paid, capped at the year's maximum. | `0` |
| `estimated_payments` | Quarterly payments already made for the year. | `0` |
| `mortgage_interest`, `state_local_taxes`, `charitable`, `medical_expenses` | What you could itemize. The estimate takes the larger of itemized and standard; state and local taxes are capped. | `14200` |
| `actions` | Your tracker. Edit `status` as you go: `open`, `in progress`, `done`. | see above |

## Make it yours

- **Add a W-2.** Copy `inputs/W-2 — Example Employer.md`, name it for the employer, and type the box values from the form. Each file is one W-2. The night lists them in the morning; the refresh adds them up.
- **Change the year.** Set `tax_year: 2026` to estimate next year from this year's numbers.
- **Track a task.** Add an `actions` line with the next `id`.

An estimate, not advice. It uses the figures the IRS has published and the simplifications listed at the end of [[Tax Advisor]]. Your preparer or your software decides the return.
