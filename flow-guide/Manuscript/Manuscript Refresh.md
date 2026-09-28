---
title: Manuscript Refresh
tags: ["manuscript", "example"]
sources:
  records: Chapter Plan.md#table:Chapters
emit:
  chapters:
    from: records
    steps:
      - sort: chapter
  drafting:
    from: records
    steps:
      - filter: status == 'Drafting'
      - sort: chapter
---
# Manuscript Refresh

This saved definition reads the chapter plan and writes a dated summary of where the book stands. It uses no model or web service.

| Part | Purpose |
| --- | --- |
| Source | Chapter Plan — one row per chapter |
| Result | data/review-*.json — chapters, and the ones still being drafted |
