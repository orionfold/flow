---
title: Portfolio Refresh
tags: [portfolio, definition, night-shift]
sources:
  settings: Holdings.md#table:Settings
  holdings: Holdings.md#table:Holdings
  macroList: Holdings.md#table:Macros
  prices:
    template: https://query1.finance.yahoo.com/v8/finance/chart/{symbol}?range=3mo&interval=1d
    over: holdings
    column: symbol
    key: chart.result.0
    columns: {timestamp: at, meta.gmtoffset: offset, indicators.quote.0.open: open, indicators.quote.0.high: high, indicators.quote.0.low: low, indicators.quote.0.close: close}
  names:
    template: https://query1.finance.yahoo.com/v8/finance/chart/{symbol}?range=1d&interval=1d
    over: holdings
    column: symbol
    key: chart.result.0.meta
  macroPrices:
    template: https://query1.finance.yahoo.com/v8/finance/chart/{symbol}?range=3mo&interval=1d
    over: macroList
    column: symbol
    key: chart.result.0
    columns: {timestamp: at, meta.gmtoffset: offset, indicators.quote.0.close: close}
  benchPrices:
    template: https://query1.finance.yahoo.com/v8/finance/chart/{symbol}?range=3mo&interval=1d
    over: settings
    column: value
    where: "key == 'benchmark'"
    key: chart.result.0
    columns: {timestamp: at, meta.gmtoffset: offset, indicators.quote.0.close: close}
  benchNames:
    template: https://query1.finance.yahoo.com/v8/finance/chart/{symbol}?range=1d&interval=1d
    over: settings
    column: value
    where: "key == 'benchmark'"
    key: chart.result.0.meta
derive:
  sessions:
    from: prices
    steps:
      - {filter: "close != ''"}
      - {calculate: "isoDate(at + offset)", as: day}
      - {sort: day}
  lastTwo:
    from: sessions
    steps:
      - {sample: 2, from: tail, by: [symbol]}
  priceQuotes:
    from: lastTwo
    steps:
      - {aggregate: symbol, first: close, last: close, count: close, as: [previous, price, sessionCount]}
  quotes:
    from: holdings
    steps:
      - {lookup: symbol, from: priceQuotes, on: symbol, fields: [previous, price, sessionCount]}
      - {lookup: symbol, from: names, on: symbol, fields: [longName]}
      - {calculate: "shares * price", as: value}
      - {calculate: "coalesce(sessionCount, 0) >= 2 ? shares * (price - previous) : number('')", as: dayGain}
      - {calculate: "shares * cost", as: basis}
      - {calculate: "shares * (price - cost)", as: gain}
      - {sort: value, descending: true}
  monthStart:
    from: sessions
    steps:
      - {sample: 22, from: tail, by: [symbol]}
      - {aggregate: symbol, first: close, last: close, count: close, as: [monthAgo, latest, monthCount]}
      - {lookup: symbol, from: holdings, on: symbol, fields: [shares]}
      - {calculate: "shares * monthAgo", as: thenValue}
      - {calculate: "shares * latest", as: nowValue}
  portfolioDays:
    from: sessions
    steps:
      - {lookup: symbol, from: holdings, on: symbol, fields: [shares]}
      - {calculate: "shares * close", as: value}
      - {aggregate: day, sum: value, count: symbol, as: [value, observedPositions]}
      - {filter: "observedPositions == positions"}
      - {sort: day}
      - {sample: 22, from: tail}
      - {joinaggregate: "", first: value, as: opening}
      - {calculate: "'Portfolio'", as: line}
      - {calculate: "round(value / opening * 100, 2)", as: indexed}
  benchSessions:
    from: benchPrices
    steps:
      - {filter: "close != ''"}
      - {calculate: "isoDate(at + offset)", as: day}
      - {sort: day}
      - {sample: 22, from: tail}
      - {joinaggregate: "", first: close, as: opening}
      - {lookup: value, from: benchNames, on: value, fields: [longName]}
      - {calculate: "longName", as: line}
      - {calculate: "round(close / opening * 100, 2)", as: indexed}
  benchMonth:
    from: benchSessions
    steps:
      - {aggregate: value, first: close, last: close, count: close, as: [monthAgo, latest, monthCount]}
  macroSessions:
    from: macroPrices
    steps:
      - {filter: "close != ''"}
      - {calculate: "isoDate(at + offset)", as: day}
      - {sort: day}
  macroMonth:
    from: macroSessions
    steps:
      - {sample: 22, from: tail, by: [symbol]}
      - {aggregate: symbol, first: close, last: close, count: close, as: [monthAgo, monthLatest, monthCount]}
  macroLastTwo:
    from: macroSessions
    steps:
      - {sample: 2, from: tail, by: [symbol]}
  macroQuotes:
    from: macroLastTwo
    steps:
      - {aggregate: symbol, first: close, last: close, count: close, as: [previous, level, sessionCount]}
  focusSessions:
    from: sessions
    steps:
      - {filter: "symbol == focus"}
      - {sample: 15, from: tail}
  opening:
    rows:
      - {step: Cost basis, change: "{round(totalCost, 0)}"}
  gains:
    from: quotes
    steps:
      - {calculate: "symbol", as: step}
      - {calculate: "coalesce(price, 0) > 0 ? round(gain, 0) : number('')", as: change}
      - {columns: [step, change]}
  closing:
    rows:
      - {step: Market value, change: "{round(totalValue, 0)}"}
  cashRow:
    rows:
      - {symbol: Cash, value: "{round(cash, 0)}"}
