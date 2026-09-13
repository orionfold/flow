---
title: Charts — Patterns
tags: [charts-gallery, reference, fictional-example]
---
# Charts — Patterns

[[Charts Gallery]] · Previous: [[Charts — Distributions]] · Next: [[Diagrams — Processes]]

**Use position and colour to find a pattern, then check its numbers.**

> Every exhibit on this page uses fictional teaching data or an authored scenario. Source labels describe the example; they are not reports, measured Flow benchmarks or product guarantees.

| Form | Use it for |
| --- | --- |
| Heatmap | Inspect a matrix of two categories and a numeric measure |
| Calendar heatmap | Read daily rhythm across weeks and months |
| Bump chart | Track rank changes across periods |
| Radar chart | Compare a few profiles on shared criteria |

A pattern is a prompt to investigate. Colour, rank and an authored score need a stated interpretation.

## The exhibits

### Heatmap

Inspect a matrix of two categories and a numeric measure. Use one explained colour scale, distinguish missing from zero and keep the scale comparable across panels.

Source: a table with two category columns and a value, such as hour by weekday, feature by segment or team by month, where colour carries the number.

```chart
chartType: Heatmap
title: Tuesday and Wednesday mornings are the busiest hours
subtitle: Average concurrent sessions by weekday and hour
source: Fictional teaching sample — Product analytics
data:
  - {weekday: Mon, hour: "08", sessions: 210}
  - {weekday: Mon, hour: "10", sessions: 480}
  - {weekday: Mon, hour: "12", sessions: 390}
  - {weekday: Mon, hour: "14", sessions: 450}
  - {weekday: Mon, hour: "16", sessions: 320}
  - {weekday: Tue, hour: "08", sessions: 260}
  - {weekday: Tue, hour: "10", sessions: 610}
  - {weekday: Tue, hour: "12", sessions: 420}
  - {weekday: Tue, hour: "14", sessions: 530}
  - {weekday: Tue, hour: "16", sessions: 340}
  - {weekday: Wed, hour: "08", sessions: 250}
  - {weekday: Wed, hour: "10", sessions: 640}
  - {weekday: Wed, hour: "12", sessions: 410}
  - {weekday: Wed, hour: "14", sessions: 560}
  - {weekday: Wed, hour: "16", sessions: 360}
  - {weekday: Thu, hour: "08", sessions: 230}
  - {weekday: Thu, hour: "10", sessions: 540}
  - {weekday: Thu, hour: "12", sessions: 400}
  - {weekday: Thu, hour: "14", sessions: 470}
  - {weekday: Thu, hour: "16", sessions: 300}
  - {weekday: Fri, hour: "08", sessions: 180}
  - {weekday: Fri, hour: "10", sessions: 410}
  - {weekday: Fri, hour: "12", sessions: 330}
  - {weekday: Fri, hour: "14", sessions: 290}
  - {weekday: Fri, hour: "16", sessions: 150}
semantic_types: {weekday: Day, hour: Category, sessions: Count}
encodings:
  x: {field: hour}
  y: {field: weekday}
  color: {field: sessions}
```

[[Charts Gallery]]

### Calendar heatmap

Read daily rhythm across weeks and months. Missing days need explicit treatment; a quiet day is not necessarily a zero or a day when a system was available.

Source: a long table of date and count, such as commits, dictation minutes or support tickets per day, over months, when the weekly rhythm matters as much as the totals.

