---
title: Charts — Distributions
tags: [charts-gallery, reference, fictional-example]
---
# Charts — Distributions

[[Charts Gallery]] · Previous: [[Charts — Composition]] · Next: [[Charts — Patterns]]

**Keep variation visible instead of replacing it with one average.**

> Every exhibit on this page uses fictional teaching data or an authored scenario. Source labels describe the example; they are not reports, measured Flow benchmarks or product guarantees.

| Form | Use it for |
| --- | --- |
| Scatter plot | Look for a relationship between two measures on the same rows |
| Regression | Summarize the fitted relationship between two numeric measures |
| Histogram | Inspect the distribution of one measure |
| Density plot | Compare smoothed distribution shapes |
| ECDF plot | Ask what share of observations is at or below a threshold |
| Boxplot | Compare medians, quartiles and flagged outliers across groups |
| Violin plot | Compare the shape of distributions, including possible multiple peaks |
| Strip plot | Show every observation in a modest sample |

Choose the question before the summary: how spread out, what share under a limit, or whether two measures move together.

## The exhibits

### Scatter plot

Look for a relationship between two measures on the same rows. Label both units and investigate outliers; association does not establish cause.

Source: a table with two numeric columns per row, and optionally a category and a size: accounts by seats and spend, models by latency and quality.

```chart
chartType: Scatter Plot
title: Accounts differ in seats and annual spend
subtitle: Accounts by seats and annual spend, $k
source: Fictional teaching sample — CRM export, July 2026
data:
  - {account: Harbor Labs, seats: 12, spend: 9.6, segment: SMB}
  - {account: Meridian Retail, seats: 240, spend: 312, segment: Enterprise}
  - {account: Larkspur Robotics, seats: 38, spend: 41, segment: Mid-market}
  - {account: Quill & Co, seats: 8, spend: 5.1, segment: SMB}
  - {account: Northwind Health, seats: 410, spend: 598, segment: Enterprise}
  - {account: Fennel Studio, seats: 21, spend: 18, segment: SMB}
  - {account: Atlas Freight, seats: 96, spend: 121, segment: Mid-market}
  - {account: Bluefin Capital, seats: 64, spend: 88, segment: Mid-market}
  - {account: Orchard Schools, seats: 150, spend: 132, segment: Enterprise}
  - {account: Tidewater Energy, seats: 330, spend: 470, segment: Enterprise}
  - {account: Pinecone Press, seats: 15, spend: 12, segment: SMB}
  - {account: Cobalt Games, seats: 52, spend: 61, segment: Mid-market}
semantic_types: {account: Name, seats: Count, spend: Amount, segment: Category}
encodings:
  x: {field: seats}
  y: {field: spend}
  color: {field: segment}
```

[[Charts Gallery]]

### Regression

Summarize the fitted relationship between two numeric measures. Keep the points visible and avoid causal language or predictions beyond the observed range.

Source: the same two numeric columns as a scatter, when you want the fitted trend drawn through them: ad spend against signups, effort against score.

```chart
chartType: Regression
title: More visits coincide with more qualified leads
subtitle: Field visits vs. qualified leads, by rep, H1 2026
source: Fictional teaching sample — Sales operations
data:
  - {rep: A, visits: 4, leads: 11}
  - {rep: B, visits: 7, leads: 22}
  - {rep: C, visits: 9, leads: 25}
  - {rep: D, visits: 12, leads: 38}
  - {rep: E, visits: 14, leads: 40}
  - {rep: F, visits: 16, leads: 51}
  - {rep: G, visits: 19, leads: 55}
  - {rep: H, visits: 22, leads: 69}
  - {rep: I, visits: 25, leads: 74}
  - {rep: J, visits: 28, leads: 88}
semantic_types: {rep: Name, visits: Count, leads: Count}
encodings:
  x: {field: visits}
  y: {field: leads}
```

[[Charts Gallery]]

### Histogram

Inspect the distribution of one measure. Bin choices change the visible shape; state the sample size and unit and do not treat an empty bin as missing data.

Source: a single numeric column with many rows, such as response times, deal sizes or document lengths, which the chart bins for you.

