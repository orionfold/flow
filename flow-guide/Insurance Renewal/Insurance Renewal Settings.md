---
title: Insurance Renewal Settings
tags: [insurance, settings, fictional-example]
---
# Insurance Renewal Settings

**Illustrative business inputs.** Edit the named table using its **Open in the table editor** control. **View ▸ Edit Table** opens the first table. Save the input document, then run the Jobs on [[Insurance Renewal]]; its refreshed views read these saved rows.

## Settings

| key | value |
| --- | --- |
| policy_year | 2026 |
| business | Alder Design Studio |
| owner | Nina Park |
| currency | USD |

## About these inputs

This fictional eighteen-person design business keeps three policies in its renewal folder. Nina owns the document collection; its broker owns insurance advice. Currency is a label, not a conversion rule: all sample amounts are annual USD premiums supplied in the packet.

## The input contract

`policy_year` selects the rows to show. Keep one complete snapshot per date in `inputs/`; a later snapshot replaces the earlier packet instead of adding its premiums again. The refresh reads the newest filename matching `insurance-snapshot-*.md`.

| Field | Meaning |
| --- | --- |
| `current_amount` | Annual premium in the expiring policy summary |
| `quote_amount` | Annual price transcribed from the offered quotation |
| `quote_status` | `received` only when a quotation exists; otherwise `awaiting` |
| `renewal` | Date copied from the source summary, not a calculated legal deadline |
| `source_id` | A reference in [[Insurance Renewal Sources]] |

The `0` placeholder for an absent quote is never a free offer or a saving. The comparison displays **Pending** and does not calculate a change.

Use [[Insurance Renewal]] for the working brief. Keep full real policy documents beside your own copies of the summaries; this example does not evaluate exclusions, sufficiency, or whether quotations are equivalent.
