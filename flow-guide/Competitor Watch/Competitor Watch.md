---
title: Competitor Watch
tags: [competitive, dashboard, work, night-shift]
jobs:
  - kind: keep-sources-fresh
    watch: [Competitors.md, captures, https://asana.com/pricing, https://clickup.com/pricing, https://linear.app/pricing, https://monday.com/pricing]
  - kind: reconcile-against-folder
    folder: captures
  - kind: overnight-notes
---
# Competitor Watch

**Decide which competitive change deserves a response from the product team.** A changed webpage is evidence to inspect, not a pricing recommendation.

> Illustrative team-work-management review · source-price snapshot 2 September 2026 · USD per seat/month, annual billing. The four companies are real; “Our product” is fictional. These are dated examples, not current quotations.

**Next action:** validate the plan, currency, minimum seats and captured price before comparing entry costs. The retained first-read note lacks exact price evidence; do not use the chart as a procurement quote. Competitor feature assessments are deliberately **unknown** until supported by a dated, tier-specific source.

[[Competitors]] owns the comparison. The named Asana, ClickUp, Linear and monday.com pricing pages can be watched for changes. Flow reports their changed text; you review that evidence and update the comparison. The chart does not extract new prices automatically.

## Entry price per seat

```chart data: Competitors.md#table:Competitors
chartType: Bar Chart
title: First paid tier, per seat per month
subtitle: Dated example prices; annual billing, USD per seat/month
source: Competitors.md, Competitors table
data:
  - {name: "Asana", product: "Asana", entry_tier: "Starter", price_per_seat: 10.99, billing: "annual", pricing_url: "https://asana.com/pricing", note: "Free tier up to 10 seats"}
  - {name: "ClickUp", product: "ClickUp", entry_tier: "Unlimited", price_per_seat: 7, billing: "annual", pricing_url: "https://clickup.com/pricing", note: "Free Forever tier with storage limits"}
  - {name: "Linear", product: "Linear", entry_tier: "Basic", price_per_seat: 10, billing: "annual", pricing_url: "https://linear.app/pricing", note: "Free tier with limits on issues"}
  - {name: "monday.com", product: "monday work management", entry_tier: "Basic", price_per_seat: 9, billing: "annual", pricing_url: "https://monday.com/pricing", note: "Free for up to two seats; seat minimums on paid tiers"}
semantic_types: {name: Category, price_per_seat: Amount}
encodings:
  y: {field: name}
  x: {field: price_per_seat}
  color: {field: name, scheme: teals}
```

## Who charges what

<!-- data: Competitors.md#table:Competitors -->
| Name | Product | Entry tier | Price per seat | Billing | Note |
| --- | --- | --- | ---: | --- | --- |
| Asana | Asana | Starter | 10.99 | annual | Free tier up to 10 seats |
| ClickUp | ClickUp | Unlimited | 7 | annual | Free Forever tier with storage limits |
| Linear | Linear | Basic | 10 | annual | Free tier with limits on issues |
| monday.com | monday work management | Basic | 9 | annual | Free for up to two seats; seat minimums on paid tiers |

## Questions the comparison has not yet answered

<!-- data: Competitors.md#table:Features -->
| feature | us | Asana | ClickUp | Linear | monday.com |
| --- | --- | --- | --- | --- | --- |
| Free tier | yes | unknown | unknown | unknown | unknown |
| Timeline view | yes | unknown | unknown | unknown | unknown |
| Offline documents | yes | unknown | unknown | unknown | unknown |
| AI change review with approval | yes | unknown | unknown | unknown | unknown |
| Public API | planned | unknown | unknown | unknown | unknown |
| Self-hosted option | no | unknown | unknown | unknown | unknown |

## Captures

Everything you keep about a change: a dated note, a screenshot, a PDF of the page. The night lists the folder.

```flow-folder captures
| File | Size | Modified | Digest |
| --- | ---: | --- | --- |
| 2026-09-02 — Pricing pages, first read.md | 1065 |  |  |
```

Bundled file list; the inventory job fills timestamps and digests in your working copy.

## Turn a source change into a decision

1. Inspect the changed text and its public source. A fetch failure is not a price change.
2. Save the evidence you intend to rely on in `captures/`, including checked date, exact plan, currency, billing period and seat minimum.
3. Update [[Competitors]] only after reviewing the source. Bound views refresh from your authored values. Optional Overnight notes use the configured local model to describe the tables; verify any interpretation against the captures.
4. Record the response you chose and its owner in a note beside the evidence. A watch does not change another company's data or commit your team to a decision.

## Make it yours

1. Copy the entire **Competitor Watch** folder and add it in Flow. Its comparison and evidence note are local and readable without a network.
2. Before the first run, review the saved jobs in **File ▸ Night Shift Jobs…**. Public page watches are optional; remove them before running if you want local-only work. Add only the specific public pages you intend to read.
3. Open [[Competitors]] and choose **View ▸ Edit Table**. Change the example ClickUp price from 7 to 8 in **Competitors**, save, and mark it as a practice edit. After **Settings → Night Shift → Run now**, only its entry-price bar/table value should change. Restore the example or replace it with verified evidence.
4. Replace the fictional product, comparison rows and first-read note. Record dates and sources for every factual price or capability claim; leave unresolved cells unknown.
5. Review the run result; enable Night Shift only for scheduled updates. No Gather definition is needed for this direct-binding example; its numbers are the values you authored.

## How this page is built

| Block | Construct | Bound to | Redrawn by |
| --- | --- | --- | --- |
| Entry price | Bar Chart | `Competitors.md#table:Competitors` | the night alone |
| Who charges what | table | `Competitors.md#table:Competitors` | the night alone |
| Feature matrix | table | `Competitors.md#table:Features` | the night alone |
| Captures | `flow-folder` inventory | `captures/` | the night alone |
| Pricing pages | Source-watch job in the Jobs editor | four public pages | the night alone |

A watched page is digested as its text, not its markup, so a rotated tracking token is not a change and a new price is.

## Overnight notes
<!-- night: notes -->
<!-- /night: notes -->
