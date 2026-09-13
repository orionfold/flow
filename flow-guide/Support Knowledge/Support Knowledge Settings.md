---
title: Support Knowledge Settings
tags: [support, settings, fictional-example]
---
# Support Knowledge Settings

**Illustrative business inputs.** Edit the named table using its **Open in the table editor** control. **View ▸ Edit Table** opens the first table. Save the input document, then run the Jobs on [[Support Knowledge]]; its refreshed views read these saved rows.

## Articles

| topic | article | status |
| --- | --- | --- |
| Access | Support Article — Account Access | Current |
| Calendar sync | Support Article — Calendar Connection | Current |
| Notifications | Support Article — Notification Choices | Current |
| Time zones | Support Proposal — Time Zone Clarity | Draft |

## Settings

| key | value |
| --- | --- |
| owner | Leila Morgan |
| review_threshold | 2 |

## About these inputs

Leila maintains the fictional Beacon Scheduling team's help material. A topic becomes a review candidate when its sample case count reaches `review_threshold` and its article status is not `Current`. This is a transparent queue rule, not an AI importance score.

The **Articles** table identifies documents inside this folder; edit its cells in the Table editor. Status is maintained by the owner: editing the text does not automatically approve or publish an article. Change Draft to Current only after your own review and any separate publication process.

## Keeping counts honest

One row in `tickets` means one resolved case, with one topic. The newest dated snapshot is a complete sample, not a batch to add to earlier snapshots. If a case touches several subjects, choose its primary topic instead of duplicating the case into the count.

| Setting | Supplied value | Effect |
| --- | --- | --- |
| Owner | Leila Morgan | Maintains the article index and review state |
| `review_threshold` | 2 cases | Minimum count for a candidate lacking a Current article |
| Access, Calendar sync, Notifications | Current | Excluded from the review queue while this status remains |
| Time zones | Draft | Enters review when its count reaches the threshold |

The sample is deliberately small. Counts describe these twelve cases; they are not population incident rates, customer prevalence, or a service-level measurement. A raw count has no customer or usage denominator.
