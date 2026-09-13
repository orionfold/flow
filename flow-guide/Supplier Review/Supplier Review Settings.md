---
title: Supplier Review Settings
tags: [procurement, settings, fictional-example]
---
# Supplier Review Settings

**Illustrative business inputs.** Edit the named table using its **Open in the table editor** control. **View ▸ Edit Table** opens the first table. Save the input document, then run the Jobs on [[Supplier Review]]; its refreshed views read these saved rows.

## Settings

| key | value |
| --- | --- |
| business | Linden Workshop |
| owner | Mateo Rivera |
| currency | USD |
| review_period | March through August 2026 |

## About these inputs

Linden is a fictional small manufacturer. Mateo gathers the commercial facts; service owners decide whether each proposed scope meets the business's needs. This workspace creates no composite vendor score and sends no purchase order.

## Two kinds of dollars

The `suppliers` array contains annual **fixed service fees**, copied from the current agreement summary and the offered renewal. The `invoices` array contains separate **variable purchases** over six complete months. They are different measures: do not add six-month variable spend to an annual fee and call it annual cost.

All example figures are USD, with no tax, exchange-rate adjustment, or assumption about future volumes. The labels here describe the packet; the data rows supply its numbers.

| Packet field | Measure | How to keep it comparable |
| --- | --- | --- |
| `suppliers.current`, `suppliers.offered` | Annual fixed service fees, USD | Check scope and term length before comparing prices |
| `invoices.amount` | Variable purchases, USD | Use the stated six complete months |
| `review_period` | March through August 2026 | Descriptive setting; the definition includes the newest packet's invoice rows |
| `currency` | USD | Label only; no exchange-rate conversion |

Each dated snapshot is complete. Add a later full snapshot when quotations or invoices change; the newest matching filename is read once. Keep each offered number supported by a source note and explain whether scope, service levels, volume, or term length changed.
