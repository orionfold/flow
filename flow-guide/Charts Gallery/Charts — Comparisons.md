---
title: Charts — Comparisons
tags: [charts-gallery, reference, fictional-example]
---
# Charts — Comparisons

[[Charts Gallery]] · Previous: [[Charts — Living Example]] · Next: [[Charts — Goals and Plans]]

**Compare amounts without losing the labels.**

> Every exhibit on this page uses fictional teaching data or an authored scenario. Source labels describe the example; they are not reports, measured Flow benchmarks or product guarantees.

| Form | Use it for |
| --- | --- |
| Bar chart | Compare a modest set of amounts on one shared unit |
| Grouped bar chart | Compare the same categories under two or three conditions |
| Lollipop chart | Keep a longer category list light while preserving individual amounts |
| Bar table | Read exact values alongside their relative size |
| Pyramid chart | Compare two cohorts across the same bands |
| Ranged dot plot | Compare two observations for each item with less ink than paired bars |

Start with a bar chart when exact category comparison is the task. A paired view earns its place when both conditions matter.

## The exhibits

### Bar chart

Compare a modest set of amounts on one shared unit. Start at zero when length carries the comparison; use a horizontal orientation for long names.

Source: a two-column table, one category column and one number column, with up to a dozen rows. Name one row in `highlight` and it takes the accent while the rest recede.

```chart
chartType: Bar Chart
title: Q3 is the strongest quarter in this sample
subtitle: New ARR by quarter, $k
source: Fictional teaching sample — Finance close, FY26
highlight: Q3 FY26
data:
  - {quarter: Q4 FY25, arr: 410}
  - {quarter: Q1 FY26, arr: 455}
  - {quarter: Q2 FY26, arr: 498}
  - {quarter: Q3 FY26, arr: 687}
  - {quarter: Q4 FY26, arr: 602}
semantic_types: {quarter: Category, arr: Amount}
encodings:
  x: {field: quarter}
  y: {field: arr}
```

[[Charts Gallery]]

### Grouped bar chart

Compare the same categories under two or three conditions. Keep units and group order consistent; many groups are easier to read in separate charts.

Source: a table with a category column, a group column and a value column: the same categories measured under two or three conditions, such as regions across years.

```chart
chartType: Grouped Bar Chart
title: EMEA closed the gap with North America in FY26
subtitle: Bookings by region and fiscal year, $M
source: Fictional teaching sample — Sales operations
data:
  - {region: North America, year: FY24, bookings: 18.2}
  - {region: North America, year: FY25, bookings: 21.0}
  - {region: North America, year: FY26, bookings: 23.4}
  - {region: EMEA, year: FY24, bookings: 9.1}
  - {region: EMEA, year: FY25, bookings: 14.6}
  - {region: EMEA, year: FY26, bookings: 21.9}
  - {region: APAC, year: FY24, bookings: 4.3}
  - {region: APAC, year: FY25, bookings: 6.8}
  - {region: APAC, year: FY26, bookings: 9.7}
semantic_types: {region: Region, year: Category, bookings: Amount}
encodings:
  x: {field: region}
  y: {field: bookings}
  group: {field: year}
```

[[Charts Gallery]]

### Lollipop chart

Keep a longer category list light while preserving individual amounts. Order the rows intentionally; a decorative stem is not a confidence interval.

Source: the same two-column table as a bar chart, but with many rows or long labels: the thin stem keeps a ranked list of twenty items legible.

```chart
chartType: Lollipop Chart
title: Onboarding and search are the two most requested improvements
subtitle: Feature requests logged in Q3, count
source: Fictional teaching sample — Support desk export
highlight: Guided onboarding
data:
  - {request: Guided onboarding, count: 214}
  - {request: Faster search, count: 187}
  - {request: Offline mode, count: 142}
  - {request: Shared folders, count: 121}
  - {request: Dark mode for print, count: 96}
  - {request: Keyboard shortcuts, count: 88}
  - {request: Export to PDF, count: 74}
  - {request: Calendar sync, count: 51}
  - {request: Audio notes, count: 43}
  - {request: Custom themes, count: 29}
semantic_types: {request: Category, count: Count}
encodings:
  x: {field: request}
  y: {field: count}
```

