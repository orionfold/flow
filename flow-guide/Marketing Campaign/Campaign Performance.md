---
title: Campaign Performance
tags: [marketing, dashboard, metrics]
---

# Marketing dashboard — Q3 2026

**Fictional example, as of 30 September 2026.** These sample figures show how to combine charts, tables and a decision in one document.

```chart
chartType: KPI Card
title: The quarter at a glance
data:
  - {metric: MQLs, value: 412, goal: 380}
  - {metric: Cost per MQL (USD), value: 104, goal: 100}
  - {metric: Pipeline created ($k), value: 1900, goal: 2100}
semantic_types: {metric: Category, value: Quantity, goal: Quantity}
encodings:
  metric: {field: metric}
  value: {field: value}
  goal: {field: goal}
```

MQL volume beat the goal; cost per MQL and pipeline created missed. Pipeline is an opportunity estimate, not recognised revenue.

## Traffic and conversion

```chart
chartType: Line Chart
title: Sessions recovered after the July dip
subtitle: Weekly organic sessions, thousands
data:
  - {week: W27, sessions: 18.2}
  - {week: W29, sessions: 14.1}
  - {week: W31, sessions: 15.8}
  - {week: W33, sessions: 19.4}
  - {week: W35, sessions: 22.7}
  - {week: W37, sessions: 24.1}
  - {week: W39, sessions: 25.3}
semantic_types: {week: Category, sessions: Quantity}
encodings:
  x: {field: week}
  y: {field: sessions}
```

The cause of the W29 dip is unknown. The sample shows a recovery after that week; it does not establish that a search update or the documentation rewrite caused it.

## Channel performance

| Channel | Spend | MQLs | Cost per MQL | Pipeline | Pipeline / spend |
| --- | ---: | ---: | ---: | ---: | ---: |
| Organic | $0 | 168 | $0 | $780k | — |
| Content | $12k | 94 | $128 | $410k | 34× |
| Paid search | $18k | 88 | $205 | $290k | 16× |
| Events | $9k | 41 | $220 | $310k | 34× |
| Social | $4k | 21 | $190 | $110k | 27× |
| **Total** | **$43k** | **412** | **$104** | **$1.9M** | **44×** |

Paid search has the lowest pipeline per dollar spent and takes the largest budget. Events has the highest cost per MQL. That is the reallocation question for Q4.

## Content performance

```chart
chartType: Bar Chart
title: Documentation had the largest attributed pipeline value
subtitle: Pipeline attributed, $k
highlight: Docs rewrite
data:
  - {piece: Docs rewrite, pipeline: 340}
  - {piece: Benchmark report, pipeline: 190}
  - {piece: Webinar series, pipeline: 140}
  - {piece: Case study, pipeline: 95}
  - {piece: Newsletter, pipeline: 62}
semantic_types: {piece: Category, pipeline: Quantity}
encodings:
  x: {field: piece}
  y: {field: pipeline}
```

## What this suggests for Q4

Run a bounded content test before changing the full budget. Attribution overlap, time lags and unpaid labour are not captured in these sample totals. Pipeline divided by spend is not realised ROI. The plan is in [[Campaign Strategy]].

The figures above are a static example of a prior-quarter review. [[Campaign Desk]] maintains the current calendar. Replace this snapshot with your own dated channel export; do not combine it with another sample company’s sales totals.
