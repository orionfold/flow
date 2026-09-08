---
title: Revenue Dashboard — Q3 2026
tags: [dashboard, finance, metrics]
---

# Revenue, dense

Everything on this page is as of the 6 October close. It is meant to be scanned, not read.

```chart
chartType: KPI Card
title: Quarter at a glance
data:
  - {metric: Revenue, value: 190, goal: 175}
  - {metric: Net retention, value: 112, goal: 105}
  - {metric: Gross margin, value: 74, goal: 70}
semantic_types: {metric: Category, value: Quantity, goal: Quantity}
encodings:
  metric: {field: metric}
  value: {field: value}
  goal: {field: goal}
```

![The figures, before they became charts](assets/figures-desk.jpeg)

*Every number on this page traces to a row in the close.*

## Monthly revenue, with the mix underneath

```chart
chartType: Stacked Bar Chart
title: Monthly revenue by segment
subtitle: $k, recognised
source: Finance close, 6 October 2026
data:
  - {month: Jul, segment: Enterprise, amount: 38}
  - {month: Jul, segment: Self-serve, amount: 18}
  - {month: Aug, segment: Enterprise, amount: 46}
  - {month: Aug, segment: Self-serve, amount: 16}
  - {month: Sep, segment: Enterprise, amount: 57}
  - {month: Sep, segment: Self-serve, amount: 15}
semantic_types: {month: Category, amount: Quantity, segment: Category}
encodings:
  x: {field: month}
  y: {field: amount}
  color: {field: segment}
```

## Cohort retention

```chart
chartType: Heatmap
title: Revenue retention by signup cohort
subtitle: Percent of month-one revenue retained
data:
  - {cohort: Apr, month: M1, retained: 100}
  - {cohort: Apr, month: M2, retained: 96}
  - {cohort: Apr, month: M3, retained: 103}
  - {cohort: May, month: M1, retained: 100}
  - {cohort: May, month: M2, retained: 94}
  - {cohort: May, month: M3, retained: 99}
  - {cohort: Jun, month: M1, retained: 100}
  - {cohort: Jun, month: M2, retained: 88}
  - {cohort: Jun, month: M3, retained: 84}
semantic_types: {cohort: Category, month: Category, retained: Quantity}
encodings:
  x: {field: month}
  y: {field: cohort}
  color: {field: retained}
```

The June cohort is the first to fall away, and June is when the pricing change landed. That is correlation, and it is in [[How We Decided]] as an open question rather than a conclusion.

## The table the charts came from

| Month | Enterprise | Self-serve | Total | New logos |
| --- | ---: | ---: | ---: | ---: |
| July | $38k | $18k | $56k | 14 |
| August | $46k | $16k | $62k | 11 |
| September | $57k | $15k | $72k | 9 |
| **Quarter** | **$141k** | **$49k** | **$190k** | **34** |

## What this page cannot do, honestly

A real dashboard is a layout problem: panels sized against each other, a sidebar of filters, numbers that reflow into a grid. **Markdown has no layout**, so this page cannot be that, and pretending otherwise would be the wrong kind of demo.

What it can be is dense, current, and made of real constructs — charts that render from data you can edit in place, tables that carry the underlying numbers, and a measure narrow enough to read. The craft goes *inside* the constructs rather than into inventing new ones.
