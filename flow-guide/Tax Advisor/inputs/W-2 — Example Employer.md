---
title: W-2 — Example Employer
tags: [tax, w-2, input]
---
# W-2 — Example Employer

**Illustrative business record.**

## Record

| form | tax_year | employer | employee | box1_wages | box2_federal_withheld | box3_social_security_wages | box4_social_security_withheld | box5_medicare_wages | box6_medicare_withheld | box12_d_401k | box12_w_hsa_employer | box16_state_wages | box17_state_withheld |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| W-2 | 2025 | Example Employer Inc. | Taxpayer | 148600 | 21940 | 158800 | 9846 | 165200 | 2395 | 16400 | 0 | 148600 | 8730 |

## About these inputs

Choose **View ▸ Edit Table** to edit this record, then save the document. Keep one record in this table; copy the whole document when adding another person or form.

One file per Form W-2. The Record table carries the boxes the estimate reads; the table below says which is which. Copy this file for each employer, name it for them, and type the values from the form. The example numbers are made up.

| Column | Box on the form | What it is |
| --- | --- | --- |
| `box1_wages` | 1 | Wages, tips, other compensation. Already net of 401(k) and payroll HSA. |
| `box2_federal_withheld` | 2 | Federal income tax withheld. Compared with the estimated tax to find the refund or balance due. |
| `box3_social_security_wages` | 3 | Social Security wages. |
| `box4_social_security_withheld` | 4 | Social Security tax withheld. |
| `box5_medicare_wages` | 5 | Medicare wages and tips. |
| `box6_medicare_withheld` | 6 | Medicare tax withheld. |
| `box12_d_401k` | 12, code D | Elective deferrals to a 401(k). Taxpayer-labelled forms count against the taxpayer contribution cap; spouse income remains part of the joint estimate. |
| `box12_w_hsa_employer` | 12, code W | HSA contributions through the employer, yours and theirs. Counted against the HSA limit. |
| `box16_state_wages` | 16 | State wages. Kept for your record. |
| `box17_state_withheld` | 17 | State income tax withheld. Kept for your record. |

A 1099 does not go here. Enter interest, dividends and gains in the **Settings** table of [[Tax Profile]].

Set `tax_year` explicitly. Use `Taxpayer` in the `employee` cell for the owner of the contribution amounts shown and `Spouse` for the other filer. Missing or other-year forms must not be treated as matching-year income. The supplied HSA example assumes no spouse HSA contributions; review shared-limit allocation separately if both spouses contribute.

Return to [[Tax Advisor]] to run its saved Jobs and review the refreshed result.
