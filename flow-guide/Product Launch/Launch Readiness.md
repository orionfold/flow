---
title: Launch Readiness
tags: ["product-launch", "example"]
jobs:
  - kind: gather
    definition: Launch Refresh.md
    as: review
  - kind: keep-sources-fresh
    watch: ["Launch Milestones.md", "Staff Meeting.md"]
  - kind: overnight-notes
---
# Launch Readiness

**Fictional website relaunch · 25 September planning snapshot · target 14 November**

## The CMS decision is the dependency to resolve first

Audit is complete. Build is blocked until the CMS decision and structure are ready. The plan overlaps migration with build, leaving little room to repair redirects at the end.

```chart data: data/review-*.json#milestones
chartType: Gantt Chart
title: Build and migration overlap; protect the handover
subtitle: Planned dates · September–November 2026
source: Fictional bundled example; replace with your own records
data:
  - {phase: "Audit", start: "2026-09-01", end: "2026-09-15", status: "Done", owner: "Priya"}
  - {phase: "Structure", start: "2026-09-15", end: "2026-10-06", status: "In progress", owner: "Dan"}
  - {phase: "Build", start: "2026-10-06", end: "2026-11-10", status: "Blocked", owner: "Mei"}
  - {phase: "Migration", start: "2026-10-27", end: "2026-11-14", status: "Planned", owner: "Dan"}
semantic_types:
  phase: Category
  start: Date
  end: Date
  status: Category
encodings:
  y:
    field: phase
  x:
    field: start
  x2:
    field: end
  color:
    field: status
    scheme: tableau10
```

## Blocked work

<!-- data: data/review-*.json#blocked -->
| Phase | Owner | Status |
| --- | --- | --- |
| Build | Mei | Blocked |

Read [[Launch Plan]] for outcomes and risk, [[Launch Brief]] for the product question, and [[Staff Meeting]] for the later decision. The brief is a separate fictional product exercise; it is not an announcement of a future Flow feature.
## Make it yours

1. Copy this entire folder in Finder, give the copy a name, then choose **Add Folder** in Flow. Keep its local subfolders beside the documents.
2. Open **Launch Milestones** and choose **View ▸ Edit Table** to replace the fictional records. Keep the column names and edit the cells, then save. The saved definition controls the calculation; the living report’s Jobs control recurring work.
3. Reconcile the 12 October meeting with the plan. Change Build from Blocked to In progress only after checking the actual start. Gather should remove Build from the blocked list.
4. With this document open, choose **File ▸ Night Shift Jobs…** to review its saved work; save any changes and close the editor. Choose **Settings ▸ Night Shift ▸ Run now**, then inspect the changed table or chart and the Briefing. Gather uses local calculations; optional Overnight notes need a configured local model. Enable Night Shift only for scheduled runs.
5. Replace the illustrative prose with your own assessment after checking the inputs. A chart can refresh its numbers; it cannot certify the conclusions around it.


## Review notes

Keep your decision here. Optional Night Shift notes appear below after a configured local model runs.

<!-- night: notes -->
<!-- /night: notes -->
