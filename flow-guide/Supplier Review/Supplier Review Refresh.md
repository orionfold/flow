---
title: Supplier Review Refresh
tags: [procurement, definition, fictional-example]
sources:
  packet: inputs/supplier-snapshot-*.md#table:Review
  suppliers: inputs/supplier-snapshot-*.md#table:Suppliers
  invoices: inputs/supplier-snapshot-*.md#table:Invoices
derive:
  currentFees:
    from: suppliers
    steps:
      - {calculate: "'Current fee'", as: basis}
      - {calculate: "current", as: annual}
      - {columns: [supplier, basis, annual]}
  offeredFees:
    from: suppliers
    steps:
      - {calculate: "'Offered fee'", as: basis}
      - {calculate: "offered", as: annual}
      - {columns: [supplier, basis, annual]}
let:
  currentTotal: {sum: current, of: suppliers}
  offeredTotal: {sum: offered, of: suppliers}
  changeTotal: "offeredTotal - currentTotal"
  purchaseTotal: {sum: amount, of: invoices}
emit:
  review:
    from: packet
    steps:
      - {columns: [business, as_of, currency, spend_period]}
  quoteDots:
    from: offeredFees
    steps:
      - {concat: currentFees}
      - {sort: supplier}
      - {columns: [supplier, basis, annual]}
  comparison:
    from: suppliers
    steps:
      - {calculate: "offered - current", as: change}
      - {calculate: "current > 0 ? round((offered - current) / current * 100, 1) : 'No baseline'", as: change_pct}
      - {columns: [supplier, current, offered, change, change_pct, renewal, source_id]}
  spend:
    from: invoices
    steps:
      - {aggregate: supplier, sum: amount, as: spent}
      - {sort: spent, descending: true}
  summary:
    - {metric: Current annual fixed fees, value: "{currentTotal}"}
    - {metric: Offered annual fixed fees, value: "{offeredTotal}"}
    - {metric: Change in fixed fees, value: "{changeTotal}"}
    - {metric: Six-month variable purchases, value: "{purchaseTotal}"}
---
# Supplier Review Refresh

This definition builds two dots per supplier, calculates the offered annual-fee change, and totals the separately supplied variable invoices. It performs no vendor scoring, market-price lookup, contract interpretation, or purchase action.

The offer must be a supplied number. If a quotation has not arrived, keep that supplier in an authored pending-items note until an offered amount exists; do not enter zero as an estimate. A zero current fee is labelled **No baseline** in the percentage column.

All invoice rows in the newest snapshot are included. Keep the snapshot's `spend_period` aligned with those rows; this definition does not infer or filter a period from the settings label.

| Source rows | Output | Unit and boundary |
| --- | --- | --- |
| Current and offered supplier fees | Paired dots and quotation comparison | Annual fixed fees; no offer is an accepted saving |
| Variable invoices | Spend by supplier and total | Six-month purchases, separate from annual fees |
| Packet metadata | Business, currency and spend period | Labels the supplied rows; does not filter dates or convert currencies |

The output is `data/supplier-review-<run-date>.json`. With this definition open, choose **File ▸ Edit Definition…** to inspect the transformations.
