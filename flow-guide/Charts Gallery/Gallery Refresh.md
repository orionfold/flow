---
title: Gallery Refresh
tags: [charts-gallery, definition, fictional-example]
sources:
  records: Gallery Data.md#table:Records
derive:
  typedRecords:
    from: records
    steps:
      - calculate: coalesce(hours, 'missing') * 1
        as: hours
let:
  hours: {sum: hours, of: typedRecords}
  activities: {count: records, of: records}
emit:
  records:
    from: typedRecords
  summary:
    - {metric: Planned hours, value: "{hours}"}
    - {metric: Activities, value: "{activities}"}
---
# Gallery Refresh

[[Charts Gallery]] · [[Gallery Data]] · [[Charts — Living Example]]

This local definition totals the **Records** table in Gallery Data. With this definition open, choose **File ▸ Edit Definition…** to inspect its source and results. It does not call a model or web service.

| Part | Meaning |
| --- | --- |
| Source | `Gallery Data.md#table:Records` reads the body table under the exact Records heading |
| Hours | Sum of the entered `hours` cells; these are planned values |
| Activities | Number of supplied table rows |
| Output | `data/gallery-*.json#summary`, written by the living example's Gather job |
| Visible result | The summary table in Charts — Living Example |

The two charts and summary bind to the same dated capture. Gather carries the source rows and computes their total; it does not rewrite your input or the reference category examples. No validity claim is made for incomplete or nonsensical plans—inspect the table before using it.

Back: [[Charts — Living Example]] · Next: [[Charts — Comparisons]]