```chart
chartType: Histogram
title: Most sample runs finish under ten seconds
subtitle: Fictional run duration, seconds; 30 observations
source: Fictional teaching sample — Fictional receipt-shaped sample
data:
  - {seconds: 3.1}
  - {seconds: 4.2}
  - {seconds: 4.8}
  - {seconds: 5.0}
  - {seconds: 5.3}
  - {seconds: 5.9}
  - {seconds: 6.1}
  - {seconds: 6.4}
  - {seconds: 6.6}
  - {seconds: 6.9}
  - {seconds: 7.2}
  - {seconds: 7.4}
  - {seconds: 7.7}
  - {seconds: 7.9}
  - {seconds: 8.1}
  - {seconds: 8.3}
  - {seconds: 8.6}
  - {seconds: 8.8}
  - {seconds: 9.0}
  - {seconds: 9.4}
  - {seconds: 9.7}
  - {seconds: 10.2}
  - {seconds: 10.8}
  - {seconds: 11.5}
  - {seconds: 12.4}
  - {seconds: 13.9}
  - {seconds: 15.2}
  - {seconds: 17.8}
  - {seconds: 21.3}
  - {seconds: 28.6}
semantic_types: {seconds: Duration}
encodings:
  x: {field: seconds}
```

[[Charts Gallery]]

### Density plot

Compare smoothed distribution shapes. Smoothing and small samples can create or hide peaks; check individual observations before naming distinct populations.

Source: one numeric column, optionally with a group column: the same data as a histogram, smoothed, when two groups need overlaying.

```chart
chartType: Density Plot
title: Local runs are tighter and faster than hosted runs
subtitle: Run duration by provider, seconds
source: Fictional teaching sample — Fictional receipt-shaped sample
data:
  - {provider: Local, seconds: 3.2}
  - {provider: Local, seconds: 4.1}
  - {provider: Local, seconds: 4.6}
  - {provider: Local, seconds: 5.0}
  - {provider: Local, seconds: 5.4}
  - {provider: Local, seconds: 5.8}
  - {provider: Local, seconds: 6.1}
  - {provider: Local, seconds: 6.5}
  - {provider: Local, seconds: 7.0}
  - {provider: Local, seconds: 7.8}
  - {provider: Local, seconds: 9.1}
  - {provider: Hosted, seconds: 4.9}
  - {provider: Hosted, seconds: 6.2}
  - {provider: Hosted, seconds: 7.4}
  - {provider: Hosted, seconds: 8.8}
  - {provider: Hosted, seconds: 9.6}
  - {provider: Hosted, seconds: 10.9}
  - {provider: Hosted, seconds: 12.3}
  - {provider: Hosted, seconds: 14.0}
  - {provider: Hosted, seconds: 16.7}
  - {provider: Hosted, seconds: 19.5}
  - {provider: Hosted, seconds: 24.1}
semantic_types: {provider: Category, seconds: Duration}
encodings:
  x: {field: seconds}
  color: {field: provider}
```

[[Charts Gallery]]

### ECDF plot

Ask what share of observations is at or below a threshold. State whether equality counts, name the sample size and remember that this is a sample proportion.

Source: one numeric column, optionally grouped: when the question is "what share finished within N seconds", read straight off the curve.

```chart
chartType: ECDF Plot
title: Ten of eleven local sample runs finish within eight seconds
subtitle: Cumulative share of runs by duration, seconds
source: Fictional teaching sample — Fictional receipt-shaped sample
data:
  - {provider: Local, seconds: 3.2}
  - {provider: Local, seconds: 4.1}
  - {provider: Local, seconds: 4.6}
  - {provider: Local, seconds: 5.0}
  - {provider: Local, seconds: 5.4}
  - {provider: Local, seconds: 5.8}
  - {provider: Local, seconds: 6.1}
  - {provider: Local, seconds: 6.5}
  - {provider: Local, seconds: 7.0}
  - {provider: Local, seconds: 7.8}
  - {provider: Local, seconds: 9.1}
  - {provider: Hosted, seconds: 4.9}
  - {provider: Hosted, seconds: 6.2}
  - {provider: Hosted, seconds: 7.4}
  - {provider: Hosted, seconds: 8.8}
  - {provider: Hosted, seconds: 9.6}
  - {provider: Hosted, seconds: 10.9}
  - {provider: Hosted, seconds: 12.3}
  - {provider: Hosted, seconds: 14.0}
  - {provider: Hosted, seconds: 16.7}
  - {provider: Hosted, seconds: 19.5}
  - {provider: Hosted, seconds: 24.1}
semantic_types: {provider: Category, seconds: Duration}
encodings:
  x: {field: seconds}
  color: {field: provider}
```

[[Charts Gallery]]

### Boxplot

Compare medians, quartiles and flagged outliers across groups. The box hides the individual pattern; a strip plot can be better for a handful of observations.

Source: a category column and a numeric column with several rows per category, such as deal size by segment or score by cohort, summarised as median, quartiles and outliers.

