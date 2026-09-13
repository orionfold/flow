---
title: Tax Estimate Basis
tags: [tax, sources, methodology]
---
# Tax Estimate Basis

This worksheet is a bounded federal estimate using entered income and matching-year W-2 forms. The input-completeness question is separate from the arithmetic. No matching forms means an **entered-income-only** estimate, not proof of zero wages for the year.

## Supported assumptions

- Reference figures and ordinary-income rate schedules for 2025 and 2026 are included for the four listed filing statuses. The 2026 deduction rules listed below are not fully computed; affected estimates remain incomplete. Qualified dividends and long-term gains are treated as ordinary income; this does not make the entire estimate conservative.
- Taxpayer and spouse meet applicable residency, SSN and dependent-eligibility requirements; no foreign-income exclusions or other MAGI additions. Here AGI is used as the MAGI approximation for the SALT and senior phase-outs.
- A taxpayer-owned HSA with full-year eligible coverage. Medicare, partial-year coverage and allocation of a spouse's HSA/catch-up require separate review. All contribution headroom shown is for **Taxpayer**, not the combined household. The HSA example assumes no spouse HSA contributions; a shared-family-limit allocation needs a separate calculation before entering an allowed amount.
- `ira_contributions` counts taxpayer contributions across IRAs; the annual cap is not proof of compensation or deduction eligibility. Enter `ira_deductible` only after checking workplace coverage and MAGI. Likewise, `student_loan_deductible` is an already-reviewed allowable amount, capped against paid interest; married filing separately receives none.
- A separate filer whose spouse itemizes must enter `true` for `spouse_itemizes` in [[Tax Profile]]'s **Settings** table. Separate-return community-property allocation is not computed. Blindness additions, refundable credits, EITC and other eligibility-dependent adjustments are not computed.

- `charitable` is an already-reviewed allowable **itemized charitable deduction**, not total gifts. Apply contribution limits and, for 2026, the 0.5% of AGI floor before entering it. Recheck that amount whenever AGI or gifts change. This input does not supply the separate 2026 deduction for non-itemizers or apply the overall high-income itemized-deduction limit.

## Official sources behind the repaired rules

Reviewed 12 September 2026. These links support the named rules; they are not a claim that every possible return was validated.

| Rule | Primary source | What this worksheet does |
| --- | --- | --- |
| Enhanced senior deduction | [2025 Schedule 1-A, lines 31–37](https://www.irs.gov/pub/irs-prior/f1040s1a--2025.pdf) | Phase out each eligible person's $6,000, then add; married taxpayers must file jointly. |
| SALT cap and separate returns | [2025 Schedule A instructions](https://www.irs.gov/instructions/i1040sca) | Halve the cap, phase-out threshold and floor for married filing separately. |
| IRA deduction versus contribution | [Publication 590-A](https://www.irs.gov/publications/p590a) | Show the contribution cap separately; the allowed deduction is a reviewed input. |
| Student-loan interest eligibility | [Topic 456](https://www.irs.gov/taxtopics/tc456) | Require a reviewed deductible amount; do not infer MAGI eligibility from interest paid. |
| Separate filer and standard deduction | [Publication 17](https://www.irs.gov/publications/p17) | Remove the standard deduction when the spouse itemizes. |
| 2026 charitable floor and overall itemized limit | [Publication 505 (2026), Worksheets 2-5 and 2-6](https://www.irs.gov/publications/p505) | Neither is calculated here. The charitable amount is reviewed input; an applicable overall limitation requires a separate calculation. |
| 2026 cash gifts with the standard deduction | [Topic 506](https://www.irs.gov/taxtopics/tc506) | The separate deduction for eligible non-itemizers is not calculated. |

## The figures the estimate uses

The bundled reference snapshot is dated 2 September 2026. Check the exact source and tax year before changing a figure. Updating `data/tax-figures.json` is advanced maintenance of the reference dataset after checking the IRS source. It is separate from entering household facts in the Table editor; source watches never update these reference figures automatically.

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
| 2026 charitable-contribution floor and contribution limits | Not calculated. Enter charitable only as an already-reviewed allowable itemized deduction after applicable limits, including the 0.5% of AGI floor for 2026; recheck when AGI changes. | https://www.irs.gov/publications/p505 |
| 2026 overall limitation on itemized deductions | Not calculated. A 2026 estimate subject to this high-income limitation remains incomplete and requires a separate calculation. | https://www.irs.gov/publications/p505 |
| 2026 deduction for eligible cash gifts by non-itemizers | Not calculated. The charitable input is used only in the itemized route; eligible standard-deduction filers need a separate calculation. | https://www.irs.gov/taxtopics/tc506 |
| No tax on tips, deduction up to $25,000 (2025–2028) | Needs the qualified-tip amount from the W-2; enter it as a note for now. | irs.gov/newsroom/working-families-tax-cuts-tax-deductions-for-working-americans-and-seniors |
| No tax on overtime, deduction up to $12,500 ($25,000 joint), 2025–2028 | Needs the qualified-overtime amount from the W-2. | irs.gov/newsroom/working-families-tax-cuts-tax-deductions-for-working-americans-and-seniors |
| Car loan interest deduction up to $10,000 (2025–2028) | Needs the loan's interest statement and the vehicle's assembly location. | irs.gov/newsroom/working-families-tax-cuts-tax-deductions-for-working-americans-and-seniors |
| Long-term capital gains and qualified dividends at 0/15/20% | Qualified dividends and long-term gains are treated as ordinary income; preferential rates are not computed. This is not an upper bound on total tax. | 26 U.S.C. §1(h) |
| State income tax | Federal only. The profile's state is kept for your own record. |  |
| Alternative minimum tax, net investment income tax, self-employment tax | Outside this estimate. |  |

## Deadlines

<!-- data: data/tax-figures.json#deadlines -->
| What | When | Source |
| --- | --- | --- |
| 2025 return due (or extension request) | 2026-04-15 | irs.gov/filing/individuals/when-to-file |
| 2025 return due with extension | 2026-10-15 | irs.gov/filing/individuals/when-to-file |
| 2026 estimated tax, third payment | 2026-09-15 | Form 1040-ES |
| 2026 estimated tax, fourth payment | 2027-01-15 | Form 1040-ES |
| 2026 return due | 2027-04-15 | irs.gov/filing/individuals/when-to-file |
