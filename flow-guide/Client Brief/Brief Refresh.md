---
title: Brief Refresh
tags: ["client-brief", "example"]
sources:
  records: Client Figures.md#table:Figures
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
---
# Brief Refresh

This saved definition reads this month's figures and writes a dated summary the brief binds to. With this definition open, choose **File ▸ Edit Definition…** to inspect it. It uses no model or web service.

| Part | Purpose |
| --- | --- |
| Source | Client Figures — the figures the brief cites |
| Result | data/review-*.json — what changed since last month |
| Next change | Change one figure, run Jobs, then read the brief |
