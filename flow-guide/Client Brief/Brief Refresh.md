---
title: Brief Refresh
tags: ["client-brief", "example"]
sources:
  records: Client Figures.md#table:Figures
  keyFigures: Client Figures.md#table:Key figures
  revenueByMonth: Client Figures.md#table:Revenue by month
emit:
  figures:
    from: records
    steps:
      - sort: id
  changed:
    from: records
    steps:
      - filter: status == 'Changed'
      - sort: id
  kpis:
    from: keyFigures
  revenue:
    from: revenueByMonth
    steps:
      - sort: month
---
# Brief Refresh

This saved definition reads this month's figures and writes a dated summary the brief binds to. With this definition open, choose **File ▸ Edit Definition…** to inspect it. It uses no model or web service.

| Part | Purpose |
| --- | --- |
| Sources | Client Figures — its three tables: the figures the brief cites, the key figures for the cards, revenue by month for the chart |
| Result | data/review-*.json — what changed since last month, the cards and the chart's rows |
| Next change | Change one figure, run Jobs, then read the brief |
