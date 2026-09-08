---
title: Portfolio Dashboard
tags: [portfolio, dashboard, night-shift]
jobs:
  - kind: gather
    definition: Portfolio Refresh.md
    into: data
    as: portfolio
  - kind: gather
    definition: Headlines Refresh.md
    into: data
    as: news
  - kind: keep-sources-fresh
    watch: [Holdings.md, data, https://www.federalreserve.gov/newsevents/pressreleases.htm]
  - kind: reconcile-against-folder
    folder: data
  - kind: overnight-notes
---
# Portfolio Dashboard

Ten widely held stocks, priced at the last close, with the indicators that move them and the headlines that explain the day. This is a living document: the `jobs:` block at the top is what the Night Shift does to it while you sleep, and every chart and table below is bound to a file in this folder, so the page redraws from data rather than being retyped. Change the portfolio in [[Holdings]]; the rest follows.

Prices come from [[Portfolio Refresh]] and the headlines from [[Headlines Refresh]] — two definitions Flow reads and runs itself before it redraws the page. They are **data, not code**: every line is something you can read and change, and no program runs. The Night Shift works out today's figures from them, redraws the page, watches this folder and the sources listed above, and leaves a receipt for each thing it did.

## At a glance

Value against what the positions cost; the month against the S&P 500.

```chart data: data/portfolio-*.json#summary
chartType: KPI Card
title: Portfolio at a glance
subtitle: Value and cost in dollars; the month against the benchmark, %
source: data/portfolio-*.json, newest capture
data:
  - {metric: "Portfolio value", value: 105761, goal: 103297}
  - {metric: "Day change", value: 613}
  - {metric: "Gain on cost, %", value: 2.7}
  - {metric: "One month, %", value: -1.3, goal: -0.9}
semantic_types: {metric: Category, value: Quantity, goal: Quantity}
encodings:
  metric: {field: metric}
  value: {field: value}
  goal: {field: goal}
```

## Holdings

Sorted by value. *Gain* is measured from the cost in [[Holdings]].

<!-- data: data/portfolio-*.json#holdings -->
| Symbol | Name | Shares | Price | Value | Day % | Cost | Gain % | Gain | Weight % |
| --- | --- | ---: | ---: | ---: | ---: | ---: | ---: | ---: | ---: |
| NVDA | NVIDIA Corporation | 60 | 224.41 | 13465 | 3.21 | 216.61 | 3.6 | 468 | 14.4 |
| AAPL | Apple Inc. | 40 | 324.96 | 12998 | -0.05 | 267.61 | 21.4 | 2294 | 13.9 |
| GOOGL | Alphabet Inc. | 30 | 337.12 | 10114 | 0.63 | 350.34 | -3.8 | -397 | 10.8 |
| MSFT | Microsoft Corporation | 18 | 496.82 | 8943 | -0.84 | 424.82 | 16.9 | 1296 | 9.6 |
| AMZN | Amazon.com, Inc. | 35 | 254.98 | 8924 | 0.02 | 261.12 | -2.4 | -215 | 9.6 |
| JPM | JPMorgan Chase & Co. | 25 | 356.22 | 8906 | 0.36 | 311.63 | 14.3 | 1115 | 9.5 |
| AVGO | Broadcom Inc. | 22 | 367.24 | 8079 | -0.66 | 418.2 | -12.2 | -1121 | 8.7 |
| BRK-B | Berkshire Hathaway Inc. | 15 | 505.24 | 7579 | 0.58 | 472.81 | 6.9 | 486 | 8.1 |
| TSLA | Tesla, Inc. | 20 | 357.01 | 7140 | 0.26 | 378.67 | -5.7 | -433 | 7.7 |
| META | Meta Platforms, Inc. | 12 | 592.85 | 7114 | 2.47 | 678.62 | -12.6 | -1029 | 7.6 |

## Allocation

```chart data: data/portfolio-*.json#allocation
chartType: Donut Chart
title: Where the money sits
subtitle: Market value by position, cash included
source: data/portfolio-*.json, newest capture
data:
  - {symbol: "NVDA", value: 13465}
  - {symbol: "AAPL", value: 12998}
  - {symbol: "GOOGL", value: 10114}
  - {symbol: "MSFT", value: 8943}
  - {symbol: "AMZN", value: 8924}
  - {symbol: "JPM", value: 8906}
  - {symbol: "AVGO", value: 8079}
  - {symbol: "BRK-B", value: 7579}
  - {symbol: "TSLA", value: 7140}
  - {symbol: "META", value: 7114}
  - {symbol: "Cash", value: 12500}
semantic_types: {symbol: Category, value: Amount}
encodings:
  size: {field: value}
  color: {field: symbol}
```

## One month against the benchmark

Both lines start at 100 on the first session of the window, so the gap is relative performance, not price.

```chart data: data/portfolio-*.json#indexed
chartType: Line Chart
title: Portfolio and benchmark, indexed to 100
subtitle: Last 22 sessions, daily closes
source: data/portfolio-*.json, newest capture
highlight: Portfolio
data:
  - {day: "2026-08-04", line: "Portfolio", indexed: 100}
  - {day: "2026-08-04", line: "S&P 500", indexed: 100}
  - {day: "2026-08-05", line: "Portfolio", indexed: 99.73}
  - {day: "2026-08-05", line: "S&P 500", indexed: 99.83}
  - {day: "2026-08-06", line: "Portfolio", indexed: 99.89}
  - {day: "2026-08-06", line: "S&P 500", indexed: 99.66}
  - {day: "2026-08-07", line: "Portfolio", indexed: 100.59}
  - {day: "2026-08-07", line: "S&P 500", indexed: 100.27}
  - {day: "2026-08-10", line: "Portfolio", indexed: 100.46}
  - {day: "2026-08-10", line: "S&P 500", indexed: 100.21}
  - {day: "2026-08-11", line: "Portfolio", indexed: 99.42}
  - {day: "2026-08-11", line: "S&P 500", indexed: 99.89}
  - {day: "2026-08-12", line: "Portfolio", indexed: 98.93}
  - {day: "2026-08-12", line: "S&P 500", indexed: 100.15}
  - {day: "2026-08-13", line: "Portfolio", indexed: 99.64}
  - {day: "2026-08-13", line: "S&P 500", indexed: 100.81}
  - {day: "2026-08-14", line: "Portfolio", indexed: 98.87}
  - {day: "2026-08-14", line: "S&P 500", indexed: 100.64}
  - {day: "2026-08-17", line: "Portfolio", indexed: 97.97}
  - {day: "2026-08-17", line: "S&P 500", indexed: 100.11}
  - {day: "2026-08-18", line: "Portfolio", indexed: 97.26}
  - {day: "2026-08-18", line: "S&P 500", indexed: 99.42}
  - {day: "2026-08-19", line: "Portfolio", indexed: 97.42}
  - {day: "2026-08-19", line: "S&P 500", indexed: 99.63}
  - {day: "2026-08-20", line: "Portfolio", indexed: 96.46}
  - {day: "2026-08-20", line: "S&P 500", indexed: 98.77}
  - {day: "2026-08-21", line: "Portfolio", indexed: 96.87}
  - {day: "2026-08-21", line: "S&P 500", indexed: 99.2}
  - {day: "2026-08-24", line: "Portfolio", indexed: 96.68}
  - {day: "2026-08-24", line: "S&P 500", indexed: 98.92}
  - {day: "2026-08-25", line: "Portfolio", indexed: 97.09}
  - {day: "2026-08-25", line: "S&P 500", indexed: 99.23}
  - {day: "2026-08-26", line: "Portfolio", indexed: 96.89}
  - {day: "2026-08-26", line: "S&P 500", indexed: 99.21}
  - {day: "2026-08-27", line: "Portfolio", indexed: 98.49}
  - {day: "2026-08-27", line: "S&P 500", indexed: 99.93}
  - {day: "2026-08-28", line: "Portfolio", indexed: 98.78}
  - {day: "2026-08-28", line: "S&P 500", indexed: 99.68}
  - {day: "2026-08-31", line: "Portfolio", indexed: 98.58}
  - {day: "2026-08-31", line: "S&P 500", indexed: 99.35}
  - {day: "2026-09-01", line: "Portfolio", indexed: 98.04}
  - {day: "2026-09-01", line: "S&P 500", indexed: 98.64}
  - {day: "2026-09-02", line: "Portfolio", indexed: 98.69}
  - {day: "2026-09-02", line: "S&P 500", indexed: 99.1}
semantic_types: {day: Date, line: Category, indexed: Quantity}
encodings:
  x: {field: day}
  y: {field: indexed}
  color: {field: line}
```

## The focus holding

The one position drawn bar by bar: `focus` in [[Holdings]].

```chart data: data/portfolio-*.json#candles
chartType: Candlestick Chart
title: The focus holding, last fifteen sessions
subtitle: Daily open, high, low, close, $
source: data/portfolio-*.json, newest capture
data:
  - {day: "2026-08-13", open: 225.06, high: 227.23, low: 223.71, close: 225.3}
  - {day: "2026-08-14", open: 226.77, high: 227.49, low: 224.5, close: 225.16}
  - {day: "2026-08-17", open: 225.98, high: 227.92, low: 224.86, close: 225.01}
  - {day: "2026-08-18", open: 220.45, high: 221.64, low: 218.69, close: 219.74}
  - {day: "2026-08-19", open: 221.67, high: 222.87, low: 216.76, close: 217.56}
  - {day: "2026-08-20", open: 218.36, high: 219.86, low: 215.66, close: 216.85}
  - {day: "2026-08-21", open: 218.42, high: 218.74, low: 214.5, close: 214.72}
  - {day: "2026-08-24", open: 215.53, high: 215.59, low: 207.25, close: 208.48}
  - {day: "2026-08-25", open: 211.03, high: 214.73, low: 210.11, close: 213.05}
  - {day: "2026-08-26", open: 212.64, high: 213.6, low: 209.23, close: 209.66}
  - {day: "2026-08-27", open: 222.86, high: 230.47, low: 220.9, close: 227.98}
  - {day: "2026-08-28", open: 227.36, high: 229.26, low: 216.81, close: 217.55}
  - {day: "2026-08-31", open: 218.87, high: 221.3, low: 216.21, close: 220.78}
  - {day: "2026-09-01", open: 216.75, high: 220.41, low: 215.1, close: 217.44}
  - {day: "2026-09-02", open: 218.79, high: 227.95, low: 218.48, close: 224.41}
semantic_types: {day: Date, open: Price, high: Price, low: Price, close: Price}
encodings:
  x: {field: day}
  open: {field: open}
  high: {field: high}
  low: {field: low}
  close: {field: close}
```

## Where the gain came from

From what the positions cost to what they are worth, one step per holding.

```chart data: data/portfolio-*.json#bridge
chartType: Waterfall Chart
title: Cost basis to market value
subtitle: Gain or loss per position, $
source: data/portfolio-*.json, newest capture
data:
  - {step: "Cost basis", change: 90797}
  - {step: "NVDA", change: 468}
  - {step: "AAPL", change: 2294}
  - {step: "GOOGL", change: -397}
  - {step: "MSFT", change: 1296}
  - {step: "AMZN", change: -215}
  - {step: "JPM", change: 1115}
  - {step: "AVGO", change: -1121}
  - {step: "BRK-B", change: 486}
  - {step: "TSLA", change: -433}
  - {step: "META", change: -1029}
  - {step: "Market value", change: 93261}
semantic_types: {step: Category, change: Amount}
encodings:
  x: {field: step}
  y: {field: change}
```

## Macro

The indicators in `macros` in [[Holdings]]: level at the last close, and the day's and month's move.

<!-- data: data/portfolio-*.json#macro -->
| Indicator | Symbol | Level | Day % | Month % |
| --- | --- | ---: | ---: | ---: |
| S&P 500 | ^GSPC | 7666.6 | 0.46 | -0.9 |
| Nasdaq Composite | ^IXIC | 26217.83 | 0.45 | -1.38 |
| VIX | ^VIX | 15.2 | -6.98 | -7.88 |
| 10-year Treasury yield | ^TNX | 4.8 | 0 | 3.65 |
| US dollar index | DX-Y.NYB | 99.41 | -0.15 | -0.28 |
| Gold | GC=F | 4480.3 | 2.61 | 5.52 |
| Crude oil | CL=F | 90.78 | -0.25 | 20.69 |
| Bitcoin | BTC-USD | 77567.39 | 0.21 | 22.34 |

```chart data: data/portfolio-*.json#tenYear
chartType: Sparkline
title: 10-year Treasury yield, last three months
source: data/portfolio-*.json, newest capture
data:
  - {day: "2026-06-02", yield: 4.455}
  - {day: "2026-06-03", yield: 4.491}
  - {day: "2026-06-04", yield: 4.477}
  - {day: "2026-06-05", yield: 4.536}
  - {day: "2026-06-08", yield: 4.552}
  - {day: "2026-06-09", yield: 4.528}
  - {day: "2026-06-10", yield: 4.542}
  - {day: "2026-06-11", yield: 4.463}
  - {day: "2026-06-12", yield: 4.487}
  - {day: "2026-06-15", yield: 4.469}
  - {day: "2026-06-16", yield: 4.428}
  - {day: "2026-06-17", yield: 4.463}
  - {day: "2026-06-18", yield: 4.451}
  - {day: "2026-06-22", yield: 4.509}
  - {day: "2026-06-23", yield: 4.493}
  - {day: "2026-06-24", yield: 4.402}
  - {day: "2026-06-25", yield: 4.392}
  - {day: "2026-06-26", yield: 4.372}
  - {day: "2026-06-29", yield: 4.374}
  - {day: "2026-06-30", yield: 4.418}
  - {day: "2026-07-01", yield: 4.475}
  - {day: "2026-07-02", yield: 4.485}
  - {day: "2026-07-06", yield: 4.479}
  - {day: "2026-07-07", yield: 4.529}
  - {day: "2026-07-08", yield: 4.569}
  - {day: "2026-07-09", yield: 4.539}
  - {day: "2026-07-10", yield: 4.569}
  - {day: "2026-07-13", yield: 4.609}
  - {day: "2026-07-14", yield: 4.585}
  - {day: "2026-07-15", yield: 4.545}
  - {day: "2026-07-16", yield: 4.569}
  - {day: "2026-07-17", yield: 4.541}
  - {day: "2026-07-20", yield: 4.598}
  - {day: "2026-07-21", yield: 4.628}
  - {day: "2026-07-22", yield: 4.657}
  - {day: "2026-07-23", yield: 4.703}
  - {day: "2026-07-24", yield: 4.679}
  - {day: "2026-07-27", yield: 4.641}
  - {day: "2026-07-28", yield: 4.604}
  - {day: "2026-07-29", yield: 4.622}
  - {day: "2026-07-30", yield: 4.663}
  - {day: "2026-07-31", yield: 4.745}
  - {day: "2026-08-03", yield: 4.686}
  - {day: "2026-08-04", yield: 4.627}
  - {day: "2026-08-05", yield: 4.617}
  - {day: "2026-08-06", yield: 4.67}
  - {day: "2026-08-07", yield: 4.66}
  - {day: "2026-08-10", yield: 4.699}
  - {day: "2026-08-11", yield: 4.684}
  - {day: "2026-08-12", yield: 4.682}
  - {day: "2026-08-13", yield: 4.641}
  - {day: "2026-08-14", yield: 4.696}
  - {day: "2026-08-17", yield: 4.724}
  - {day: "2026-08-18", yield: 4.706}
  - {day: "2026-08-19", yield: 4.653}
  - {day: "2026-08-20", yield: 4.696}
  - {day: "2026-08-21", yield: 4.738}
  - {day: "2026-08-24", yield: 4.704}
  - {day: "2026-08-25", yield: 4.639}
  - {day: "2026-08-26", yield: 4.664}
  - {day: "2026-08-27", yield: 4.672}
  - {day: "2026-08-28", yield: 4.72}
  - {day: "2026-08-31", yield: 4.758}
  - {day: "2026-09-01", yield: 4.796}
  - {day: "2026-09-02", yield: 4.796}
semantic_types: {day: Date, yield: Percentage}
encodings:
  x: {field: day}
  y: {field: yield}
```

## Headlines

Three per holding, from Yahoo Finance's per-symbol feed, newest capture. Headlines are the publisher's words, not Flow's.

<!-- data: data/news-*.json#headlines -->
| Symbol | Headline | Source | Published |
| --- | --- | --- | --- |
| AAPL | Warren Buffett’s biggest bet has a dividend secret | thestreet.com | 2026-09-02 |
| AAPL | Apple's new CEO faces his first big test | thestreet.com | 2026-09-02 |
| AAPL | Apple May Need a Foldable iPhone to Avoid a Revenue Slowdown Next Year | finance.yahoo.com | 2026-09-02 |
| MSFT | Steve Ballmer banned, Clippers fined $30M over Kawhi Leonard scandal | finance.yahoo.com | 2026-09-02 |
| MSFT | Bank of America resets Microsoft stock price target for 2026 | thestreet.com | 2026-09-02 |
| MSFT | US Stock Futures Rangebound After S&P 500, Dow Snap Three-Day Losing Streak As Oil Steadies — MSFT, DELL, UBER, ASTS, AVGO In Focus | stocktwits.com | 2026-09-02 |
| NVDA | Does Caterpillar’s AI Robotics Push with FieldAI and NVIDIA Reshape the Bull Case for CAT? | finance.yahoo.com | 2026-09-02 |
| NVDA | Billionaire Dan Loeb Exited Nvidia and Broadcom. Is He Calling the Top in AI Chips? | finance.yahoo.com | 2026-09-02 |
| NVDA | Bridgewater Cut Nvidia 18% and More Than Doubled Vistra. Is It Rotating From Chips to Power? | finance.yahoo.com | 2026-09-02 |
| AMZN | Better High-Growth Stock for 2026: Amazon.com vs. Uber Technologies | fool.com | 2026-09-02 |
| AMZN | Zoox vs. Waymo: Are Amazon and Alphabet Ready to Win the Robotaxi Race? | finance.yahoo.com | 2026-09-02 |
| AMZN | Stanley Druckenmiller Increased Amazon More Than 10-Fold and Opened an AMD Position. What’s the Common Bet? | finance.yahoo.com | 2026-09-02 |
| GOOGL | Sundar Pichai's Alphabet Has Grown Google Cloud Revenue 82% Year Over Year. Here's Why That Growth Rate Justifies the Company's Capex Bet. | fool.com | 2026-09-02 |
| GOOGL | MGNI Stock Heads For Another Green Week: Analyst Says Google AdTech Ruling Opens Door To Bigger Opportunity | stocktwits.com | 2026-09-02 |
| GOOGL | Here's Why Eos Energy Stock Soared Today | fool.com | 2026-09-02 |
| META | META Stock Jumps To Best Day In Nearly A Month — Meta Platforms Unveils Most Powerful AI Model To Compete With AI Rivals | stocktwits.com | 2026-09-02 |
| META | Edwards Lifesciences to Present at the Deutsche Bank Healthcare Summit | finance.yahoo.com | 2026-09-02 |
| META | US judge rejects bid to break up Google's ad business | finance.yahoo.com | 2026-09-02 |
| TSLA | Tesla's Cybercab to take center stage at Austin event | finance.yahoo.com | 2026-09-02 |
| TSLA | Tesla uses data transparency to get what it wants | thestreet.com | 2026-09-02 |
| TSLA | Dow Jones Futures: Snowflake, Broadcom, HPE Are Big Earnings Movers; Tesla Cybercab Event Due | finance.yahoo.com | 2026-09-02 |
| BRK-B | Berkshire Is Making a Big Bet on Google. This Is Why, According to CEO Greg Abel | investopedia.com | 2026-09-02 |
| BRK-B | MicroStrategy Reserve Capital Beats All S&P 500 Financials But Berkshire, MSTR Still Slips | beincrypto.com | 2026-09-02 |
| BRK-B | What Is Berkshire Hathaway (BRK.A) Signaling About AI Under Greg Abel? | finance.yahoo.com | 2026-09-02 |
| AVGO | Broadcom stock wavers as chipmaker's strong results 'not enough to keep investors happy' | finance.yahoo.com | 2026-09-02 |
| AVGO | Billionaire Dan Loeb Exited Nvidia and Broadcom. Is He Calling the Top in AI Chips? | finance.yahoo.com | 2026-09-02 |
| AVGO | Dow Jones Futures: Snowflake, Broadcom, HPE Are Big Earnings Movers; Tesla Cybercab Event Due | finance.yahoo.com | 2026-09-02 |
| JPM | JPMorgan executive reveals what AI projects must prove to win funding | thestreet.com | 2026-09-02 |
| JPM | JPMorgan scales back Jane Street financing amid growing bond market rivalry - FT | finance.yahoo.com | 2026-09-02 |
| JPM | J.P. Morgan Asset Management Announces Rebrand of Campbell Global to J.P. Morgan Natural Capital | finance.yahoo.com | 2026-09-02 |

## What you declared

Read straight from the front matter of [[Holdings]] each night. Edit a lot there and this table is current in the morning, with no refresh at all.

<!-- data: Holdings.md#holdings -->
| Symbol | Shares | Cost | Bought |
| --- | ---: | ---: | --- |
| AAPL | 40 | 267.61 | 2026-04-27 |
| MSFT | 18 | 424.82 | 2026-04-27 |
| NVDA | 60 | 216.61 | 2026-04-27 |
| AMZN | 35 | 261.12 | 2026-04-27 |
| GOOGL | 30 | 350.34 | 2026-04-27 |
| META | 12 | 678.62 | 2026-04-27 |
| TSLA | 20 | 378.67 | 2026-04-27 |
| BRK-B | 15 | 472.81 | 2026-04-27 |
| AVGO | 22 | 418.20 | 2026-04-27 |
| JPM | 25 | 311.63 | 2026-04-27 |

## Captures in this folder

The Night Shift keeps this inventory of `data/` current: every refresh adds a dated capture, and the morning names the new file.

```flow-folder data
| File | Size | Modified | Digest |
| --- | ---: | --- | --- |
| news-2026-09-02.json | 6305 | 2026-09-03T04:35:44Z | 929b480d7785 |
| portfolio-2026-09-02.json | 15308 | 2026-09-03T18:12:36Z | b58346fc7d14 |
```

## What you will see in the morning

- **Holdings changed.** You added a stock to [[Holdings]] in the evening; the *What you declared* table shows it, and the Morning Briefing shows the exact diff of the file.
- **A new capture landed.** The refresh ran at 01:30; every chart and table above redrew from it, the inventory grew by two files, and the Briefing carries the redrawn KPI card as its snapshot.
- **The Fed said something.** The press-release page changed overnight; the Briefing shows what text changed. Only the pages you list are fetched, and each fetch has a receipt.
- **Nothing moved.** An honest empty morning: the run is in Receipts, the page is untouched.

## Make it yours

1. Edit the front matter of [[Holdings]]: your symbols, shares and costs.
2. Use Run now (the moon in the title bar). Flow works out today's figures from [[Portfolio Refresh]] and [[Headlines Refresh]], writes a capture into `data/`, and redraws the page from what it wrote. Every run is in Receipts.
3. Turn the Night Shift on: the moon in the title bar, or Settings ▸ Night Shift. Every night the refresh runs first, then the page redraws.

## How this page is built

A case study in the constructs, so you can lift any of them into your own document.

| Block | Construct | Bound to | Redrawn by |
| --- | --- | --- | --- |
| At a glance | KPI Card chart | `data/portfolio-*.json#summary` | refresh, then the night |
| Holdings | table under a `data:` comment | `data/portfolio-*.json#holdings` | refresh, then the night |
| Allocation | Donut Chart | `#allocation` | refresh, then the night |
| One month | Line Chart, indexed | `#indexed` | refresh, then the night |
| Focus holding | Candlestick Chart | `#candles` | refresh, then the night |
| Gain bridge | Waterfall Chart | `#bridge` | refresh, then the night |
| Macro | table and a Sparkline | `#macro`, `#tenYear` | refresh, then the night |
| Headlines | table | `data/news-*.json#headlines` | refresh, then the night |
| What you declared | table | `Holdings.md#holdings` | the night alone |
| Captures | `flow-folder` inventory | `data/` | the night alone |

A binding is a path relative to this document. A `*` in the file name takes the newest capture by name, which is why the captures are dated. `#key` names the list inside the file. The night rewrites only the rows; the titles, the column alignment and the chart type are yours.

## Overnight notes
<!-- night: notes -->
<!-- /night: notes -->