```chart
chartType: Boxplot
title: Enterprise sample deals span a wider range
subtitle: Closed-won deal size by segment, $k
source: Fictional teaching sample — CRM export, H1 2026
data:
  - {segment: SMB, size: 4.1}
  - {segment: SMB, size: 5.2}
  - {segment: SMB, size: 5.8}
  - {segment: SMB, size: 6.4}
  - {segment: SMB, size: 7.0}
  - {segment: SMB, size: 7.9}
  - {segment: SMB, size: 9.3}
  - {segment: SMB, size: 12.1}
  - {segment: Mid-market, size: 18}
  - {segment: Mid-market, size: 24}
  - {segment: Mid-market, size: 31}
  - {segment: Mid-market, size: 36}
  - {segment: Mid-market, size: 41}
  - {segment: Mid-market, size: 48}
  - {segment: Mid-market, size: 57}
  - {segment: Mid-market, size: 88}
  - {segment: Enterprise, size: 96}
  - {segment: Enterprise, size: 132}
  - {segment: Enterprise, size: 188}
  - {segment: Enterprise, size: 240}
  - {segment: Enterprise, size: 312}
  - {segment: Enterprise, size: 398}
  - {segment: Enterprise, size: 470}
  - {segment: Enterprise, size: 598}
semantic_types: {segment: Category, size: Amount}
encodings:
  x: {field: segment}
  y: {field: size}
```

[[Charts Gallery]]

### Violin plot

Compare the shape of distributions, including possible multiple peaks. Check sample size and smoothing; a suggestive shape is not evidence for a user persona.

Source: the same category-and-value table as a boxplot, when the shape of each distribution, such as bimodal or skewed, is the point.

```chart
chartType: Violin Plot
title: Pro's sample weekly sessions fall into two clusters
subtitle: Sessions per week by plan
source: Fictional teaching sample — Product analytics
data:
  - {plan: Pro, sessions: 1}
  - {plan: Pro, sessions: 1}
  - {plan: Pro, sessions: 2}
  - {plan: Pro, sessions: 2}
  - {plan: Pro, sessions: 2}
  - {plan: Pro, sessions: 3}
  - {plan: Pro, sessions: 9}
  - {plan: Pro, sessions: 10}
  - {plan: Pro, sessions: 11}
  - {plan: Pro, sessions: 12}
  - {plan: Pro, sessions: 12}
  - {plan: Pro, sessions: 14}
  - {plan: Team, sessions: 5}
  - {plan: Team, sessions: 6}
  - {plan: Team, sessions: 7}
  - {plan: Team, sessions: 7}
  - {plan: Team, sessions: 8}
  - {plan: Team, sessions: 8}
  - {plan: Team, sessions: 9}
  - {plan: Team, sessions: 9}
  - {plan: Team, sessions: 10}
  - {plan: Team, sessions: 11}
  - {plan: Team, sessions: 12}
  - {plan: Team, sessions: 15}
semantic_types: {plan: Category, sessions: Count}
encodings:
  x: {field: plan}
  y: {field: sessions}
```

[[Charts Gallery]]

### Strip plot

Show every observation in a modest sample. Repeated values may overlap; check the count and use the source table when exact individual values matter.

Source: a category column and a numeric column with a modest number of rows per category, when every individual point should stay visible.

```chart
chartType: Strip Plot
title: Reviewer scores agree closely on the strongest candidates
subtitle: Interview scores by candidate, 1–5, four reviewers each
source: Fictional teaching sample — Hiring panel, August 2026
data:
  - {candidate: Ames, score: 4.5}
  - {candidate: Ames, score: 4.0}
  - {candidate: Ames, score: 4.5}
  - {candidate: Ames, score: 5.0}
  - {candidate: Brook, score: 3.0}
  - {candidate: Brook, score: 4.0}
  - {candidate: Brook, score: 2.5}
  - {candidate: Brook, score: 3.5}
  - {candidate: Chen, score: 4.0}
  - {candidate: Chen, score: 4.0}
  - {candidate: Chen, score: 3.5}
  - {candidate: Chen, score: 4.5}
  - {candidate: Diaz, score: 2.0}
  - {candidate: Diaz, score: 3.5}
  - {candidate: Diaz, score: 4.0}
  - {candidate: Diaz, score: 2.5}
semantic_types: {candidate: Name, score: Score}
encodings:
  x: {field: candidate}
  y: {field: score}
```

[[Charts Gallery]]

## Use a form with your own records

Copy the whole **Charts Gallery** folder and add that copy to Flow first. Open [[Gallery Data]] to practise with a table you can edit. [[Charts — Living Example]] shows the refresh path. These reference exhibits keep their own embedded examples; they do not change when the practice table changes.

For a new exhibit, open a suitable example in the chart editor or select your own source rows and use Visualize. Keep the units and source explanation with the result. Visualize uses your configured Agency route; inspect its proposal before applying. Authored Mermaid diagrams need deliberate text edits; they are not automatically maintained from the table.

[[Charts Gallery]] · Previous: [[Charts — Composition]] · Next: [[Charts — Patterns]]