[[Charts Gallery]]

### Bar table

Read exact values alongside their relative size. Show the measurement basis; a score without its rubric is not a recommendation.

Source: a ranked table of names and one number, when you want the numbers read as a list as well as compared: a leaderboard, a vendor shortlist, a benchmark.

```chart
chartType: Bar Table
title: Compare fictional review scores across six options
subtitle: Illustrative scorecard, 0–100; no model benchmark or cost claim
source: Fictional teaching sample — Runtime evaluation, August 2026
data:
  - {model: Option A, score: 91}
  - {model: Option B, score: 87}
  - {model: Option C, score: 84}
  - {model: Option D, score: 79}
  - {model: Option E, score: 73}
  - {model: Option F, score: 66}
semantic_types: {model: Name, score: Score}
encodings:
  y: {field: model}
  x: {field: score}
```

[[Charts Gallery]]

### Pyramid chart

Compare two cohorts across the same bands. Check whether raw counts or within-cohort percentages answer the question; unequal cohort sizes can dominate the picture.

Source: a table with an age band or tier column, a two-value side column and a count: a population pyramid, or any two cohorts mirrored around a centre.

```chart
chartType: Pyramid Chart
title: The customer base skews younger than the buyer base
subtitle: Active users and paying admins by age band, thousands
source: Fictional teaching sample — Product analytics, July 2026
data:
  - {band: 18–24, side: Users, people: 48}
  - {band: 18–24, side: Admins, people: 4}
  - {band: 25–34, side: Users, people: 112}
  - {band: 25–34, side: Admins, people: 21}
  - {band: 35–44, side: Users, people: 96}
  - {band: 35–44, side: Admins, people: 38}
  - {band: 45–54, side: Users, people: 61}
  - {band: 45–54, side: Admins, people: 29}
  - {band: 55–64, side: Users, people: 27}
  - {band: 55–64, side: Admins, people: 12}
  - {band: 65+, side: Users, people: 9}
  - {band: 65+, side: Admins, people: 3}
semantic_types: {band: Category, side: Category, people: Count}
encodings:
  y: {field: band}
  x: {field: people}
  color: {field: side}
```

[[Charts Gallery]]

### Ranged dot plot

Compare two observations for each item with less ink than paired bars. Name both endpoints; this before/after layout does not establish what caused a change.

Source: a table with a category, a condition and a numeric value, with two rows per category. The before and after values appear as two dots joined by a line.

```chart
chartType: Ranged Dot Plot
title: Every region has a lower after-period median
subtitle: Median minutes to first document, before and after
source: Fictional teaching sample — Product analytics
data:
  - {region: North America, when: Before, minutes: 18}
  - {region: North America, when: After, minutes: 7}
  - {region: EMEA, when: Before, minutes: 21}
  - {region: EMEA, when: After, minutes: 9}
  - {region: APAC, when: Before, minutes: 26}
  - {region: APAC, when: After, minutes: 11}
  - {region: LATAM, when: Before, minutes: 24}
  - {region: LATAM, when: After, minutes: 12}
semantic_types: {region: Region, when: Category, minutes: Duration}
encodings:
  y: {field: region}
  x: {field: minutes}
  color: {field: when}
```

[[Charts Gallery]]

## Use a form with your own records

Copy the whole **Charts Gallery** folder and add that copy to Flow first. Open [[Gallery Data]] to practise with a table you can edit. [[Charts — Living Example]] shows the refresh path. These reference exhibits keep their own embedded examples; they do not change when the practice table changes.

For a new exhibit, open a suitable example in the chart editor or select your own source rows and use Visualize. Keep the units and source explanation with the result. Visualize uses your configured Agency route; inspect its proposal before applying. Authored Mermaid diagrams need deliberate text edits; they are not automatically maintained from the table.

[[Charts Gallery]] · Previous: [[Charts — Living Example]] · Next: [[Charts — Goals and Plans]]
