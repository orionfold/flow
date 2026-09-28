---
title: Desk Refresh
tags: ["agent-desk", "example"]
sources:
  records: Agent Tasks.md#table:Tasks
emit:
  tasks:
    from: records
    steps:
      - sort: id
  waiting:
    from: records
    steps:
      - filter: status == 'Waiting'
      - sort: id
---
# Desk Refresh

This saved definition reads the task list and writes a dated summary of what still waits for your review. It uses no model or web service.

| Part | Purpose |
| --- | --- |
| Source | Agent Tasks — the work you handed an agent |
| Result | data/review-*.json — what waits for review |
