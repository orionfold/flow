---
title: Account Refresh
tags: ["sales-account", "example"]
sources:
  records: Account Requirements.md#table:Requirements
emit:
  requirements:
    from: records
    steps:
      - sort: id
  questions:
    from: records
    steps:
      - filter: status == 'Open'
      - sort: id
---
# Account Refresh

This saved definition reads the records inside this folder and writes a dated summary. With this definition open, choose **File ▸ Edit Definition…** to inspect the sources, steps and results. It uses no model or web service.

| Part | Purpose |
| --- | --- |
| Source | Account Requirements — authored records |
| Result | data/review-*.json — regenerated summary |
| Next change | Change one source record, run Gather, then inspect the bound view. |
