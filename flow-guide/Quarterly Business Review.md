---
title: Quarterly Business Review — Q3 2026
tags: [qbr, finance, board]
---

# Q3 2026 in one page

Revenue grew 41% on the quarter, and almost all of it came from six enterprise deals that were in the pipeline before July. The self-serve motion, which was supposed to carry the year, did not move. That is the finding, and the rest of this document is the evidence for it.

```chart
chartType: Bar Chart
title: Enterprise carried the quarter
subtitle: Revenue by segment, $k
source: Finance close, 6 October 2026
highlight: Q3
data:
  - {quarter: Q1, segment: Enterprise, revenue: 68}
  - {quarter: Q2, segment: Enterprise, revenue: 79}
  - {quarter: Q3, segment: Enterprise, revenue: 141}
  - {quarter: Q1, segment: Self-serve, revenue: 52}
  - {quarter: Q2, segment: Self-serve, revenue: 56}
  - {quarter: Q3, segment: Self-serve, revenue: 49}
semantic_types: {quarter: Category, revenue: Quantity, segment: Category}
encodings:
  x: {field: quarter}
  y: {field: revenue}
  color: {field: segment}
```

## What the numbers say

| Metric | Q2 | Q3 | Change |
| --- | ---: | ---: | ---: |
| Revenue | $135k | $190k | **+41%** |
| Enterprise ARR | $79k | $141k | +78% |
| Self-serve ARR | $56k | $49k | −13% |
| Net retention | 104% | 112% | +8pp |
| Gross margin | 71% | 74% | +3pp |
| Sales cycle (median) | 71 days | 54 days | −17 days |

Two of these deserve more than a row.

**Net retention at 112%** is the healthiest signal in the table. Existing customers expanded without being sold to, which is what [[Customer Interviews]] found when it asked why teams added seats: nobody mentioned a salesperson.

**Self-serve down 13%** is the one that should worry us. It is not churn — logo retention held at 94% — it is that new self-serve signups converted at less than half of Q2's rate. [[Market Landscape]] has the likely reason.

## The shape of the pipeline

```chart
chartType: Line Chart
title: Sales cycle compressed as deals got larger
subtitle: Median days from first call to signature
source: CRM export, 6 October 2026
data:
  - {month: Apr, days: 78}
  - {month: May, days: 74}
  - {month: Jun, days: 71}
  - {month: Jul, days: 66}
  - {month: Aug, days: 58}
  - {month: Sep, days: 54}
semantic_types: {month: Category, days: Quantity}
encodings:
  x: {field: month}
  y: {field: days}
```

Larger deals closing faster is unusual enough to be worth stating carefully. The plausible explanation is selection rather than skill: the six deals that closed were all referrals from existing customers, and a referred buyer arrives having already decided.[^referral]

[^referral]: Five of the six name an existing customer as their first contact with us. The sixth came from a conference talk. None came from paid acquisition.

## What we are doing about it

1. **Fund the referral motion deliberately.** It is producing our best deals by accident. See [[How We Decided]] for the argument and the approval.
2. **Stop spending on self-serve acquisition** until the conversion problem is understood. This is a pause, not a retreat.
3. **Hire one solutions engineer.** The enterprise deals are closing on demos that the founders are personally running, and that does not scale past Q4.

## What this cost

Producing this review — the analysis, the drafting, the checking — cost $3.09 in model spend. [[Cost of This Quarter]] breaks it down, because a number nobody can check is not evidence.

> The thing we should not do is declare the self-serve experiment failed on one quarter of data. It is one quarter, and it followed a pricing change we made in June.
