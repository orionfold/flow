---
title: Launch Refresh
tags: ["product-launch", "example"]
sources:
  records: Launch Milestones.md#table:Milestones
emit:
  milestones:
    from: records
    steps:
      - sort: start
  blocked:
    from: records
    steps:
      - filter: status == 'Blocked'
---
# Launch Refresh

This saved definition reads the records inside this folder and writes a dated summary. With this definition open, choose **File ▸ Edit Definition…** to inspect the sources, steps and results. It uses no model or web service.

| Part | Purpose |
| --- | --- |
| Source | Launch Milestones — authored records |
| Result | data/review-*.json — regenerated summary |
| Next change | Change one source record, run Gather, then inspect the bound view. |
