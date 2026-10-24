# Worked example — Visual Explainer

## Input

> When the app needs a product page it first asks the cache. If the cache
> has the page, it comes back in a few milliseconds. If not, that is a
> miss: the app reads the page from the database, which takes about 200
> ms, stores it in the cache with a ten-minute expiry, and returns it. The
> next request for the same page is a hit.

## Output

```figure
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 640 260" role="img" aria-label="The app asks the cache first; a miss reads the database, the page is stored in the cache for ten minutes, and the next request for it is a hit.">
  <title>A miss reads the database once, then the cache answers</title>
  <style>
    .box { fill: #ffffff; stroke: #8e8e93; stroke-width: 1.5 }
    .name { font: 600 15px system-ui, sans-serif; fill: #1d1d1f; text-anchor: middle }
    .label { font: 600 13px system-ui, sans-serif; fill: #1d1d1f }
    .line { font: 12px system-ui, sans-serif; fill: #6e6e73 }
    .flow { fill: none; stroke: #8e8e93; stroke-width: 2 }
    .hit { fill: none; stroke: #0a7aff; stroke-width: 3; stroke-dasharray: 6 4; animation: travel 1s linear infinite }
    @keyframes travel { to { stroke-dashoffset: -10 } }
  </style>
  <defs>
    <marker id="head" viewBox="0 0 10 10" refX="9" refY="5" markerWidth="7" markerHeight="7" orient="auto-start-reverse"><path d="M0 0 L10 5 L0 10 z" fill="#8e8e93"/></marker>
    <marker id="hit-head" viewBox="0 0 10 10" refX="9" refY="5" markerWidth="6" markerHeight="6" orient="auto-start-reverse"><path d="M0 0 L10 5 L0 10 z" fill="#0a7aff"/></marker>
  </defs>
  <rect width="640" height="260" rx="14" fill="#f5f5f7"/>
  <rect class="box" x="30" y="30" width="140" height="64" rx="10"/>
  <text class="name" x="100" y="67">App</text>
  <rect class="box" x="250" y="30" width="140" height="64" rx="10"/>
  <text class="name" x="320" y="67">Cache</text>
  <rect class="box" x="470" y="30" width="140" height="64" rx="10"/>
  <text class="name" x="540" y="67">Database</text>
  <g data-flow-step="1">
    <line class="flow" x1="170" y1="50" x2="246" y2="50" marker-end="url(#head)"/>
    <text class="label" x="30" y="150">1. Ask the cache first</text>
    <text class="line" x="30" y="168">It first asks the cache.</text>
  </g>
  <g data-flow-step="2">
    <path class="flow" d="M100 94 C100 122 540 122 540 98" marker-end="url(#head)"/>
    <text class="label" x="330" y="150">2. A miss reads the database</text>
    <text class="line" x="330" y="168">which takes about 200 ms</text>
  </g>
  <g data-flow-step="3">
    <line class="flow" x1="470" y1="62" x2="394" y2="62" marker-end="url(#head)"/>
    <text class="label" x="30" y="210">3. Stored in the cache</text>
    <text class="line" x="30" y="228">with a ten-minute expiry</text>
  </g>
  <g data-flow-step="4">
    <line class="hit" x1="170" y1="76" x2="244" y2="76" marker-end="url(#hit-head)"/>
    <text class="label" x="330" y="210">4. The next request is a hit</text>
    <text class="line" x="330" y="228">back in a few milliseconds</text>
  </g>
</svg>
```
