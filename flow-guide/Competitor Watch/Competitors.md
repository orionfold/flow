---
title: Competitors
tags: [competitive, parameters, night-shift]
---
# Competitive research inputs

**Illustrative business inputs.** Edit the named table using its **Open in the table editor** control. **View ▸ Edit Table** opens the first table. Save the input document, then run the Jobs on [[Competitor Watch]]; its refreshed views read these saved rows.

## Competitors

| name | product | entry_tier | price_per_seat | billing | pricing_url | note |
| --- | --- | --- | --- | --- | --- | --- |
| Asana | Asana | Starter | 10.99 | annual | https://asana.com/pricing | Free tier up to 10 seats |
| ClickUp | ClickUp | Unlimited | 7 | annual | https://clickup.com/pricing | Free Forever tier with storage limits |
| Linear | Linear | Basic | 10 | annual | https://linear.app/pricing | Free tier with limits on issues |
| monday.com | monday work management | Basic | 9 | annual | https://monday.com/pricing | Free for up to two seats; seat minimums on paid tiers |

## Features

| feature | us | Asana | ClickUp | Linear | monday.com |
| --- | --- | --- | --- | --- | --- |
| Free tier | yes | unknown | unknown | unknown | unknown |
| Timeline view | yes | unknown | unknown | unknown | unknown |
| Offline documents | yes | unknown | unknown | unknown | unknown |
| AI change review with approval | yes | unknown | unknown | unknown | unknown |
| Public API | planned | unknown | unknown | unknown | unknown |
| Self-hosted option | no | unknown | unknown | unknown | unknown |

## Settings

| key | value |
| --- | --- |
| market | Team work management |
| us | Our product |

## About these inputs

The one file you edit. Each **Competitors** row is a company, the tier a new customer meets first, and the page where its price is published. Each **Features** row is a capability in the comparison matrix. [[Competitor Watch]] draws its table and chart from the first list and its matrix from the second, every night.

## What each field means

| Field | What it is |
| --- | --- |
| `name`, `product` | The company and the product, when they differ. |
| `entry_tier`, `price_per_seat`, `billing` | The first paid tier and its published price per seat per month at the billing period you note. Read from the pricing page the day you wrote the line. |
| `pricing_url` | The public page the price came from. Add that URL to the source-watch job using **File ▸ Night Shift Jobs…** on [[Competitor Watch]]. |
| `note` | One line: the free tier's limit, a seat minimum, a regional price. |
| `features` | One line per capability; each competitor's column is `yes`, `no`, `planned`, `partial` or `unknown`. |

## Make it yours

- **Track a competitor.** Use the Table editor to add a **Competitors** row and a matching column in **Features**. Then open **File ▸ Night Shift Jobs…** on [[Competitor Watch]] to add the pricing page to its source watch.
- **Record a price change.** The night told you the page changed; read it, edit the `price_per_seat` cell in **Competitors** and save, and the chart is current the next morning. Every capture of the page you want to keep goes in `captures/`.

The four companies are real; the prices were read from their public pricing pages on 2 September 2026 and will drift. The feature matrix is a checklist for a fictional product, not a verified assessment of these competitors. Competitor capabilities remain unknown until you retain a source and tier-specific finding.