let:
  cash: {max: value, of: settings, where: "key == 'cash'"}
  benchmark: {max: value, of: settings, where: "key == 'benchmark'"}
  focus: {max: value, of: settings, where: "key == 'focus'"}
  currency: {max: value, of: settings, where: "key == 'currency'"}
  positions: {count: symbol, of: holdings}
  pricedPositions: {count: symbol, of: quotes, where: "coalesce(price, 0) > 0"}
  dayPositions: {count: symbol, of: quotes, where: "coalesce(sessionCount, 0) >= 2"}
  monthPositions: {count: symbol, of: monthStart, where: "monthCount == 22"}
  totalValue: {sum: value, of: quotes}
  totalCost: {sum: basis, of: quotes}
  totalDayChange: {sum: dayGain, of: quotes}
  monthThen: {sum: thenValue, of: monthStart}
  monthNow: {sum: nowValue, of: monthStart}
  portfolioMonth: "monthThen > 0 && monthPositions == positions ? round((monthNow / monthThen - 1) * 100, 1) : number('')"
  benchThen: {sum: monthAgo, of: benchMonth}
  benchNow: {sum: latest, of: benchMonth}
  benchmarkObservations: {sum: monthCount, of: benchMonth}
  benchmarkMonth: "benchThen > 0 && benchmarkObservations == 22 ? round((benchNow / benchThen - 1) * 100, 1) : number('')"
emit:
  currency: "{currency}"
  benchmark: "{benchmark}"
  focus: "{focus}"
  positions: "{positions}"
  coverage:
    - {Item: Declared holdings, Value: "{positions}"}
    - {Item: Holdings with a positive quote, Value: "{pricedPositions}"}
    - {Item: Missing quotes, Value: "{positions - pricedPositions}"}
    - {Item: Total basis, Value: "{positions == pricedPositions ? 'All declared holdings priced; latest daily bars' : 'Incomplete quotes; portfolio totals withheld'}"}
  summary:
    - {metric: Portfolio value, value: "{positions == pricedPositions ? round(totalValue + cash, 0) : number('')}", goal: "{round(totalCost + cash, 0)}"}
    - {metric: Day change, value: "{positions == dayPositions ? round(totalDayChange, 0) : number('')}"}
    - {metric: "Gain on cost, %", value: "{positions == pricedPositions && totalCost > 0 ? round((totalValue / totalCost - 1) * 100, 1) : number('')}"}
    - {metric: "One month, %", value: "{portfolioMonth}", goal: "{benchmarkMonth}"}
  holdings:
    from: quotes
    steps:
      - {calculate: "symbol", as: Symbol}
      - {calculate: "coalesce(longName, symbol)", as: Name}
      - {calculate: "shares", as: Shares}
      - {calculate: "coalesce(price, 0) > 0 ? round(price, 2) : number('')", as: Price}
      - {calculate: "coalesce(value, 0) > 0 ? round(value, 0) : number('')", as: Value}
      - {calculate: "coalesce(sessionCount, 0) >= 2 && coalesce(previous, 0) > 0 ? round((price / previous - 1) * 100, 2) : number('')", as: "Day %"}
      - {calculate: "round(cost, 2)", as: Cost}
      - {calculate: "coalesce(price, 0) > 0 && cost > 0 ? round((price / cost - 1) * 100, 1) : number('')", as: "Gain %"}
      - {calculate: "coalesce(price, 0) > 0 ? round(gain, 0) : number('')", as: Gain}
      - {calculate: "positions == pricedPositions && totalValue > 0 ? round(value / totalValue * 100, 1) : number('')", as: "Weight %"}
      - {columns: [Symbol, Name, Shares, Price, Value, "Day %", Cost, "Gain %", Gain, "Weight %"]}
  allocation:
    from: quotes
    steps:
      - {calculate: "symbol", as: symbol}
      - {calculate: "coalesce(value, 0) > 0 ? round(value, 0) : number('')", as: value}
      - {columns: [symbol, value]}
      - {concat: cashRow}
      - {filter: "positions == pricedPositions"}
  indexed:
    from: portfolioDays
    steps:
      - {concat: benchSessions}
      - {sort: day}
      - {columns: [day, line, indexed]}
  candles:
    from: focusSessions
    steps:
      - {calculate: "day", as: day}
      - {calculate: "round(open, 2)", as: open}
      - {calculate: "round(high, 2)", as: high}
      - {calculate: "round(low, 2)", as: low}
      - {calculate: "round(close, 2)", as: close}
      - {columns: [day, open, high, low, close]}
  macro:
    from: macroList
    steps:
      - {lookup: symbol, from: macroQuotes, on: symbol, fields: [previous, level, sessionCount]}
      - {lookup: symbol, from: macroMonth, on: symbol, fields: [monthAgo, monthLatest, monthCount]}
      - {calculate: "name", as: Indicator}
      - {calculate: "symbol", as: Symbol}
      - {calculate: "coalesce(sessionCount, 0) > 0 ? round(level, 2) : number('')", as: Level}
      - {calculate: "coalesce(sessionCount, 0) >= 2 && coalesce(previous, 0) != 0 ? round((level / previous - 1) * 100, 2) : number('')", as: "Day %"}
      - {calculate: "coalesce(monthCount, 0) == 22 && coalesce(monthAgo, 0) != 0 ? round((monthLatest / monthAgo - 1) * 100, 2) : number('')", as: "Month %"}
      - {columns: [Indicator, Symbol, Level, "Day %", "Month %"]}
  tenYear:
    from: macroSessions
    steps:
      - {filter: "symbol == '^TNX'"}
      - {calculate: "round(close, 3)", as: yield}
      - {columns: [day, yield]}
  bridge:
    from: opening
    steps:
      - {concat: gains}
      - {concat: closing}
      - {filter: "positions == pricedPositions"}
      - {columns: [step, change]}
