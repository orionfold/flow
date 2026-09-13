---
title: Research Refresh
tags: ["customer-research", "example"]
sources:
  records: Interview Register.md#table:Interviews
emit:
  needs:
    from: records
    steps:
      - aggregate: need
        sum: mentions
        as: mentions
      - sort: need
  interviews:
    from: records
    steps:
      - sort: id
---
# Research Refresh

This saved definition reads the records inside this folder and writes a dated summary. With this definition open, choose **File ▸ Edit Definition…** to inspect the sources, steps and results. It uses no model or web service.

| Part | Purpose |
| --- | --- |
| Source | Interview Register — authored records |
| Result | data/review-*.json — regenerated summary |
| Next change | Change one source record, run Gather, then inspect the bound view. |
