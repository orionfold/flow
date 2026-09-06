---
title: Holdings
tags: [portfolio, parameters, night-shift]
currency: USD
cash: 12500
benchmark: "^GSPC"
focus: NVDA
holdings:
  - {symbol: AAPL, shares: 40, cost: 267.61, bought: 2026-04-27}
  - {symbol: MSFT, shares: 18, cost: 424.82, bought: 2026-04-27}
  - {symbol: NVDA, shares: 60, cost: 216.61, bought: 2026-04-27}
  - {symbol: AMZN, shares: 35, cost: 261.12, bought: 2026-04-27}
  - {symbol: GOOGL, shares: 30, cost: 350.34, bought: 2026-04-27}
  - {symbol: META, shares: 12, cost: 678.62, bought: 2026-04-27}
  - {symbol: TSLA, shares: 20, cost: 378.67, bought: 2026-04-27}
  - {symbol: BRK-B, shares: 15, cost: 472.81, bought: 2026-04-27}
  - {symbol: AVGO, shares: 22, cost: 418.20, bought: 2026-04-27}
  - {symbol: JPM, shares: 25, cost: 311.63, bought: 2026-04-27}
macros:
  - {symbol: "^GSPC", name: S&P 500}
  - {symbol: "^IXIC", name: Nasdaq Composite}
  - {symbol: "^VIX", name: VIX}
  - {symbol: "^TNX", name: 10-year Treasury yield}
  - {symbol: "DX-Y.NYB", name: US dollar index}
  - {symbol: "GC=F", name: Gold}
  - {symbol: "CL=F", name: Crude oil}
  - {symbol: "BTC-USD", name: Bitcoin}
---
# Holdings

This is the one file you edit. The front matter above is the portfolio: every
line in `holdings` is a position, every line in `macros` is an indicator the
dashboard follows. [[Portfolio Dashboard]] reads this file each night and
redraws its holdings table from it, and the refresh script reads it to know
which prices to fetch.

## What each field means

| Field | What it is | Example |
| --- | --- | --- |
| `symbol` | The ticker as Yahoo Finance spells it. A class share uses a hyphen: `BRK-B`. | `NVDA` |
| `shares` | How many you hold. Fractions are fine: `12.5`. | `60` |
| `cost` | Your average cost per share, in `currency`. The dashboard's gain and loss figures are measured from it. | `118.75` |
| `bought` | When you bought, or when you last added. Kept for your own record; nothing computes on it. | `2025-11-20` |
| `cash` | Cash held beside the positions. Counted in the portfolio total, never charted. | `12500` |
| `benchmark` | The index the one-month line compares against. | `^GSPC` |
| `focus` | The one holding drawn as candlesticks. | `NVDA` |
| `macros` | The indicators in the macro table. Any Yahoo Finance symbol works: an index, a yield, a future, a currency pair. | `^TNX` |

## Make it yours

- **Add a stock.** Add a line under `holdings` in the same shape:
  `- {symbol: COST, shares: 8, cost: 912.00, bought: 2026-08-30}`. The
  next morning it is in the holdings table; the next refresh prices it.
- **Remove a stock.** Delete its line. That is all.
- **Change a lot.** Edit `shares` and `cost` in place. If you added to a
  position, put the new average cost.
- **Track a different indicator.** Replace a `macros` line. A currency pair
  is `EURUSD=X`; a sector fund is its ticker, `XLK`.

The example lots above are illustrative: real symbols at their real closing
prices on 27 April 2026, not a recommendation. Replace them with what you own.
