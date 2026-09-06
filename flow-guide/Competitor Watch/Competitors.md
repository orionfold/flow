---
title: Competitors
tags: [competitive, parameters, night-shift]
market: Team work management
us: Our product
competitors:
  - {name: Asana, product: Asana, entry_tier: Starter, price_per_seat: 10.99, billing: annual, pricing_url: "https://asana.com/pricing", note: "Free tier up to 10 seats"}
  - {name: ClickUp, product: ClickUp, entry_tier: Unlimited, price_per_seat: 7, billing: annual, pricing_url: "https://clickup.com/pricing", note: "Free Forever tier with storage limits"}
  - {name: Linear, product: Linear, entry_tier: Basic, price_per_seat: 10, billing: annual, pricing_url: "https://linear.app/pricing", note: "Free tier with limits on issues"}
  - {name: monday.com, product: monday work management, entry_tier: Basic, price_per_seat: 9, billing: annual, pricing_url: "https://monday.com/pricing", note: "Free for up to two seats; seat minimums on paid tiers"}
features:
  - {feature: Free tier, us: yes, Asana: yes, ClickUp: yes, Linear: yes, monday.com: yes}
  - {feature: Timeline view, us: yes, Asana: yes, ClickUp: yes, Linear: yes, monday.com: yes}
  - {feature: Offline documents, us: yes, Asana: no, ClickUp: no, Linear: no, monday.com: no}
  - {feature: AI change review with approval, us: yes, Asana: no, ClickUp: no, Linear: no, monday.com: no}
  - {feature: Public API, us: planned, Asana: yes, ClickUp: yes, Linear: yes, monday.com: yes}
  - {feature: Self-hosted option, us: no, Asana: no, ClickUp: no, Linear: no, monday.com: no}
---
# Competitors

The one file you edit. Each `competitors` line is a company, the tier a new
customer meets first, and the page where its price is published. Each
`features` line is one row of the comparison matrix. [[Competitor Watch]]
draws its table and chart from the first list and its matrix from the second,
every night.

## What each field means

| Field | What it is |
| --- | --- |
| `name`, `product` | The company and the product, when they differ. |
| `entry_tier`, `price_per_seat`, `billing` | The first paid tier and its published price per seat per month at the billing period you note. Read from the pricing page the day you wrote the line. |
| `pricing_url` | The public page the price came from. Put the same URL in `watch` on the dashboard so the night tells you when it changes. |
| `note` | One line: the free tier's limit, a seat minimum, a regional price. |
| `features` | One line per capability; each competitor's column is `yes`, `no`, `planned` or `partial`. |

## Make it yours

- **Track a competitor.** Add a `competitors` line and a column in every
  `features` line. Then add its pricing page to `watch` in
  [[Competitor Watch]].
- **Record a price change.** The night told you the page changed; read it,
  edit `price_per_seat` here, and the chart is current the next morning.
  Every capture of the page you want to keep goes in `captures/`.

The four companies are real; the prices were read from their public pricing
pages on 2 September 2026 and will drift. The feature matrix is an example
for a made-up product; replace the rows with the ones your market argues
about.
