---
title: Campaign Refresh
tags: ["marketing-campaign", "example"]
sources:
  records: Editorial Calendar.md#table:Pieces
emit:
  calendar:
    from: records
    steps:
      - sort: due
  open:
    from: records
    steps:
      - filter: status != 'Published'
      - sort: due
---
# Campaign Refresh

This saved definition reads the records inside this folder and writes a dated summary. With this definition open, choose **File ▸ Edit Definition…** to inspect the sources, steps and results. It uses no model or web service.

| Part | Purpose |
| --- | --- |
| Source | Editorial Calendar — authored records |
| Result | data/review-*.json — regenerated summary |
| Next change | Change one source record, run Gather, then inspect the bound view. |
