---
title: Team Status
category: business-teams
featured: true
summary: "Keep a team's progress, blockers and next steps together."
tags: [status, dashboard, work, night-shift]
jobs:
  - kind: keep-sources-fresh
    watch: [Plan.md, updates, Team Review Decisions.md, Team Measurement Notes.md]
  - kind: reconcile-against-folder
    folder: updates
  - kind: overnight-notes
---
# Team Status

**Unblock the runner-image decision before promising the search benchmark or release date.**

> Fictional four-person product team · review as of 2 September 2026 · Q3 plan. These are illustrative reports, not Flow's own delivery or performance records.

Sam's blocked runner image also delays the fixture Marcus needs to measure search. **Next action:** the team lead records a decision on the image, then Marcus confirms the measurement date. Priya's reported completion-rate change needs its sample basis before it supports an impact claim.

Each owner maintains one local update. [[Plan]] owns milestones, [[Team Review Decisions]] owns decisions, and [[Team Measurement Notes]] preserves measurement limits. Flow can refresh the rollup and propose local-model Overnight notes; it does not make these decisions or certify the measurements.

## Decisions needed

<!-- data: Team Review Decisions.md#table:Decisions -->
| Id | Decision | Owner | Due | Basis | State |
| --- | --- | --- | --- | --- | --- |
| D1 | Approve or reject the pinned runner image | Team lead | 2026-09-03 | Sam Whitaker update | needed |
| D2 | Replan the search measurement after the fixture handoff | Marcus Chen | 2026-09-04 | Marcus Chen and Sam Whitaker updates | waiting on D1 |
| D3 | Confirm onboarding measurement basis before claiming impact | Priya Raman | 2026-09-04 | Team Measurement Notes | needed |

## The team this week

One row per file in `updates/`, read from each file's **Record** table. A person who has not updated is visible by their `updated` date.

