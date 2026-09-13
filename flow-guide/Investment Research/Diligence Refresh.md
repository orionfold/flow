---
title: Diligence Refresh
tags: ["investment-research", "example"]
sources:
  records: Diligence Register.md#table:Checks
emit:
  open:
    from: records
    steps:
      - filter: status == 'Open'
      - sort: id
  all:
    from: records
    steps:
      - sort: id
---
# Diligence Refresh

This saved definition reads the records inside this folder and writes a dated summary. With this definition open, choose **File ▸ Edit Definition…** to inspect the sources, steps and results. It uses no model or web service.

| Part | Purpose |
| --- | --- |
| Source | Diligence Register — authored records |
| Result | data/review-*.json — regenerated summary |
| Next change | Change one source record, run Gather, then inspect the bound view. |
