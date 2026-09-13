---
title: Insurance Renewal Refresh
tags: [insurance, definition, fictional-example]
sources:
  settings: Insurance Renewal Settings.md#table:Settings
  packet: inputs/insurance-snapshot-*.md#table:Review
  policies: inputs/insurance-snapshot-*.md#table:Policies
  schedule: inputs/insurance-snapshot-*.md#table:Schedule
  requests: inputs/insurance-snapshot-*.md#table:Requests
let:
  year: {max: value, of: settings, where: "key == 'policy_year'"}
emit:
  review:
    from: packet
    steps:
      - {columns: [as_of, business, period, basis]}
  comparison:
    from: policies
    steps:
      - {filter: "policy_year == year"}
      - {calculate: "quote_status == 'received' ? quote_amount : 'Pending'", as: offer}
      - {calculate: "quote_status == 'received' ? quote_amount - current_amount : 'Pending'", as: change}
      - {calculate: "quote_status == 'received' && current_amount > 0 ? round((quote_amount - current_amount) / current_amount * 100, 1) : 'Pending'", as: change_pct}
      - {columns: [policy, current_amount, offer, change, change_pct, renewal, source_id]}
  timeline:
    from: schedule
    steps:
      - {filter: "policy_year == year"}
      - {columns: [task, start, due, stage]}
  outstanding:
    from: requests
    steps:
      - {filter: "policy_year == year && status != 'received'"}
      - {columns: [id, item, owner, status, source_id]}
---
# Insurance Renewal Refresh

This definition reads one dated local packet and builds the comparison, review windows, and outstanding-document list in [[Insurance Renewal]]. It transcribes and calculates; it does not read insurance language or recommend a policy.

The percentage change uses the expiring premium as its denominator. A missing quotation remains Pending. Rows from other policy years are excluded using [[Insurance Renewal Settings]]. A missing named source prevents a new successful capture; an older displayed capture remains dated evidence, not proof of a successful refresh.

| Input | Result | Rule to inspect |
| --- | --- | --- |
| Latest packet's policies | Premium comparison | Selected policy year; expiring premium is the percentage denominator; missing quote stays Pending |
| Latest packet's schedule | Preparation windows | Supplied dates for the selected policy year |
| Latest packet's requests | Outstanding documents | Received items are excluded |

Edit routine facts in the newest packet's named tables using the Table editor; save before running the jobs. With this definition open, choose **File ▸ Edit Definition…** to inspect the sources and calculations. The output is `data/insurance-renewal-<run-date>.json`. The two bundled captures are authored examples of those calculations, not runtime receipts.