```chart
chartType: Calendar Heatmap
title: Writing happens on weekdays; weekends are near-silent
subtitle: Words dictated per day, June–August 2026
source: Fictional teaching sample — Fictional receipt-shaped sample
data:
  - {day: 2026-06-01, words: 1240}
  - {day: 2026-06-02, words: 980}
  - {day: 2026-06-03, words: 1510}
  - {day: 2026-06-04, words: 1320}
  - {day: 2026-06-05, words: 760}
  - {day: 2026-06-06, words: 120}
  - {day: 2026-06-07, words: 0}
  - {day: 2026-06-08, words: 1410}
  - {day: 2026-06-09, words: 1680}
  - {day: 2026-06-10, words: 1290}
  - {day: 2026-06-11, words: 1750}
  - {day: 2026-06-12, words: 900}
  - {day: 2026-06-13, words: 210}
  - {day: 2026-06-14, words: 60}
  - {day: 2026-06-15, words: 1330}
  - {day: 2026-06-16, words: 1490}
  - {day: 2026-06-17, words: 1620}
  - {day: 2026-06-18, words: 1380}
  - {day: 2026-06-19, words: 810}
  - {day: 2026-06-20, words: 0}
  - {day: 2026-06-21, words: 90}
  - {day: 2026-06-22, words: 1560}
  - {day: 2026-06-23, words: 1720}
  - {day: 2026-06-24, words: 1440}
  - {day: 2026-06-25, words: 1910}
  - {day: 2026-06-26, words: 1020}
  - {day: 2026-06-27, words: 140}
  - {day: 2026-06-28, words: 0}
  - {day: 2026-06-29, words: 1380}
  - {day: 2026-06-30, words: 1650}
  - {day: 2026-07-01, words: 1470}
  - {day: 2026-07-02, words: 1590}
  - {day: 2026-07-03, words: 640}
  - {day: 2026-07-04, words: 0}
  - {day: 2026-07-05, words: 0}
  - {day: 2026-07-06, words: 1720}
  - {day: 2026-07-07, words: 1830}
  - {day: 2026-07-08, words: 1510}
  - {day: 2026-07-09, words: 1960}
  - {day: 2026-07-10, words: 1100}
  - {day: 2026-07-11, words: 180}
  - {day: 2026-07-12, words: 40}
  - {day: 2026-07-13, words: 1620}
  - {day: 2026-07-14, words: 1740}
  - {day: 2026-07-15, words: 1580}
  - {day: 2026-07-16, words: 2010}
  - {day: 2026-07-17, words: 1150}
  - {day: 2026-07-18, words: 220}
  - {day: 2026-07-19, words: 0}
  - {day: 2026-07-20, words: 1690}
  - {day: 2026-07-21, words: 1880}
  - {day: 2026-07-22, words: 1720}
  - {day: 2026-07-23, words: 2140}
  - {day: 2026-07-24, words: 1230}
  - {day: 2026-07-25, words: 260}
  - {day: 2026-07-26, words: 0}
  - {day: 2026-07-27, words: 1750}
  - {day: 2026-07-28, words: 1920}
  - {day: 2026-07-29, words: 1810}
  - {day: 2026-07-30, words: 2230}
  - {day: 2026-07-31, words: 1290}
  - {day: 2026-08-01, words: 310}
  - {day: 2026-08-02, words: 0}
  - {day: 2026-08-03, words: 1840}
  - {day: 2026-08-04, words: 2010}
  - {day: 2026-08-05, words: 1930}
  - {day: 2026-08-06, words: 2380}
  - {day: 2026-08-07, words: 1410}
  - {day: 2026-08-08, words: 280}
  - {day: 2026-08-09, words: 0}
  - {day: 2026-08-10, words: 1960}
  - {day: 2026-08-11, words: 2120}
  - {day: 2026-08-12, words: 2040}
  - {day: 2026-08-13, words: 2460}
  - {day: 2026-08-14, words: 1520}
  - {day: 2026-08-15, words: 330}
  - {day: 2026-08-16, words: 0}
  - {day: 2026-08-17, words: 2080}
  - {day: 2026-08-18, words: 2210}
  - {day: 2026-08-19, words: 2150}
semantic_types: {day: Date, words: Count}
encodings:
  x: {field: day}
  color: {field: words}
```

[[Charts Gallery]]

### Bump chart

Track rank changes across periods. Define the ranking method and ties; moving from second to first says nothing about the size of the underlying gap.

