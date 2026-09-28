---
title: Issue Refresh
tags: ["newsletter-archive", "example"]
sources:
  records: Issue Log.md#table:Issues
emit:
  issues:
    from: records
    steps:
      - sort: issue
  drafts:
    from: records
    steps:
      - filter: status == 'Draft'
      - sort: issue
---
# Issue Refresh

This saved definition reads the issue log and writes a dated summary of what is published and what is still a draft. It uses no model or web service.

| Part | Purpose |
| --- | --- |
| Source | Issue Log — one row per issue |
| Result | data/review-*.json — the archive and the drafts |
