---
title: W-2 — Example Employer
tags: [tax, w-2, input]
form: W-2
tax_year: 2025
employer: Example Employer Inc.
employee: Taxpayer
box1_wages: 148600
box2_federal_withheld: 21940
box3_social_security_wages: 158800
box4_social_security_withheld: 9846
box5_medicare_wages: 165200
box6_medicare_withheld: 2395
box12_d_401k: 16400
box12_w_hsa_employer: 0
box16_state_wages: 148600
box17_state_withheld: 8730
---
# W-2 — Example Employer

One file per Form W-2. The front matter carries the boxes the estimate reads;
the table below says which is which. Copy this file for each employer, name
it for them, and type the values from the form. The example numbers are made
up.

| Front matter key | Box on the form | What it is |
| --- | --- | --- |
| `box1_wages` | 1 | Wages, tips, other compensation. Already net of 401(k) and payroll HSA. |
| `box2_federal_withheld` | 2 | Federal income tax withheld. Compared with the estimated tax to find the refund or balance due. |
| `box3_social_security_wages` | 3 | Social Security wages. |
| `box4_social_security_withheld` | 4 | Social Security tax withheld. |
| `box5_medicare_wages` | 5 | Medicare wages and tips. |
| `box6_medicare_withheld` | 6 | Medicare tax withheld. |
| `box12_d_401k` | 12, code D | Elective deferrals to a 401(k). Compared with the year's limit to show headroom. |
| `box12_w_hsa_employer` | 12, code W | HSA contributions through the employer, yours and theirs. Counted against the HSA limit. |
| `box16_state_wages` | 16 | State wages. Kept for your record. |
| `box17_state_withheld` | 17 | State income tax withheld. Kept for your record. |

A 1099 does not go here. Put interest, dividends and gains in the front
matter of [[Tax Profile]].
