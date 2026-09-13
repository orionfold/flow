---
title: Charts — Time Series
tags: [charts-gallery, reference, fictional-example]
---
# Charts — Time Series

[[Charts Gallery]] · Previous: [[Charts — Goals and Plans]] · Next: [[Charts — Composition]]

**Read direction, timing and range before explaining them.**

> Every exhibit on this page uses fictional teaching data or an authored scenario. Source labels describe the example; they are not reports, measured Flow benchmarks or product guarantees.

| Form | Use it for |
| --- | --- |
| Line chart | Compare observations in time order |
| Area chart | Emphasize the amount of a volume or balance over time |
| Range area chart | Show a supplied lower and upper range |
| Sparkline | Place a compact trend beside a statement |
| Slope chart | Compare exactly two named periods for each item |
| Connected scatter plot | Follow one entity through time on two quantitative axes |
| Candlestick chart | Show an opening value, high, low and closing value for each period |

Match the form to the time question: a path, a balance, a range or two endpoints. Dates are part of the evidence.

## The exhibits

### Line chart

Compare observations in time order. A line joins the supplied points; sparse observations do not establish what happened between them.

Source: a table with a date column and one or more numeric series columns, or a long table of date, series, value: weekly actives, monthly revenue, daily latency.

```chart
chartType: Line Chart
title: Active documents rise across all three plans
subtitle: Weekly active documents by plan, thousands
source: Fictional teaching sample — Product analytics
highlight: Team
data:
  - {week: 2026-01-05, plan: Free, actives: 14.2}
  - {week: 2026-01-05, plan: Pro, actives: 6.1}
  - {week: 2026-01-05, plan: Team, actives: 3.8}
  - {week: 2026-02-02, plan: Free, actives: 15.0}
  - {week: 2026-02-02, plan: Pro, actives: 6.6}
  - {week: 2026-02-02, plan: Team, actives: 4.4}
  - {week: 2026-03-02, plan: Free, actives: 18.9}
  - {week: 2026-03-02, plan: Pro, actives: 8.2}
  - {week: 2026-03-02, plan: Team, actives: 6.9}
  - {week: 2026-04-06, plan: Free, actives: 24.6}
  - {week: 2026-04-06, plan: Pro, actives: 10.4}
  - {week: 2026-04-06, plan: Team, actives: 9.8}
  - {week: 2026-05-04, plan: Free, actives: 27.1}
  - {week: 2026-05-04, plan: Pro, actives: 11.9}
  - {week: 2026-05-04, plan: Team, actives: 12.7}
  - {week: 2026-06-01, plan: Free, actives: 28.3}
  - {week: 2026-06-01, plan: Pro, actives: 13.2}
  - {week: 2026-06-01, plan: Team, actives: 15.1}
  - {week: 2026-07-06, plan: Free, actives: 29.0}
  - {week: 2026-07-06, plan: Pro, actives: 14.6}
  - {week: 2026-07-06, plan: Team, actives: 17.9}
semantic_types: {week: Date, plan: Category, actives: Count}
encodings:
  x: {field: week}
  y: {field: actives}
  color: {field: plan}
```

[[Charts Gallery]]

### Area chart

Emphasize the amount of a volume or balance over time. Keep a meaningful zero; a cash balance alone cannot establish runway without a spending basis.

Source: a date column and one cumulative or volume measure, such as total storage, cumulative signups or cash balance, where the filled area reads as the amount.

```chart
chartType: Area Chart
title: Cash balance falls from 42.1M to 32.6M
subtitle: Month-end cash balance, $M
source: Fictional teaching sample — Treasury
data:
  - {month: 2025-08, cash: 42.1}
  - {month: 2025-09, cash: 41.0}
  - {month: 2025-10, cash: 39.8}
  - {month: 2025-11, cash: 38.9}
  - {month: 2025-12, cash: 37.5}
  - {month: 2026-01, cash: 36.6}
  - {month: 2026-02, cash: 35.9}
  - {month: 2026-03, cash: 34.8}
  - {month: 2026-04, cash: 34.4}
  - {month: 2026-05, cash: 33.7}
  - {month: 2026-06, cash: 33.0}
  - {month: 2026-07, cash: 32.6}
semantic_types: {month: YearMonth, cash: Amount}
encodings:
  x: {field: month}
  y: {field: cash}
```

[[Charts Gallery]]

### Range area chart

Show a supplied lower and upper range. Say whether it is a forecast interval, observed spread or scenario range; Flow does not infer its statistical meaning.

Source: a date column with a low and a high column, and optionally a central value: a forecast with its confidence band, a temperature range, a p10/p90 spread.

```chart
chartType: Range Area Chart
title: Forecast ranges narrow across six updates
subtitle: Illustrative low and high forecast bounds; new ARR, $k
source: Fictional teaching sample — Revenue operations
data:
  - {month: 2026-08, low: 520, high: 780}
  - {month: 2026-09, low: 548, high: 760}
  - {month: 2026-10, low: 571, high: 742}
  - {month: 2026-11, low: 596, high: 724}
  - {month: 2026-12, low: 612, high: 706}
  - {month: 2027-01, low: 629, high: 691}
semantic_types: {month: YearMonth, low: Amount, high: Amount}
encodings:
  x: {field: month}
  y: {field: low}
  y2: {field: high}
```

