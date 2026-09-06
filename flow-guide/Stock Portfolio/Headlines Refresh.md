---
title: Headlines Refresh
tags: [portfolio, definition, night-shift]
sources:
  holdings: Holdings.md#holdings
  feeds:
    template: https://feeds.finance.yahoo.com/rss/2.0/headline?s={symbol}
    over: holdings
    column: symbol
    as: feed
let:
  provenance: "'Yahoo Finance RSS headlines'"
emit:
  source: "{provenance}"
  headlines:
    from: feeds
    steps:
      - {sample: 3, from: head, by: [symbol]}
      - {calculate: "symbol", as: Symbol}
      - {calculate: "title", as: Headline}
      - {calculate: "host(link)", as: Source}
      - {calculate: "isoDay(published)", as: Published}
      - {columns: [Symbol, Headline, Source, Published]}
---
# How the headlines refresh themselves

This is the second definition [[Portfolio Dashboard]] runs each night, and it
writes the headlines table. It is separate from [[Portfolio Refresh]] because
it writes a **different capture**: the dashboard binds its prices to
`data/portfolio-*.json` and its headlines to `data/news-*.json`, and one
definition writes one capture. Two captures, two definitions, two jobs.

## What it does

| Block | What it is for |
| --- | --- |
| `sources:` | Your holdings, and one feed address per symbol |
| `emit:` | The headlines table, three per holding |

The feed address is a **template**, filled from the `symbol` column of your
holdings exactly as the prices are — you wrote the address once, and a symbol
you add to [[Holdings]] is followed the next night. `as: feed` says the answer
is a feed rather than a page of data, so Flow reads each item's title, link and
date and nothing else.

`by: [symbol]` on the sample is what makes it three per holding. Without it,
the first three of the whole set would all belong to the first symbol.

`isoDay(published)` turns a feed's own date — `Fri, 04 Sep 2026 11:07:39 +0000`
— into `2026-09-04`. It answers in UTC, always, so the same feed gives the same
capture wherever your Mac is; a date it cannot read shows nothing rather than
the wrong day.

`host(link)` is what turns `https://www.thestreet.com/a/b` into
`thestreet.com` — the site, which is what the table shows. It names one thing
and can do nothing else: there is no pattern language here, because a pattern
is code you would have to read as a program instead of as a sentence.

## Headlines are the publisher's words

Nothing here summarises, rewrites or judges a headline. The table shows what
the publisher wrote, with the site it came from, and links back to it. If a
feed says nothing on a given night, that holding simply has no rows — an empty
answer is an honest one.
