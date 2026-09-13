---
title: Board Outlook
tags: [board, planning, example]
---
# Board Outlook

**Meridian Software · fictional planning discussion · 30 September 2026**

## Q4 needs a forecast with conditions

The later annual review records Q4 revenue of $5.7M. This earlier board packet is the planning view: a $5.7M base case against a $5.2M Q3 close. Keep a forecast and an actual separate so that the review can explain the difference.

| Scenario | Q4 revenue, USD M | What must hold |
| --- | ---: | --- |
| Downside | 5.2 | Renewals hold; expansion closes later |
| Base | 5.7 | Planned renewals and the dated expansion schedule close |
| Upside | 6.0 | Additional expansion clears procurement this quarter |

```chart
chartType: Bar Chart
title: Three scenarios make the uncertainty visible
subtitle: Fictional Q4 revenue · USD millions
source: Authored board planning exercise
data:
  - {scenario: Downside, revenue: 5.2}
  - {scenario: Base, revenue: 5.7}
  - {scenario: Upside, revenue: 6.0}
semantic_types: {scenario: Category, revenue: Amount}
encodings:
  x: {field: scenario}
  y: {field: revenue}
  color: {field: scenario, scheme: teals}
```

## The decisions to record

1. Confirm the scenario used for cash planning and its evidence date.
2. Separate essential replacement roles from expansion hiring in [[Hiring Plan]].
3. Set a date to revisit commitments if signed expansion falls behind.

This packet does not demonstrate cash runway or approve spending. Bring the cash balance, collections schedule and signed commitments to that decision. Compare the eventual result with [[Quarterly Review]] and retain the decision in [[Decision Record]].
