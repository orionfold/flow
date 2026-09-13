---
title: Legal Matter Refresh
tags: [legal, definition, fictional-example]
sources:
  packet: inputs/legal-snapshot-*.md#table:Review
  events: inputs/legal-snapshot-*.md#table:Events
  documents: inputs/legal-snapshot-*.md#table:Documents
let:
  eventCount: {count: date, of: events}
  documentCount: {count: exhibit, of: documents}
emit:
  review:
    from: packet
    steps:
      - {columns: [matter, as_of, record_type]}
  chronology:
    from: events
    steps:
      - {sort: date}
      - {columns: [date, event, basis, exhibit]}
  counts:
    - {metric: Events in the packet, value: "{eventCount}"}
    - {metric: Source records supplied, value: "{documentCount}"}
---
# Legal Matter Refresh

The definition sorts the events already transcribed in the latest local packet and counts its records. It never infers a fact from an exhibit, decides which conflicting account is true, or calculates a legal deadline.

The output is `data/legal-matter-<run-date>.json`. The comparison matrix and review questions in [[Legal Matter]] are authored prose; they are not silently rewritten when this definition runs. Check them yourself when a new source arrives.

| Input in the newest packet | Calculated output | Human review still needed |
| --- | --- | --- |
| Transcribed events | Chronology sorted by event date; event count | Accuracy of each transcription |
| Supplied document index | Count of source records | Completeness and authenticity of the records |
| Packet review metadata | Matter and snapshot date | Authored comparison matrix and questions |

With this definition open, choose **File ▸ Edit Definition…** to inspect these steps. The source watch is a separate job: open [[Legal Matter]] and choose **File ▸ Night Shift Jobs…**.
