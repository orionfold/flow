---
title: Support Knowledge Refresh
tags: [support, definition, fictional-example]
sources:
  settings: Support Knowledge Settings.md#table:Settings
  articles: Support Knowledge Settings.md#table:Articles
  packet: inputs/support-snapshot-*.md#table:Review
  tickets: inputs/support-snapshot-*.md#table:Tickets
derive:
  topicCounts:
    from: tickets
    steps:
      - {filter: "outcome == 'Resolved'"}
      - {aggregate: topic, count: ticket, as: tickets}
  coverage:
    from: topicCounts
    steps:
      - {lookup: topic, from: articles, on: topic, fields: [article, status]}
      - {sort: topic}
let:
  threshold: {max: value, of: settings, where: "key == 'review_threshold'"}
  resolvedCount: {count: ticket, of: tickets, where: "outcome == 'Resolved'"}
  topicCount: {count: topic, of: topicCounts}
emit:
  review:
    from: packet
    steps:
      - {columns: [product, as_of, scope]}
  byTopic:
    from: topicCounts
    steps:
      - {sort: tickets, descending: true}
      - {columns: [topic, tickets]}
  coverage:
    from: coverage
    steps:
      - {columns: [topic, tickets, article, status]}
  reviewCandidates:
    from: coverage
    steps:
      - {filter: "tickets >= threshold && status != 'Current'"}
      - {columns: [topic, tickets, article, status]}
  summary:
    - {metric: Resolved sample cases, value: "{resolvedCount}"}
    - {metric: Topics represented, value: "{topicCount}"}
---
# Support Knowledge Refresh

This definition counts the resolved cases in the newest local snapshot, joins each topic to the owner-maintained article index, and applies the explicit review threshold. It does not read a ticketing service, generate new articles, or publish changes.

The output is `data/support-knowledge-<run-date>.json`. The article proposal is an authored example linked from the working page. Optional model notes are a separate job; they do not turn a Draft status into Current.

| Input | Output | Rule |
| --- | --- | --- |
| Resolved cases in the latest packet | Topic counts | One primary topic per case |
| Owner-maintained article index | Coverage table | Match each topic to its article and status |
| Review threshold and article status | Review candidates | Count reaches the threshold and article is not Current |

With this definition open, choose **File ▸ Edit Definition…** to inspect the rule. Edit routine topic names, article statuses, and the threshold in [[Support Knowledge Settings]].
