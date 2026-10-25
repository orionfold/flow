---
title: Skills Refresh
tags: [skills-gallery, definition, fictional-example]
sources:
  records: Skills Input.md#table:Initiatives
derive:
  typed:
    from: records
    steps:
      - calculate: coalesce(value, 'missing') * 1
        as: value
      - calculate: coalesce(effort, 'missing') * 1
        as: effort
  quick:
    from: typed
    steps:
      - filter: quadrant == 'Quick win'
let:
  initiatives: {count: initiative, of: typed}
  quickWins: {count: initiative, of: quick}
emit:
  initiatives:
    from: typed
  summary:
    - {metric: Initiatives, value: "{initiatives}"}
    - {metric: Quick wins, value: "{quickWins}"}
---
# Skills Refresh

[[Skills Gallery]] · [[Skills Input]] · [[Skills — Living Example]]

This local definition reads the **Initiatives** table in Skills Input and counts what it holds. With this definition open, choose **File ▸ Edit Definition…** to inspect its source and results. It does not call a model or a web service.

| Part | Meaning |
| --- | --- |
| Source | `Skills Input.md#table:Initiatives`, the table under that exact heading |
| Initiatives | The number of rows you entered |
| Quick wins | The rows whose quadrant you named Quick win |
| Output | `data/skills-*.json`, written by the living example's Gather job |
| Visible result | The map and the summary in Skills — Living Example |

The skill drew the map once, from a passage. This definition keeps that map's dots on your current numbers; it does not re-run the skill or judge your scores.

Back: [[Skills — Living Example]] · Next: [[Skills — Decide]]