<!-- data: updates/*.md#tables:Record -->
| Name | Area | Status | Confidence | Updated | This week | Next week | Blocker |
| --- | --- | --- | ---: | --- | --- | --- | --- |
| Dana Okafor | Billing | green | 90 | 2026-09-01 | Annual plan pricing live in the checkout; the receipt email now carries the seat count. | Dunning sequence: the three emails and the in-app banner. |  |
| Marcus Chen | Search | amber | 60 | 2026-08-31 | Rebuilt the index writer; the rebuild on the 40,000-note vault is at 48 s, target is 30 s. | Profile the tokenizer, which is 60% of the time, and try the batched write. | Need the perf fixture from Platform before the batched write can be measured honestly. |
| Priya Raman | Onboarding | green | 85 | 2026-08-31 | Shipped the first-run walkthrough to the beta group; two of the three flows measured under a minute. | Fold the survey feedback into the second flow and cut the copy by a third. |  |
| Sam Whitaker | Platform | red | 35 | 2026-09-01 | The signing pipeline broke on the new runner image; two days lost to a certificate that the image no longer trusts. | Pin the runner image, then hand Search the perf fixture. | The pinned image needs an infra ticket approved; without it every build after Tuesday is unsigned. |

## Confidence

```chart data: updates/*.md#tables:Record
chartType: Bar Chart
title: How sure each area is of landing the quarter
subtitle: Self-reported confidence, 0 to 100
source: updates/*.md, Record tables
data:
  - {name: "Dana Okafor", area: "Billing", status: "green", confidence: 90, updated: "2026-09-01", this_week: "Annual plan pricing live in the checkout; the receipt email now carries the seat count.", next_week: "Dunning sequence: the three emails and the in-app banner.", blocker: null, source: "Dana Okafor.md"}
  - {name: "Marcus Chen", area: "Search", status: "amber", confidence: 60, updated: "2026-08-31", this_week: "Rebuilt the index writer; the rebuild on the 40,000-note vault is at 48 s, target is 30 s.", next_week: "Profile the tokenizer, which is 60% of the time, and try the batched write.", blocker: "Need the perf fixture from Platform before the batched write can be measured honestly.", source: "Marcus Chen.md"}
  - {name: "Priya Raman", area: "Onboarding", status: "green", confidence: 85, updated: "2026-08-31", this_week: "Shipped the first-run walkthrough to the beta group; two of the three flows measured under a minute.", next_week: "Fold the survey feedback into the second flow and cut the copy by a third.", blocker: null, source: "Priya Raman.md"}
  - {name: "Sam Whitaker", area: "Platform", status: "red", confidence: 35, updated: "2026-09-01", this_week: "The signing pipeline broke on the new runner image; two days lost to a certificate that the image no longer trusts.", next_week: "Pin the runner image, then hand Search the perf fixture.", blocker: "The pinned image needs an infra ticket approved; without it every build after Tuesday is unsigned.", source: "Sam Whitaker.md"}
semantic_types: {name: Name, confidence: Score}
encodings:
  y: {field: name}
  x: {field: confidence}
  color: {field: area, scheme: teals}
```

## The quarter

```chart data: Plan.md#table:Milestones
chartType: Gantt Chart
title: Milestones, coloured by state
subtitle: From Plan.md
source: Plan.md, Milestones table
data:
  - {milestone: "Onboarding walkthrough to beta", owner: "Priya Raman", start: "2026-08-03", end: "2026-08-28", state: "done"}
  - {milestone: "Search index rebuild under 30 s", owner: "Marcus Chen", start: "2026-08-10", end: "2026-09-12", state: "at risk"}
  - {milestone: "Annual plans in checkout", owner: "Dana Okafor", start: "2026-08-17", end: "2026-09-05", state: "done"}
  - {milestone: "Signed builds on the new runner", owner: "Sam Whitaker", start: "2026-08-24", end: "2026-09-08", state: "blocked"}
  - {milestone: "Dunning sequence live", owner: "Dana Okafor", start: "2026-09-07", end: "2026-09-25", state: "planned"}
  - {milestone: "Release 2.4", owner: "Sam Whitaker", start: "2026-09-15", end: "2026-09-30", state: "planned"}
semantic_types: {milestone: Name, start: Date, end: Date, state: Category}
encodings:
  y: {field: milestone}
  x: {field: start}
  x2: {field: end}
  color: {field: state, scheme: oranges}
```

## Updates on file

```flow-folder updates
| File | Size | Modified | Digest |
| --- | ---: | --- | --- |
| Dana Okafor.md | 975 |  |  |
| Marcus Chen.md | 1119 |  |  |
| Priya Raman.md | 1013 |  |  |
| Sam Whitaker.md | 1092 |  |  |
```

Bundled file list; the inventory job fills timestamps and digests in your working copy.

## What changes on a run

Bound tables and charts refresh from the supplied update files and plan. Source watches and inventory report changed files. A new person requires an actual source document; a stale `updated` date stays visible. Review any Overnight note against those dates, blockers and [[Team Measurement Notes]]. Local prose generation does not establish a new measurement, approval or milestone.

## Make it yours

1. Copy the whole **Team Status** folder and add it in Flow. Share that folder using a storage arrangement your team already approves; one designated Mac can run the scheduled jobs.
2. Open [[Sam Whitaker]] and choose **View ▸ Edit Table**. Change `confidence` from 35 to 45 in his **Record** row, then save. After a run, his bar and row should change; the blocker and decision D1 must remain unresolved until explicitly edited.
3. Replace the four fictional updates, milestones, measurement notes and decisions with your team's records. Preserve one source file per owner and an honest `updated` date.
4. Use **File ▸ Night Shift Jobs…** to review the local watches, folder inventory and optional Overnight notes. This example binds directly to authored documents; it does not need a Gather definition.
5. Choose **Settings ▸ Night Shift ▸ Run now**; enable Night Shift only for scheduled updates. Check the run result and diff. Update the decision queue yourself after the meeting; Flow has not approved the runner image or sent anyone a task.

## How this page is built

| Block | Construct | Bound to | Redrawn by |
| --- | --- | --- | --- |
| The team this week | table over a glob | `updates/*.md#tables:Record` | the night alone |
| Confidence | Bar Chart over the same glob | `updates/*.md#tables:Record` | the night alone |
| The quarter | Gantt Chart | `Plan.md#table:Milestones` | the night alone |
| Updates on file | `flow-folder` inventory | `updates/` | the night alone |

The binding `updates/*.md#tables:Record` reads the **Record** table from every matching document. Each person keeps one source document; the combined view preserves the owner and update date of each record.

## Overnight notes
<!-- night: notes -->
<!-- /night: notes -->
