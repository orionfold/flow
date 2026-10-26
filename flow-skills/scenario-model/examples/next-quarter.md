# Worked example — Scenario Model

## Input

> We expect 40 new customers next quarter, though sales says it could be
> anywhere from 25 to 60. Each brings about $3,000 in the quarter. The
> support hire we are weighing costs $60,000 a quarter.

## Output

### Even the low case covers the support hire

- Low: 25 customers × $3,000 = $75,000.
- Base: 40 customers × $3,000 = $120,000.
- High: 60 customers × $3,000 = $180,000.

```chart
chartType: Bar Chart
title: Even the low case covers the $60,000 support hire
source: Sales' range and the revenue per customer
highlight: Base
data:
  - {case: Low, revenue: 75000}
  - {case: Base, revenue: 120000}
  - {case: High, revenue: 180000}
encodings:
  x: {field: case}
  y: {field: revenue}
```

```flowui
component: Form
title: Planning case · Next quarter
subtitle: Which case the hiring plan follows
fields:
  - label: Case
    bind: verdict
    type: choice
    options:
      - Low
      - Base
      - High
  - label: Reason
    bind: reason
  - label: Decided by
    bind: signer
decision: {label: Record decision, action: decide}
```
