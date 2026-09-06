---
title: Team Status
tags: [status, dashboard, work, night-shift]
jobs:
  - kind: keep-sources-fresh
    watch: [Plan.md, updates]
  - kind: reconcile-against-folder
    folder: updates
  - kind: overnight-notes
---
# Team Status

The weekly roll-up, written by the night instead of by the manager. Each
person keeps one file in `updates/` and rewrites its front matter when their
week changes. Every night this page reads all of them into one table, redraws
the confidence chart, and lists the quarter's milestones from [[Plan]]. The
morning's Briefing shows who changed what, as a diff, so the Monday meeting
starts from what is already known.

## The team this week

One row per file in `updates/`, read from each file's front matter. A person
who has not updated is visible by their `updated` date.

<!-- data: updates/*.md -->
| Name | Area | Status | Confidence | Updated | This week | Next week | Blocker |
| --- | --- | --- | ---: | --- | --- | --- | --- |
| Dana Okafor | Billing | green | 90 | 2026-09-01 | Annual plan pricing live in the checkout; the receipt email now carries the seat count. | Dunning sequence: the three emails and the in-app banner. |  |
| Marcus Chen | Search | amber | 60 | 2026-08-31 | Rebuilt the index writer; the rebuild on the 40,000-note vault is at 48 s, target is 30 s. | Profile the tokenizer, which is 60% of the time, and try the batched write. | Need the perf fixture from Platform before the batched write can be measured honestly. |
| Priya Raman | Onboarding | green | 85 | 2026-08-31 | Shipped the first-run walkthrough to the beta group; two of the three flows measured under a minute. | Fold the survey feedback into the second flow and cut the copy by a third. |  |
| Sam Whitaker | Platform | red | 35 | 2026-09-01 | The signing pipeline broke on the new runner image; two days lost to a certificate that the image no longer trusts. | Pin the runner image, then hand Search the perf fixture. | The pinned image needs an infra ticket approved; without it every build after Tuesday is unsigned. |

## Confidence

```chart data: updates/*.md
chartType: Bar Chart
title: How sure each area is of landing the quarter
subtitle: Self-reported confidence, 0 to 100
source: updates/*.md, front matter
data:
  - {title: "Dana Okafor", name: "Dana Okafor", area: "Billing", status: "green", confidence: 90, updated: "2026-09-01", this_week: "Annual plan pricing live in the checkout; the receipt email now carries the seat count.", next_week: "Dunning sequence: the three emails and the in-app banner.", blocker: ""}
  - {title: "Marcus Chen", name: "Marcus Chen", area: "Search", status: "amber", confidence: 60, updated: "2026-08-31", this_week: "Rebuilt the index writer; the rebuild on the 40,000-note vault is at 48 s, target is 30 s.", next_week: "Profile the tokenizer, which is 60% of the time, and try the batched write.", blocker: "Need the perf fixture from Platform before the batched write can be measured honestly."}
  - {title: "Priya Raman", name: "Priya Raman", area: "Onboarding", status: "green", confidence: 85, updated: "2026-08-31", this_week: "Shipped the first-run walkthrough to the beta group; two of the three flows measured under a minute.", next_week: "Fold the survey feedback into the second flow and cut the copy by a third.", blocker: ""}
  - {title: "Sam Whitaker", name: "Sam Whitaker", area: "Platform", status: "red", confidence: 35, updated: "2026-09-01", this_week: "The signing pipeline broke on the new runner image; two days lost to a certificate that the image no longer trusts.", next_week: "Pin the runner image, then hand Search the perf fixture.", blocker: "The pinned image needs an infra ticket approved; without it every build after Tuesday is unsigned."}
semantic_types: {name: Name, confidence: Score}
encodings:
  y: {field: name}
  x: {field: confidence}
```

## The quarter

```chart data: Plan.md#milestones
chartType: Gantt Chart
title: Milestones, coloured by state
subtitle: From Plan.md
source: Plan.md, front matter
data:
  - {milestone: "Onboarding walkthrough to beta", owner: "Priya Raman", start: "2026-08-03", end: "2026-08-28", state: "done"}
  - {milestone: "Search index rebuild under 30 s", owner: "Marcus Chen", start: "2026-08-10", end: "2026-09-12", state: "at risk"}
  - {milestone: "Annual plans in checkout", owner: "Dana Okafor", start: "2026-08-17", end: "2026-09-05", state: "on track"}
  - {milestone: "Signed builds on the new runner", owner: "Sam Whitaker", start: "2026-08-24", end: "2026-09-08", state: "blocked"}
  - {milestone: "Dunning sequence live", owner: "Dana Okafor", start: "2026-09-07", end: "2026-09-25", state: "planned"}
  - {milestone: "Release 2.4", owner: "Sam Whitaker", start: "2026-09-15", end: "2026-09-30", state: "planned"}
semantic_types: {milestone: Name, start: Date, end: Date, state: Category}
encodings:
  y: {field: milestone}
  x: {field: start}
  x2: {field: end}
  color: {field: state}
```

## Updates on file

```flow-folder updates
| File | Size | Modified | Digest |
| --- | ---: | --- | --- |
| Dana Okafor.md | 975 | 2026-09-03T04:43:12Z | f2d3e8026afe |
| Marcus Chen.md | 1119 | 2026-09-03T04:43:12Z | a1ce8b47462b |
| Priya Raman.md | 1013 | 2026-09-03T04:43:12Z | c6554cf7c6ad |
| Sam Whitaker.md | 1092 | 2026-09-03T04:43:12Z | fcb6f43c4eeb |
```

## What you will see in the morning

- **Someone updated.** Their row changed, the confidence bar moved, and the
  Briefing shows the exact diff of their file.
- **Someone joined.** A new file in `updates/` is a new row and a new bar;
  the inventory names the file.
- **The plan moved.** A milestone's dates or state changed in [[Plan]]; the
  timeline shows it and the Briefing shows the diff.

## Make it yours

1. Copy one of the files in `updates/` per person on the team, named for
   them, and delete the four examples.
2. Ask each person to rewrite their front matter once a week. The three
   sentences are the update; the numbers are the roll-up.
3. Put the quarter in the front matter of [[Plan]].
4. Turn the Night Shift on: the moon in the title bar, or Settings ▸ Night
   Shift. A shared folder works the same way: everyone edits their own file,
   one Mac runs the night.

## How this page is built

| Block | Construct | Bound to | Redrawn by |
| --- | --- | --- | --- |
| The team this week | table over a glob | `updates/*.md` | the night alone |
| Confidence | Bar Chart over the same glob | `updates/*.md` | the night alone |
| The quarter | Gantt Chart | `Plan.md#milestones` | the night alone |
| Updates on file | `flow-folder` inventory | `updates/` | the night alone |

A glob without a `#key` reads one row per matching file, from that file's
front matter. That is the whole mechanism: a folder of small documents, each
owned by one person, rolled up by the night.

## Overnight notes
<!-- night: notes -->
<!-- /night: notes -->
