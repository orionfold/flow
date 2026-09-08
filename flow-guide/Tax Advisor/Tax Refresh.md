---
title: Tax Refresh
tags: [tax, definition, night-shift]
sources:
  profile: Tax Profile.md
  forms: inputs/*.md
  figureRows: data/tax-figures.json#figures
  bracketRows:
    path: data/tax-figures.json
    key: brackets
    flatten: {as: [year, status], of: [upper, rate]}
  bracketSources:
    path: data/tax-figures.json
    key: brackets
    flatten: {as: [year, key], of: [source]}
derive:
  w2:
    from: forms
    steps:
      - {filter: "form == 'W-2'"}
  figures:
    from: figureRows
    steps:
      - {fold: ["2025", "2026"], key: year, value: amount}
  brackets:
    from: bracketRows
    steps:
      - {filter: "year == taxYear && status == filingStatus"}
      - {window: "", last: upper, as: lower, frame: [-1, -1]}
      - {calculate: "coalesce(lower, 0)", as: lower}
      - {calculate: "min(taxable, coalesce(upper, taxable)) - lower", as: inBracket}
      - {filter: "inBracket > 0"}
      - {calculate: "inBracket * rate", as: bracketTax}
  summaryRows:
    rows:
      - {metric: "{balance >= 0 ? 'Estimated refund' : 'Estimated balance due'}", value: "{abs(balance)}"}
      - {metric: Taxable income, value: "{round(taxable, 0)}", goal: "{round(agi, 0)}"}
      - {metric: "Effective rate, %", value: "{agi > 0 ? round(liability / agi * 100, 1) : 0}", goal: "{round(marginalRate * 100, 0)}"}
      - {metric: Federal tax after credits, value: "{round(liability, 0)}", goal: "{round(paid, 0)}"}
  bridgeRows:
    rows:
      - {step: W-2 wages, change: "{round(wages, 0)}"}
      - {step: Other income, change: "{round(otherIncome, 0)}"}
      - {step: Adjustments, change: "{-round(adjustments, 0)}"}
      - {step: "{usesItemized ? 'Itemized deduction' : 'Standard deduction'}", change: "{-round(deduction, 0)}"}
  seniorRow:
    rows:
      - {step: Senior deduction, change: "{-round(seniorDeduction, 0)}"}
  taxableRow:
    rows:
      - {step: Taxable income, change: "{round(taxable, 0)}"}
  seniorLine:
    from: seniorRow
    steps:
      - {filter: "seniorDeduction > 0"}
let:
  taxYear: {max: value, of: profile, where: "key == 'tax_year'"}
  filingStatus: {max: value, of: profile, where: "key == 'filing_status'"}
  age: {max: value, of: profile, where: "key == 'age'"}
  spouseAge: {max: value, of: profile, where: "key == 'spouse_age'"}
  joint: "filingStatus == 'married_jointly'"
  unmarried: "filingStatus == 'single' || filingStatus == 'head_of_household'"
  statusName: "filingStatus == 'single' ? 'single' : filingStatus == 'married_jointly' ? 'married filing jointly' : filingStatus == 'married_separately' ? 'married filing separately' : 'head of household'"
  formCount: {count: form, of: w2}
  wages: {sum: box1_wages, of: w2}
  withheld: {sum: box2_federal_withheld, of: w2}
  deferrals: {sum: box12_d_401k, of: w2}
  payrollHSA: {sum: box12_w_hsa_employer, of: w2}
  interestIncome: {max: value, of: profile, where: "key == 'interest_income'"}
  dividendIncome: {max: value, of: profile, where: "key == 'dividend_income'"}
  capitalGains: {max: value, of: profile, where: "key == 'capital_gains'"}
  otherIncomeLine: {max: value, of: profile, where: "key == 'other_income'"}
  otherIncome: "coalesce(interestIncome, 0) + coalesce(dividendIncome, 0) + coalesce(capitalGains, 0) + coalesce(otherIncomeLine, 0)"
  iraDeductible: {max: value, of: profile, where: "key == 'ira_deductible'"}
  hsaContributions: {max: value, of: profile, where: "key == 'hsa_contributions'"}
  hsaCoverage: {max: value, of: profile, where: "key == 'hsa_coverage'"}
  studentLoanPaid: {max: value, of: profile, where: "key == 'student_loan_interest'"}
  studentLoanCap: {max: amount, of: figures, where: "Item == 'Student loan interest deduction, maximum' && year == taxYear"}
  studentLoan: "min(coalesce(studentLoanPaid, 0), studentLoanCap)"
  hsaSelfLimit: {max: amount, of: figures, where: "Item == 'HSA contribution limit, self-only coverage' && year == taxYear"}
  hsaFamilyLimit: {max: amount, of: figures, where: "Item == 'HSA contribution limit, family coverage' && year == taxYear"}
  hsaCatchUp: {max: amount, of: figures, where: "Item == 'HSA catch-up, age 55 and over' && year == taxYear"}
  hsaBase: "hsaCoverage == 'family' ? hsaFamilyLimit : hsaCoverage == 'self' ? hsaSelfLimit : 0"
  hsaLimit: "hsaBase > 0 && (age >= 55 || (joint && spouseAge >= 55)) ? hsaBase + hsaCatchUp : hsaBase"
  hsaDeductible: "max(0, min(coalesce(hsaContributions, 0), hsaLimit - payrollHSA))"
  adjustments: "coalesce(iraDeductible, 0) + hsaDeductible + studentLoan"
  agi: "wages + otherIncome - adjustments"
  standardBase: {max: amount, of: figures, where: "Item == 'Standard deduction, ' + statusName && year == taxYear"}
  seniors: "(age >= 65 ? 1 : 0) + (joint && spouseAge >= 65 ? 1 : 0)"
  additionalUnmarried: {max: amount, of: figures, where: "Item == 'Additional standard deduction, 65 or blind, unmarried' && year == taxYear"}
  additionalMarried: {max: amount, of: figures, where: "Item == 'Additional standard deduction, 65 or blind, married (each)' && year == taxYear"}
  standard: "standardBase + seniors * (unmarried ? additionalUnmarried : additionalMarried)"
  saltCapBase: {max: amount, of: figures, where: "Item == 'State and local tax deduction cap' && year == taxYear"}
  saltPhaseStart: "taxYear == 2025 ? 500000 : 505000"
  saltCap: "agi > saltPhaseStart ? max(10000, saltCapBase - 0.30 * (agi - saltPhaseStart)) : saltCapBase"
  medicalExpenses: {max: value, of: profile, where: "key == 'medical_expenses'"}
  medical: "max(0, coalesce(medicalExpenses, 0) - 0.075 * agi)"
  mortgageInterest: {max: value, of: profile, where: "key == 'mortgage_interest'"}
  stateLocalTaxes: {max: value, of: profile, where: "key == 'state_local_taxes'"}
  charitable: {max: value, of: profile, where: "key == 'charitable'"}
  saltClaimed: "min(coalesce(stateLocalTaxes, 0), saltCap)"
  itemized: "coalesce(mortgageInterest, 0) + saltClaimed + coalesce(charitable, 0) + medical"
  usesItemized: "itemized > standard"
  deduction: "max(standard, itemized)"
  seniorBase: {max: amount, of: figures, where: "Item == 'Senior deduction, 65 or older (each), 2025–2028' && year == taxYear"}
  seniorPhaseJoint: {max: amount, of: figures, where: "Item == 'Senior deduction phase-out begins, MAGI, joint' && year == taxYear"}
  seniorPhaseSingle: {max: amount, of: figures, where: "Item == 'Senior deduction phase-out begins, MAGI, single' && year == taxYear"}
  seniorPhase: "joint ? seniorPhaseJoint : seniorPhaseSingle"
  seniorGross: "seniors * seniorBase"
  seniorDeduction: "seniorGross > 0 && agi > seniorPhase ? max(0, seniorGross - 0.06 * (agi - seniorPhase)) : seniorGross"
  taxable: "max(0, agi - deduction - seniorDeduction)"
  tax: {sum: bracketTax, of: brackets}
  marginalRate: {last: rate, of: brackets}
  childCount: {max: value, of: profile, where: "key == 'dependents_under_17'"}
  otherDependents: {max: value, of: profile, where: "key == 'other_dependents'"}
  childCreditEach: {max: amount, of: figures, where: "Item == 'Child tax credit, per qualifying child under 17' && year == taxYear"}
  otherDependentEach: {max: amount, of: figures, where: "Item == 'Credit for other dependents, each' && year == taxYear"}
  creditPhaseJoint: {max: amount, of: figures, where: "Item == 'Child tax credit phase-out begins, joint' && year == taxYear"}
  creditPhaseSingle: {max: amount, of: figures, where: "Item == 'Child tax credit phase-out begins, single and head of household' && year == taxYear"}
  creditPhase: "joint ? creditPhaseJoint : creditPhaseSingle"
  creditGross: "coalesce(childCount, 0) * childCreditEach + coalesce(otherDependents, 0) * otherDependentEach"
  creditPhased: "agi > creditPhase ? max(0, creditGross - 50 * ceil((agi - creditPhase) / 1000)) : creditGross"
  credit: "min(creditPhased, tax)"
  liability: "tax - credit"
  estimatedPayments: {max: value, of: profile, where: "key == 'estimated_payments'"}
  paid: "withheld + coalesce(estimatedPayments, 0)"
  balance: "round(paid - liability, 0)"
  deferralBase: {max: amount, of: figures, where: "Item == '401(k), 403(b), most 457 elective deferral limit' && year == taxYear"}
  deferralCatchUp50: {max: amount, of: figures, where: "Item == '401(k) catch-up, age 50 and over' && year == taxYear"}
  deferralCatchUp60: {max: amount, of: figures, where: "Item == '401(k) catch-up, ages 60 to 63' && year == taxYear"}
  deferralLimit: "age >= 60 && age <= 63 ? deferralBase + deferralCatchUp60 : age >= 50 ? deferralBase + deferralCatchUp50 : deferralBase"
  iraBase: {max: amount, of: figures, where: "Item == 'IRA contribution limit' && year == taxYear"}
  iraCatchUp: {max: amount, of: figures, where: "Item == 'IRA catch-up, age 50 and over' && year == taxYear"}
  iraLimit: "age >= 50 ? iraBase + iraCatchUp : iraBase"
  bracketsSourceText: {max: source, of: bracketSources, where: "year == taxYear && key == 'source'"}
emit:
  taxYear: "{taxYear}"
  filingStatus: "{filingStatus}"
  forms: "{formCount}"
  bracketsSource: "{bracketsSourceText}"
  summary:
    from: summaryRows
  bridge:
    from: bridgeRows
    steps:
      - {concat: seniorLine}
      - {concat: taxableRow}
  taxByBracket:
    from: brackets
    steps:
      - {calculate: "text(round(rate * 100, 0)) + '%'", as: bracket}
      - {calculate: "round(inBracket, 0)", as: income}
      - {calculate: "round(bracketTax, 0)", as: tax}
      - {columns: [bracket, income, tax]}
  withholding:
    - {metric: Federal withheld and paid, actual: "{round(paid, 0)}", goal: "{round(liability, 0)}"}
  headroom:
    - {Account: "401(k) deferrals (box 12 D)", Contributed: "{round(deferrals, 0)}", Limit: "{deferralLimit}", Headroom: "{round(max(0, deferralLimit - deferrals), 0)}"}
    - {Account: HSA (payroll plus your own), Contributed: "{round(payrollHSA + coalesce(hsaContributions, 0), 0)}", Limit: "{hsaLimit}", Headroom: "{round(max(0, hsaLimit - payrollHSA - coalesce(hsaContributions, 0)), 0)}"}
    - {Account: Traditional IRA (deductible), Contributed: "{round(coalesce(iraDeductible, 0), 0)}", Limit: "{iraLimit}", Headroom: "{round(max(0, iraLimit - coalesce(iraDeductible, 0)), 0)}"}
  deductionChoice:
    - {Route: Standard deduction, Amount: "{round(standard, 0)}", Chosen: "{usesItemized ? '' : 'yes'}"}
    - {Route: "Itemized: mortgage interest", Amount: "{round(coalesce(mortgageInterest, 0), 0)}", Chosen: "{''}"}
    - {Route: "{'Itemized: state and local taxes, capped at ' + text(round(saltCap, 0))}", Amount: "{round(saltClaimed, 0)}", Chosen: "{''}"}
    - {Route: "Itemized: charitable", Amount: "{round(coalesce(charitable, 0), 0)}", Chosen: "{''}"}
    - {Route: "Itemized: medical above 7.5% of AGI", Amount: "{round(medical, 0)}", Chosen: "{''}"}
    - {Route: "Itemized total", Amount: "{round(itemized, 0)}", Chosen: "{usesItemized ? 'yes' : ''}"}
---
# How this estimate is worked out

This is the definition [[Tax Advisor]] runs each night. It is **data, not code** — every line is something you can read and change, and Flow works the estimate out itself rather than running a program. It reads three things and nothing else: [[Tax Profile]], the W-2 forms in `inputs/`, and the figures in `data/tax-figures.json`. Nothing is fetched and nothing leaves your Mac.

**It is an estimate, not advice.** What it does not compute is listed in `data/tax-figures.json` under `notComputed`, and on [[Tax Advisor]] itself.

## The four blocks

| Block | What it is for |
| --- | --- |
| `sources:` | Your profile, your W-2 forms, and the year's figures and brackets |
| `derive:` | The W-2 forms that count, the figures by year, and the brackets your income falls in |
| `let:` | Every single value the estimate is built from, in the order it is worked out |
| `emit:` | The tables the capture holds, one per chart and table on the page |

## `sources:` — the brackets, read as a table

`data/tax-figures.json` holds the brackets two levels deep: by year, then by filing status. `flatten:` reads **every** bracket as a row and names those two levels `year` and `status`, so choosing yours becomes an ordinary filter rather than a path Flow has to build from your profile. The file stays something you can open and read.

Each bracket is a pair — where it ends and its rate — and `of: [upper, rate]` names them. The top bracket has no end at all, and the definition reads it as `coalesce(upper, taxable)`: the bracket that goes all the way up.

## `derive:` — the bracket walk

Tax is worked out band by band. Each bracket's lower edge is the one above it, which is what `frame: [-1, -1]` says: look at exactly the row before this one. The first bracket has no row before it, so `coalesce(lower, 0)` starts it at zero — which is also the right answer.

`figures` is folded from columns into rows, so a figure is chosen by matching its year the same way a bracket is. Two years live in that file and only one is yours.

## `let:` — the estimate, in order

Read top to bottom and it is the return: wages and other income, the adjustments that come off, the deduction — the larger of standard and itemized — the senior deduction and its phase-out, taxable income, the tax by bracket, the credits and their phase-out, and what you have already paid.

Each phase-out is written as a `? :` so you can see the threshold and the taper, rather than a rule you have to trust.

## Making it yours

Edit [[Tax Profile]] rather than this file for anything ordinary — your filing status, your dependents, the income and deductions that are yours. Update `data/tax-figures.json` when a new year's figures are published. Come back here to add a table or change what a summary row measures.