---
# How this portfolio refreshes itself

This is the definition [[Portfolio Dashboard]] runs each night. It is **data, not code** — every line is something you can read and change, and Flow runs it itself rather than running a program. It reads [[Holdings]], fetches daily bars from the one address written below, and works out every table on the page.

## The four blocks

| Block | What it is for |
| --- | --- |
| `sources:` | What to read: [[Holdings]], and one Yahoo Finance address per symbol |
| `derive:` | Row sets worked out once — the sessions, the last two closes, the month |
| `let:` | Single values: the portfolio's total, its cost, its month against the benchmark |
| `emit:` | The tables the capture holds, one per chart and table in the document |

## `sources:` — one address, filled per holding

The `prices` source is a **template**: the address is written once with `{symbol}` in it, and Flow fills it from the `symbol` column of your holdings. You wrote the endpoint down; a symbol you add to [[Holdings]] is fetched the next night without asking again. Every filled address is checked against the one you wrote, so a value in the file cannot send Flow somewhere else.

`columns:` is there because a price API does not return rows. It returns a list of times and a list of closes that line up by position, and `columns:` says which list becomes which column. When one list is shorter than another — the session still open — the rows stop at the shorter one rather than inventing a price nothing quoted.

## `derive:` — the work done once

`sessions` is every daily bar with its date worked out. `isoDate` turns the seconds a price API stamps a bar with into a day, in UTC, adding the exchange's own offset from the same payload — so the bar lands on the day that exchange traded it.

`lastTwo` is each symbol's last two sessions. The `by: [symbol]` matters: without it the last two rows of the whole set are two rows of one holding, and nothing else gets priced. `quotes` then takes `first` and `last` of those two — the earlier close and the latest, **in the order they traded**, not the smaller and the larger, which would be backwards for every stock that fell.

## Two things worth knowing

**Dates are worked out in UTC, by arithmetic.** No calendar and no language settings enter this, so the same bars produce the same capture on any machine — which is what lets Flow tell a real change from a re-run.

**Every authored holding remains in the table when a fetched response has no price rows.** Its unpriced cells are empty; coverage names the gap and the total, weights, allocation and value bridge are withheld. An unavailable network request refuses the Gather and preserves the previous dated capture. Neither case establishes a current complete portfolio.

**A period needs enough observations.** Day changes require two available daily bars. The fields labelled one month use 22 available daily bars, not a calendar-month or transaction-based return; a shorter series leaves the change blank. The benchmark and macro indicators follow the same rules. A missing macro series retains its named row with blank values. Compare the dates in each indexed series before comparing their changes: symbols and markets can have different trading calendars.

## Making it yours

Edit [[Holdings]] rather than this file for anything ordinary — your positions, your cash, your benchmark, the indicators you follow. Come back here to add a table, change what a summary row measures, or read prices from somewhere else.
