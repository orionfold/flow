---
title: Marketing Dashboard — Q3
tags: [marketing, dashboard, metrics]
---

# Marketing dashboard — Q3 2026

As of 30 September. Everything here is measured, not modelled.

```chart
chartType: KPI Card
title: The quarter at a glance
data:
  - {metric: MQLs, value: 412, goal: 380}
  - {metric: Cost per MQL, value: 84, goal: 100}
  - {metric: Pipeline created, value: 1900, goal: 2100}
semantic_types: {metric: Category, value: Quantity, goal: Quantity}
encodings:
  metric: {field: metric}
  value: {field: value}
  goal: {field: goal}
```

Two of three ahead. Pipeline created missed, and it is the only one that matters
to [[Sales Report — Q3]].

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

The W29 dip was a search algorithm update. Recovery came from the docs rewrite,
not from anything the marketing team planned — worth being honest about.

## Channel performance

| Channel | Spend | MQLs | Cost per MQL | Pipeline | ROI |
| --- | ---: | ---: | ---: | ---: | ---: |
| Organic | $0 | 168 | $0 | $780k | — |
| Content | $12k | 94 | $128 | $410k | 34× |
| Paid search | $18k | 88 | $205 | $290k | 16× |
| Events | $9k | 41 | $220 | $310k | 34× |
| Social | $4k | 21 | $190 | $110k | 27× |
| **Total** | **$43k** | **412** | **$104** | **$1.9M** | **44×** |

Paid search is the worst performer on both cost and ROI and takes the largest
budget. That is the reallocation question for Q4.

## Content performance

```chart
chartType: Bar Chart
title: The docs rewrite outperformed every campaign
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

Move half the paid search budget to content, keep events flat, and treat
documentation as a marketing surface rather than a support cost. The plan is in
[[Content Strategy — Q4]].
