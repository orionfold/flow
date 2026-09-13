---
title: Revenue Detail
tags: ["business-review", "example"]
---
# Revenue Detail

**Fictional FY2026 close · USD millions unless stated**

## The quarter totals reconcile to $19.2M

<!-- data: data/review-*.json#quarters -->
| Quarter | Revenue m | Gross margin pct | Customers | Operating income m |
| --- | --- | --- | --- | --- |
| Q1 | 3.9 | 79 | 404 | -0.4 |
| Q2 | 4.4 | 80 | 419 | -0.2 |
| Q3 | 5.2 | 82 | 433 | 0.3 |
| Q4 | 5.7 | 83 | 447 | 0.7 |

```chart data: data/review-*.json#quarters
chartType: Area Chart
title: Operating profit turned positive in Q3
subtitle: USD millions · quarterly operating profit or loss
source: Fictional bundled example; replace with your own records
data:
  - {series: "Revenue", quarter: "Q1", revenue_m: 3.9, gross_margin_pct: 79, customers: 404, operating_income_m: -0.4}
  - {series: "Revenue", quarter: "Q2", revenue_m: 4.4, gross_margin_pct: 80, customers: 419, operating_income_m: -0.2}
  - {series: "Revenue", quarter: "Q3", revenue_m: 5.2, gross_margin_pct: 82, customers: 433, operating_income_m: 0.3}
  - {series: "Revenue", quarter: "Q4", revenue_m: 5.7, gross_margin_pct: 83, customers: 447, operating_income_m: 0.7}
semantic_types:
  quarter: Category
  operating_income_m: Amount
encodings:
  x:
    field: quarter
  y:
    field: operating_income_m
```

## Definitions that prevent false comparisons

| Metric | Basis |
| --- | --- |
| Revenue | Recognised in the period; not ARR or bookings |
| Gross margin | Gross profit / revenue; weight quarter margins by quarter revenue |
| Operating income | After operating expenses, before financing and income tax |
| Customer count | Period-end count, not customers added during the quarter |

Source: [[Quarterly Close]]. No cash-flow conclusion follows from operating profit alone; working capital and financing are absent from this sample.