Source: a table of period, competitor and rank: the league table at each point in time, when the story is who passed whom.

```chart
chartType: Bump Chart
title: Cedar moves from fifth to first across four periods
subtitle: Fictional product ranks by quarter; no analyst survey
source: Fictional teaching sample — Authored ranking example
highlight: Cedar
data:
  - {quarter: Q3 25, product: Alder, rank: 1}
  - {quarter: Q3 25, product: Birch, rank: 2}
  - {quarter: Q3 25, product: Elm, rank: 3}
  - {quarter: Q3 25, product: Hazel, rank: 4}
  - {quarter: Q3 25, product: Cedar, rank: 5}
  - {quarter: Q4 25, product: Alder, rank: 1}
  - {quarter: Q4 25, product: Birch, rank: 2}
  - {quarter: Q4 25, product: Cedar, rank: 3}
  - {quarter: Q4 25, product: Elm, rank: 4}
  - {quarter: Q4 25, product: Hazel, rank: 5}
  - {quarter: Q1 26, product: Alder, rank: 1}
  - {quarter: Q1 26, product: Cedar, rank: 2}
  - {quarter: Q1 26, product: Birch, rank: 3}
  - {quarter: Q1 26, product: Elm, rank: 4}
  - {quarter: Q1 26, product: Hazel, rank: 5}
  - {quarter: Q2 26, product: Cedar, rank: 1}
  - {quarter: Q2 26, product: Alder, rank: 2}
  - {quarter: Q2 26, product: Birch, rank: 3}
  - {quarter: Q2 26, product: Elm, rank: 4}
  - {quarter: Q2 26, product: Hazel, rank: 5}
semantic_types: {quarter: Category, product: Name, rank: Rank}
encodings:
  x: {field: quarter}
  y: {field: rank}
  color: {field: product}
```

[[Charts Gallery]]

### Radar chart

Compare a few profiles on shared criteria. Define each score and direction, use comparable scales and inspect the table; polygon area is not a defensible overall score.

Source: a table of criteria, option and score, such as a vendor evaluation or a skills matrix, with two or three options scored on five to eight axes.

```chart
chartType: Radar Chart
title: The local runtime wins on privacy and cost, trails on reasoning
subtitle: Evaluation scores, 1–10
source: Fictional teaching sample — Runtime evaluation, August 2026
data:
  - {criterion: Quality, option: Local runtime, score: 8}
  - {criterion: Speed, option: Local runtime, score: 7}
  - {criterion: Privacy, option: Local runtime, score: 10}
  - {criterion: Cost, option: Local runtime, score: 10}
  - {criterion: Reasoning, option: Local runtime, score: 6}
  - {criterion: Context length, option: Local runtime, score: 6}
  - {criterion: Quality, option: Hosted frontier, score: 9}
  - {criterion: Speed, option: Hosted frontier, score: 8}
  - {criterion: Privacy, option: Hosted frontier, score: 4}
  - {criterion: Cost, option: Hosted frontier, score: 3}
  - {criterion: Reasoning, option: Hosted frontier, score: 10}
  - {criterion: Context length, option: Hosted frontier, score: 9}
semantic_types: {criterion: Category, option: Category, score: Score}
encodings:
  x: {field: criterion}
  y: {field: score}
  color: {field: option}
```

[[Charts Gallery]]

## Use a form with your own records

Copy the whole **Charts Gallery** folder and add that copy to Flow first. Open [[Gallery Data]] to practise with a table you can edit. [[Charts — Living Example]] shows the refresh path. These reference exhibits keep their own embedded examples; they do not change when the practice table changes.

For a new exhibit, open a suitable example in the chart editor or select your own source rows and use Visualize. Keep the units and source explanation with the result. Visualize uses your configured Agency route; inspect its proposal before applying. Authored Mermaid diagrams need deliberate text edits; they are not automatically maintained from the table.

[[Charts Gallery]] · Previous: [[Charts — Distributions]] · Next: [[Diagrams — Processes]]
