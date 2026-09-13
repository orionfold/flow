---
title: Charts — Goals and Plans
tags: [charts-gallery, reference, fictional-example]
---
# Charts — Goals and Plans

[[Charts Gallery]] · Previous: [[Charts — Comparisons]] · Next: [[Charts — Time Series]]

**Separate the target from the plan that may reach it.**

> Every exhibit on this page uses fictional teaching data or an authored scenario. Source labels describe the example; they are not reports, measured Flow benchmarks or product guarantees.

| Form | Use it for |
| --- | --- |
| Bullet chart | Compare an actual value with its own target |
| KPI card | Give one important measure a clear value, unit and comparison |
| Gantt chart | Show authored start and finish dates, overlaps and handovers |

Use a target view for performance and a Gantt for planned time. Do not let a green target or a filled bar stand in for approval.

## The exhibits

### Bullet chart

Compare an actual value with its own target. Keep rows in the same unit on a shared axis; put dollars, percentages and days in separate exhibits.

Source: a table of metrics, each with an actual value and a target: the quarterly scorecard, where every row is a measure against its goal.

```chart
chartType: Bullet Chart
title: Three percentage targets met; net retention fell short
subtitle: Actual and target in percent; four separately defined measures
source: Fictional teaching sample — Board scorecard
data:
  - {metric: Activation (%), actual: 72, goal: 70}
  - {metric: Net retention (%), actual: 112, goal: 115}
  - {metric: Gross margin (%), actual: 81, goal: 78}
  - {metric: Support CSAT (%), actual: 94, goal: 92}
semantic_types: {metric: Category, actual: Quantity, goal: Quantity}
encodings:
  y: {field: metric}
  x: {field: actual}
  goal: {field: goal}
```

[[Charts Gallery]]

### KPI card

Give one important measure a clear value, unit and comparison. A card needs its period and denominator nearby; it should not replace the evidence behind the number.

Source: a single line or a one-row table naming a metric, its current value and its target: the one number the page is about.

```chart
chartType: KPI Card
title: Net revenue retention
subtitle: Trailing twelve months, against the 115% plan
source: Fictional teaching sample — Finance, July 2026
data:
  - {metric: Net revenue retention, value: 112, goal: 115}
semantic_types: {metric: Name, value: Percentage, goal: Percentage}
encodings:
  metric: {field: metric}
  value: {field: value}
  goal: {field: goal}
```

[[Charts Gallery]]

### Gantt chart

Show authored start and finish dates, overlaps and handovers. Bars represent the entered schedule; they do not prove work started or that a dependency is satisfied.

Source: a table of tasks with a start date, an end date and an owner or phase: a project plan or release schedule written as rows.

```chart
chartType: Gantt Chart
title: Private beta overlaps launch preparation
subtitle: Q4 release plan
source: Fictional teaching sample — Program management
data:
  - {task: Design freeze, start: 2026-09-01, end: 2026-09-12, phase: Design}
  - {task: Build, start: 2026-09-08, end: 2026-10-17, phase: Engineering}
  - {task: Private beta, start: 2026-10-06, end: 2026-11-28, phase: Beta}
  - {task: Docs and briefs, start: 2026-10-20, end: 2026-11-21, phase: Marketing}
  - {task: Launch prep, start: 2026-11-16, end: 2026-12-05, phase: Marketing}
  - {task: Launch, start: 2026-12-08, end: 2026-12-12, phase: Launch}
semantic_types: {task: Name, start: Date, end: Date, phase: Category}
encodings:
  y: {field: task}
  x: {field: start}
  x2: {field: end}
  color: {field: phase}
```

[[Charts Gallery]]

## Use a form with your own records

Copy the whole **Charts Gallery** folder and add that copy to Flow first. Open [[Gallery Data]] to practise with a table you can edit. [[Charts — Living Example]] shows the refresh path. These reference exhibits keep their own embedded examples; they do not change when the practice table changes.

For a new exhibit, open a suitable example in the chart editor or select your own source rows and use Visualize. Keep the units and source explanation with the result. Visualize uses your configured Agency route; inspect its proposal before applying. Authored Mermaid diagrams need deliberate text edits; they are not automatically maintained from the table.

[[Charts Gallery]] · Previous: [[Charts — Comparisons]] · Next: [[Charts — Time Series]]
