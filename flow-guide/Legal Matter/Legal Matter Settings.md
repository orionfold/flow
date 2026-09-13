---
title: Legal Matter Settings
tags: [legal, settings, fictional-example]
---
# Legal Matter Settings

**Illustrative business inputs.** Edit the named table using its **Open in the table editor** control. **View ▸ Edit Table** opens the first table. Save the input document, then run the Jobs on [[Legal Matter]]; its refreshed views read these saved rows.

## Settings

| key | value |
| --- | --- |
| matter | Harbor Supply and Elm Studio delivery records |
| owner | Avery Chen |
| currency | USD |
| purpose | Prepare a factual document review |

## About these inputs

Avery is organizing a fictional commercial delivery file for professional review. This workspace records what documents say and what still needs checking. It supplies no jurisdiction, legal cause of action, limitation date, liability conclusion, or demand to send.

## Keep the input small and explicit

Each dated snapshot in `inputs/` is a complete packet index. `events` contains transcribed facts with a date, a short description, the basis, and an exhibit ID. `documents` counts the supplied source records. The newest filename wins; previous snapshots are retained for comparison.

An event date is the date described by the record. A snapshot date is when that record became part of the packet. The later packet can therefore add an earlier event without changing its event date.

| Field or record | Sample | Meaning |
| --- | --- | --- |
| Owner | Avery Chen | Maintains this factual review file |
| Event date | 28 August for LM-06 | When the record says the event occurred |
| Packet date | 12 September for the added LM-06 record | When the source joined this example packet |
| Exhibit ID | LM-06 | Connects the transcribed event to the authored source index |

The ordinary Markdown links in [[Legal Matter Sources]] connect IDs to the underlying text. This index is authored and must be maintained when you add an exhibit; Flow is not claiming automatic legal citation verification.
