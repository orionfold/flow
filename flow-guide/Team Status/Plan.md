---
title: Plan
tags: [status, parameters, night-shift]
---
# Plan

**Illustrative business inputs.** Edit the named table using its **Open in the table editor** control. **View ▸ Edit Table** opens the first table. Save the input document, then run the Jobs on [[Team Status]]; its refreshed views read these saved rows.

## Milestones

| milestone | owner | start | end | state |
| --- | --- | --- | --- | --- |
| Onboarding walkthrough to beta | Priya Raman | 2026-08-03 | 2026-08-28 | done |
| Search index rebuild under 30 s | Marcus Chen | 2026-08-10 | 2026-09-12 | at risk |
| Annual plans in checkout | Dana Okafor | 2026-08-17 | 2026-09-05 | done |
| Signed builds on the new runner | Sam Whitaker | 2026-08-24 | 2026-09-08 | blocked |
| Dunning sequence live | Dana Okafor | 2026-09-07 | 2026-09-25 | planned |
| Release 2.4 | Sam Whitaker | 2026-09-15 | 2026-09-30 | planned |

## Settings

| key | value |
| --- | --- |
| quarter | Q3 2026 |

## About these inputs

The quarter's milestones, one line each. [[Team Status]] draws its timeline from this list every night; the owners' weekly updates live in `updates/`.

| Field | What it is |
| --- | --- |
| `milestone` | The outcome, named as a thing that is either done or not. |
| `owner` | One person. |
| `start`, `end` | The dates the timeline draws between. |
| `state` | `planned`, `on track`, `at risk`, `blocked`, `done`. The timeline colours by it. |

Edit the dates here when the plan changes, never in the dashboard: the dashboard is redrawn from this file.
