---
title: Skills — Living Example
tags: [skills-gallery, living-workspace, fictional-example]
jobs:
  - kind: gather
    definition: Skills Refresh.md
    into: data
    as: skills
  - kind: keep-sources-fresh
    watch: [Skills Input.md]
---
# Skills — Living Example

[[Skills Gallery]] · Input: [[Skills Input]] · Next: [[Skills — Decide]]

**A skill draws once; Jobs keep it current.** This page shows both halves. The **skill** is Opportunity Map: it read the planning notes below and drew the map from them, once. **Jobs** then took over: the map's dots now come from the table in [[Skills Input]], so a changed score moves a dot without running the skill again.

## The notes the skill read

> This quarter we could ship self-serve intake, which support says would remove a third of their tickets and takes one engineer two weeks. A billing rewrite would fix the invoicing errors finance complains about but needs three engineers for a quarter and a migration. A dark-mode theme is a common request with little revenue behind it; a designer estimates a week. Replatforming search onto a new engine would cut hosting cost slightly and take two months of the platform team.

*Fictional quarter plan · as of 24 October 2026.* Selecting these notes and pressing **Opportunity Map** under **Skills** in **Elements** scored each initiative for value and effort from 1 to 10, named its quadrant and drew the map below.

## Which initiatives are worth the effort

```chart data: data/skills-*.json#initiatives skill: opportunity-map
chartType: Scatter Plot
title: Self-serve intake is the clear quick win
subtitle: Value against effort, 1 to 10; top left is high value for little effort; drawn by Opportunity Map
source: Newest skills capture from Skills Input; fictional plan
data:
  - {initiative: Self-serve intake, effort: 2, value: 8, quadrant: Quick win}
  - {initiative: Billing rewrite, effort: 9, value: 7, quadrant: Big bet}
  - {initiative: Dark mode, effort: 2, value: 3, quadrant: Fill-in}
  - {initiative: Search replatform, effort: 8, value: 3, quadrant: Reconsider}
semantic_types:
  effort: {semanticType: Score, intrinsicDomain: [1, 10]}
  value: {semanticType: Score, intrinsicDomain: [1, 10]}
  quadrant: Category
encodings:
  x: {field: effort}
  y: {field: value}
  color: {field: quadrant, scheme: tableau10}
```

**Which part is which.** The skill wrote this chart: its title is the skill's reading of the notes, and the chart's opening line names `skill: opportunity-map`, so **Change it…** in the chart's pane runs the skill again. Jobs own only the dots and the summary: they redraw from the newest capture of [[Skills Input]]. After you change a score, check that the title still says what the dots show; a refresh never rewrites it.

<!-- data: data/skills-*.json#summary -->
| Metric | Value |
| --- | ---: |
| Initiatives | 4 |
| Quick wins | 1 |

## Make it yours

1. Copy the complete **Skills Gallery** folder and add the copy to Flow. Work in that copy.
2. Open [[Skills Input]] and use **View ▸ Edit Table** on its Initiatives table. Change Dark mode's value from **3 to 7** and its quadrant to **Quick win**, then save.
3. Return here and choose **Settings ▸ Jobs ▸ Run all Jobs**. Expect Dark mode's dot to rise beside Self-serve intake, and the summary to show **2 quick wins**. Review the change, then keep it.
4. To draw a map from your own notes instead, select them in any document, open **Elements**, and press **Opportunity Map** under **Skills**.

## What refresh changes

Gather reads the saved table and writes its rows and counts to one capture. The map and the summary redraw from the newest capture. Your table, the title and this explanation stay as written. The worked examples on the other pages carry their own data and do not change when you edit this one.

Back: [[Skills Gallery]] · Input: [[Skills Input]] · Definition: [[Skills Refresh]] · Next: [[Skills — Decide]]