[[Charts Gallery]]

### Sparkline

Place a compact trend beside a statement. Keep the unit, period and scale context in the title or nearby text because the display is deliberately small.

Source: a short date-and-value table meant to sit beside a sentence, such as a week of latency or a month of signups, shown without axes as a glance.

```chart
chartType: Sparkline
title: p95 latency, last 14 days
source: Fictional teaching sample — Observability
data:
  - {day: 2026-08-06, ms: 412}
  - {day: 2026-08-07, ms: 398}
  - {day: 2026-08-08, ms: 405}
  - {day: 2026-08-09, ms: 371}
  - {day: 2026-08-10, ms: 366}
  - {day: 2026-08-11, ms: 512}
  - {day: 2026-08-12, ms: 488}
  - {day: 2026-08-13, ms: 344}
  - {day: 2026-08-14, ms: 339}
  - {day: 2026-08-15, ms: 341}
  - {day: 2026-08-16, ms: 328}
  - {day: 2026-08-17, ms: 330}
  - {day: 2026-08-18, ms: 317}
  - {day: 2026-08-19, ms: 312}
semantic_types: {day: Date, ms: Duration}
encodings:
  x: {field: day}
  y: {field: ms}
```

[[Charts Gallery]]

### Slope chart

Compare exactly two named periods for each item. The gap and direction matter; it cannot show the path or volatility between endpoints.

Source: a table with exactly two time points per item, such as before and after or this year and last, where the steepness of each line is the finding.

```chart
chartType: Slope Chart
title: Every region grew; APAC more than doubled
subtitle: Bookings FY25 → FY26, $M
source: Fictional teaching sample — Sales operations
highlight: APAC
data:
  - {year: FY25, region: North America, bookings: 21.0}
  - {year: FY26, region: North America, bookings: 23.4}
  - {year: FY25, region: EMEA, bookings: 14.6}
  - {year: FY26, region: EMEA, bookings: 21.9}
  - {year: FY25, region: APAC, bookings: 4.3}
  - {year: FY26, region: APAC, bookings: 9.7}
  - {year: FY25, region: LATAM, bookings: 2.8}
  - {year: FY26, region: LATAM, bookings: 3.9}
semantic_types: {year: Category, region: Region, bookings: Amount}
encodings:
  x: {field: year}
  y: {field: bookings}
  color: {field: region}
```

[[Charts Gallery]]

### Connected scatter plot

Follow one entity through time on two quantitative axes. Preserve chronological order and both units; the connecting path is a trajectory, not a regression fit.

Source: a table of period, x-measure and y-measure for one entity, such as price against volume by year or spend against growth by quarter, where the path shows the trajectory.

```chart
chartType: Connected Scatter Plot
title: Higher spending coincides with shorter payback
subtitle: Quarterly marketing spend, $M; CAC payback, months
source: Fictional teaching sample — Finance and growth
data:
  - {quarter: Q3 25, spend: 1.2, payback: 19}
  - {quarter: Q4 25, spend: 1.5, payback: 17}
  - {quarter: Q1 26, spend: 1.9, payback: 16}
  - {quarter: Q2 26, spend: 2.4, payback: 13}
  - {quarter: Q3 26, spend: 2.6, payback: 11}
semantic_types: {quarter: Category, spend: Amount, payback: Duration}
encodings:
  x: {field: spend}
  y: {field: payback}
  order: {field: quarter}
```

[[Charts Gallery]]

### Candlestick chart

Show an opening value, high, low and closing value for each period. Check the time zone, sampling window and units; it is not an investment recommendation.

Source: a table of date, open, high, low and close: market prices, but also any daily range with a start and an end, such as queue depth or token spend.

```chart
chartType: Candlestick Chart
title: A volatile week ended above where it began
subtitle: Daily open, high, low, close, $
source: Fictional teaching sample — Market data
data:
  - {day: 2026-08-10, open: 142.1, high: 147.8, low: 140.3, close: 146.2}
  - {day: 2026-08-11, open: 146.5, high: 149.0, low: 143.9, close: 144.1}
  - {day: 2026-08-12, open: 144.0, high: 145.2, low: 138.6, close: 139.4}
  - {day: 2026-08-13, open: 139.8, high: 146.7, low: 139.1, close: 145.9}
  - {day: 2026-08-14, open: 146.3, high: 151.4, low: 145.0, close: 150.7}
semantic_types: {day: Date, open: Price, high: Price, low: Price, close: Price}
encodings:
  x: {field: day}
  open: {field: open}
  high: {field: high}
  low: {field: low}
  close: {field: close}
```

[[Charts Gallery]]

## Use a form with your own records

Copy the whole **Charts Gallery** folder and add that copy to Flow first. Open [[Gallery Data]] to practise with a table you can edit. [[Charts — Living Example]] shows the refresh path. These reference exhibits keep their own embedded examples; they do not change when the practice table changes.

For a new exhibit, open a suitable example in the chart editor or select your own source rows and use Visualize. Keep the units and source explanation with the result. Visualize uses your configured Agency route; inspect its proposal before applying. Authored Mermaid diagrams need deliberate text edits; they are not automatically maintained from the table.

[[Charts Gallery]] · Previous: [[Charts — Goals and Plans]] · Next: [[Charts — Composition]]
