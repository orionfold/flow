---
title: Travel Refresh
tags: ["travel-planner", "example"]
sources:
  records: Travel Plan.md#table:Stays
  allowances: Travel Plan.md#table:Allowances
derive:
  accommodation:
    rows:
      - {category: Accommodation, amount: "{lodging}"}
let:
  nights:
    sum: nights
    of: records
  lodging:
    sum: budget_eur
    of: records
  otherCosts: {sum: amount, of: allowances}
  total: "lodging + otherCosts"
emit:
  budget:
    from: accommodation
    steps:
      - {concat: allowances}
  stays:
    from: records
    steps:
      - sort: arrival
  summary:
    - metric: Nights
      value: '{nights}'
    - metric: Accommodation, EUR
      value: '{lodging}'
    - metric: Total budget, EUR
      value: '{total}'
---
# Travel Refresh

This saved definition reads the records inside this folder and writes a dated summary. With this definition open, choose **File ▸ Edit Definition…** to inspect the sources, steps and results. It uses no model or web service.

| Part | Purpose |
| --- | --- |
| Source | Travel Plan — authored records |
| Result | data/review-*.json — regenerated summary |
| Next change | Change one source record, run Gather, then inspect the bound view. |
