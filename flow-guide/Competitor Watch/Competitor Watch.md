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

The market's published prices and the feature matrix your team argues about, kept current by the night. The pricing pages listed above are fetched each night and compared with the night before: a price that moves reaches you the next morning as the exact text that changed, and nothing else on those pages is kept. The tables and the chart are drawn from [[Competitors]].

## Entry price per seat

```chart data: Competitors.md#competitors
chartType: Bar Chart
title: First paid tier, per seat per month
subtitle: Published price at annual billing, $
source: Competitors.md, front matter
data:
  - {name: "Asana", product: "Asana", entry_tier: "Starter", price_per_seat: 10.99, billing: "annual", pricing_url: "https://asana.com/pricing", note: "Free tier up to 10 seats"}
  - {name: "ClickUp", product: "ClickUp", entry_tier: "Unlimited", price_per_seat: 7, billing: "annual", pricing_url: "https://clickup.com/pricing", note: "Free Forever tier with storage limits"}
  - {name: "Linear", product: "Linear", entry_tier: "Basic", price_per_seat: 10, billing: "annual", pricing_url: "https://linear.app/pricing", note: "Free tier with limits on issues"}
  - {name: "monday.com", product: "monday work management", entry_tier: "Basic", price_per_seat: 9, billing: "annual", pricing_url: "https://monday.com/pricing", note: "Free for up to two seats; seat minimums on paid tiers"}
semantic_types: {name: Category, price_per_seat: Amount}
encodings:
  y: {field: name}
  x: {field: price_per_seat}
```

## Who charges what

<!-- data: Competitors.md#competitors -->
| Name | Product | Entry tier | Price per seat | Billing | Note |
| --- | --- | --- | ---: | --- | --- |
| Asana | Asana | Starter | 10.99 | annual | Free tier up to 10 seats |
| ClickUp | ClickUp | Unlimited | 7 | annual | Free Forever tier with storage limits |
| Linear | Linear | Basic | 10 | annual | Free tier with limits on issues |
| monday.com | monday work management | Basic | 9 | annual | Free for up to two seats; seat minimums on paid tiers |

## The feature matrix

<!-- data: Competitors.md#features -->
| feature | us | Asana | ClickUp | Linear | monday.com |
| --- | --- | --- | --- | --- | --- |
| Free tier | yes | yes | yes | yes | yes |
| Timeline view | yes | yes | yes | yes | yes |
| Offline documents | yes | no | no | no | no |
| AI change review with approval | yes | no | no | no | no |
| Public API | planned | yes | yes | yes | yes |
| Self-hosted option | no | no | no | no | no |

## Captures

Everything you keep about a change: a dated note, a screenshot, a PDF of the page. The night lists the folder.

```flow-folder captures
| File | Size | Modified | Digest |
| --- | ---: | --- | --- |
| 2026-09-02 — Pricing pages, first read.md | 1065 | 2026-09-03T04:47:36Z | a00a48fc33fa |
```

## What you will see in the morning

- **A price moved.** A watched pricing page changed; the Briefing shows the text that changed. Edit `price_per_seat` in [[Competitors]] and the chart is current the next morning.
- **The page could not be reached.** The Briefing says so by name, once; nothing is guessed.
- **You changed the matrix.** A new row or a flipped cell shows in the morning with its diff.

## Make it yours

1. Edit the front matter of [[Competitors]]: your market, your competitors, the rows your team compares on.
2. Put each competitor's pricing page, and any changelog or status page you care about, in `watch` at the top of this page. Public `https` pages only; each fetch leaves a receipt.
3. Turn the Night Shift on: the moon in the title bar, or Settings ▸ Night Shift.

## How this page is built

| Block | Construct | Bound to | Redrawn by |
| --- | --- | --- | --- |
| Entry price | Bar Chart | `Competitors.md#competitors` | the night alone |
| Who charges what | table | `Competitors.md#competitors` | the night alone |
| Feature matrix | table | `Competitors.md#features` | the night alone |
| Captures | `flow-folder` inventory | `captures/` | the night alone |
| Pricing pages | `watch` in the `jobs:` block | four public pages | the night alone |

A watched page is digested as its text, not its markup, so a rotated tracking token is not a change and a new price is.

## Overnight notes
<!-- night: notes -->
<!-- /night: notes -->
