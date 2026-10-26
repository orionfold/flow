# Worked example — Field-Notes Diagram

## Input

> A product page takes 2.4 seconds to load. Looking up the address takes
> 0.1 s, opening the connection and its encryption 0.3 s, and the server
> takes 1.2 s to answer. Downloading the images and scripts then takes
> 0.5 s, and drawing the page 0.3 s. The server's answer is half of the
> wait, and it is the part worth fixing first.

## Output

```figure
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 600 400" role="img" aria-label="A 2.4 second page load: address lookup 0.1 s, connection and encryption 0.3 s, server answer 1.2 s, downloads 0.5 s, drawing 0.3 s. The server's 1.2 s is half the wait.">
  <title>The server's answer is half of a 2.4 s page load</title>
  <style>
    .eyebrow { font: 600 15px ui-monospace, Menlo, monospace; letter-spacing: 0.18em; fill: #5b6170; text-anchor: middle }
    .label { font: 600 16px ui-monospace, Menlo, monospace; fill: #1d2230 }
    .thesis-label { font: 700 16px ui-monospace, Menlo, monospace; fill: #0e9e98 }
    .value { font: 13px ui-monospace, Menlo, monospace; fill: #5b6170 }
    .bar { fill: url(#plain); stroke: #2b5fc4; stroke-width: 1; transform-box: fill-box; transform-origin: left center }
    .thesis { fill: url(#primary); stroke: #0e9e98; stroke-width: 2; transform-box: fill-box; transform-origin: left center }
    .wash { fill: #0e9e98; fill-opacity: 0.08 }
    .rule { stroke: #5b6170; stroke-width: 1; stroke-dasharray: 4 6 }
    .anchor { font: 13px ui-monospace, Menlo, monospace; letter-spacing: 0.08em; fill: #5b6170 }
    .plain-top { stop-color: #2b5fc4; stop-opacity: 0.42 }
    .plain-bottom { stop-color: #2b5fc4; stop-opacity: 0.14 }
    .primary-top { stop-color: #0e9e98; stop-opacity: 0.55 }
    .primary-bottom { stop-color: #0e9e98; stop-opacity: 0.18 }
    @media (prefers-color-scheme: dark) {
      .eyebrow, .value, .anchor { fill: #8b929c }
      .label { fill: #e9ecf0 }
      .thesis-label, .wash { fill: #14c8c0 }
      .bar { stroke: #7aa2f7 }
      .thesis { stroke: #14c8c0 }
      .rule { stroke: #8b929c }
      .plain-top, .plain-bottom { stop-color: #7aa2f7 }
      .primary-top, .primary-bottom { stop-color: #14c8c0 }
    }
    @media (prefers-reduced-motion: no-preference) {
      g:not(.flow-figure-ahead) .bar, g:not(.flow-figure-ahead) .thesis { animation: grow 0.6s cubic-bezier(0.2, 0.8, 0.2, 1) both }
      g:not(.flow-figure-ahead) .rise { animation: rise 0.5s ease-out both }
      g:not(.flow-figure-ahead) .d1 { animation-delay: 0.1s }
      g:not(.flow-figure-ahead) .d2 { animation-delay: 0.2s }
      g:not(.flow-figure-ahead) .d3 { animation-delay: 0.3s }
      g:not(.flow-figure-ahead) .d4 { animation-delay: 0.4s }
    }
    @keyframes grow { from { transform: scaleX(0) } }
    @keyframes rise { from { opacity: 0; transform: translateY(12px) } }
  </style>
  <defs>
    <linearGradient id="plain" x1="0" y1="0" x2="0" y2="1"><stop class="plain-top" offset="0"/><stop class="plain-bottom" offset="1"/></linearGradient>
    <linearGradient id="primary" x1="0" y1="0" x2="0" y2="1"><stop class="primary-top" offset="0"/><stop class="primary-bottom" offset="1"/></linearGradient>
  </defs>
  <text class="eyebrow" x="300" y="44">WHERE A 2.4 S PAGE LOAD GOES</text>
  <g data-flow-step="1">
    <text class="label rise" x="24" y="106">Address lookup</text>
    <rect class="bar" x="200" y="87" width="27.5" height="26" rx="3"/>
    <text class="value rise" x="237.5" y="105">0.1 s</text>
    <text class="label rise d1" x="24" y="156">Connection</text>
    <rect class="bar d1" x="200" y="137" width="82.5" height="26" rx="3"/>
    <text class="value rise d1" x="292.5" y="155">0.3 s</text>
    <text class="label rise d2" x="24" y="256">Downloads</text>
    <rect class="bar d2" x="200" y="237" width="137.5" height="26" rx="3"/>
    <text class="value rise d2" x="347.5" y="255">0.5 s</text>
    <text class="label rise d3" x="24" y="306">Drawing</text>
    <rect class="bar d3" x="200" y="287" width="82.5" height="26" rx="3"/>
    <text class="value rise d3" x="292.5" y="305">0.3 s</text>
  </g>
  <g data-flow-step="2">
    <rect class="wash" x="12" y="178" width="576" height="44" rx="4"/>
    <text class="thesis-label rise" x="24" y="206">Server answer</text>
    <rect class="thesis" x="200" y="187" width="330" height="26" rx="3"/>
    <text class="value rise" x="540" y="205">1.2 s</text>
    <line class="rule" x1="24" y1="345" x2="576" y2="345"/>
    <text class="anchor rise d4" x="24" y="375">SERVER ANSWER: 1.2 OF 2.4 S, HALF THE WAIT</text>
  </g>
</svg>
```
