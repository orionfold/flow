# Worked example — Isometric Figure

## Input

> Our product rests on three layers. At the bottom, the data platform
> stores every customer event and keeps it for two years. On top of it, the
> model layer turns those events into forecasts each night. The app layer,
> on top, shows each team its forecast and lets them adjust it.

## Output

```figure
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 720 540" role="img" aria-label="Three layers: the data platform at the bottom stores every customer event, the model layer on it turns events into forecasts each night, and the app layer on top shows each team its forecast." data-flow-state="all data model app">
  <title>The product rests on three layers</title>
  <defs>
    <linearGradient id="sheen" x1="0" y1="0" x2="0" y2="1">
      <stop offset="0" stop-color="#ffffff" stop-opacity="0.7"/>
      <stop offset="0.6" stop-color="#ffffff" stop-opacity="0"/>
    </linearGradient>
  </defs>
  <style>
    .slab { cursor: pointer; transition: transform 0.2s }
    .slab path { stroke: #ffffff; stroke-opacity: 0.7; stroke-width: 1 }
    .top { fill-opacity: 0.85 }
    .sheen { fill: url(#sheen) }
    .c0 .top { fill: #d3f2ee } .c0 .left { fill: #2bb3a3; fill-opacity: 0.55 } .c0 .right { fill: #2bb3a3; fill-opacity: 0.8 } .c0 .obj { fill: #2bb3a3 }
    .c1 .top { fill: #e4defd } .c1 .left { fill: #7b61ff; fill-opacity: 0.55 } .c1 .right { fill: #7b61ff; fill-opacity: 0.8 } .c1 .obj { fill: #7b61ff }
    .c2 .top { fill: #d6e6fb } .c2 .left { fill: #2f80ed; fill-opacity: 0.55 } .c2 .right { fill: #2f80ed; fill-opacity: 0.8 } .c2 .obj { fill: #2f80ed }
    .obj { fill-opacity: 0.9 } .obj.alt { fill-opacity: 0.65 }
    .obj-top { fill: #ffffff; fill-opacity: 0.6 }
    .hole { fill: #ffffff; fill-opacity: 0.8 }
    .obj-line { stroke: #ffffff; stroke-width: 3; stroke-linecap: round; fill: none }
    .name { font: 600 13px system-ui, sans-serif; fill: #1d1d1f; text-anchor: middle }
    .note { font: 13px system-ui, sans-serif; fill: #1d1d1f; visibility: hidden }
    .note-title { font-weight: 600 }
    .hint { font: 12px system-ui, sans-serif; fill: #6e6e73 }
    .data .slab-data, .model .slab-model, .app .slab-app { transform: translateY(-14px) }
    .data .slab-data .top, .model .slab-model .top, .app .slab-app .top { fill-opacity: 1; stroke: #0a84ff; stroke-width: 2 }
    .data .note-data, .model .note-model, .app .note-app { visibility: visible }
    .data .hint, .model .hint, .app .hint { visibility: hidden }
    @media (prefers-color-scheme: dark) {
      .name, .note { fill: #f5f5f7 }
      .hint { fill: #98989d }
      .c0 .top { fill: #2bb3a3; fill-opacity: 0.35 }
      .c1 .top { fill: #7b61ff; fill-opacity: 0.35 }
      .c2 .top { fill: #2f80ed; fill-opacity: 0.35 }
    }
  </style>
  <g class="slab slab-data c0" data-flow-press="state=data" aria-label="Data platform">
    <path class="left" d="M70 400 L230 480 L230 500 L70 420 z"/>
    <path class="right" d="M230 480 L390 400 L390 420 L230 500 z"/>
    <path class="top" d="M230 320 l160 80 l-160 80 l-160 -80 z"/>
    <path class="sheen" d="M230 320 l160 80 l-160 80 l-160 -80 z"/>
    <path class="obj" d="M126 392 v-12 a24 12 0 0 0 48 0 v12 a24 12 0 0 1 -48 0 z"/>
    <path class="obj" d="M126 377 v-12 a24 12 0 0 0 48 0 v12 a24 12 0 0 1 -48 0 z"/>
    <path class="obj" d="M126 362 v-12 a24 12 0 0 0 48 0 v12 a24 12 0 0 1 -48 0 z"/>
    <ellipse class="obj-top" cx="150" cy="350" rx="24" ry="12"/>
    <text class="name" x="280" y="400">Data platform</text>
  </g>
  <g class="slab slab-model c1" data-flow-press="state=model" aria-label="Model layer">
    <path class="left" d="M70 260 L230 340 L230 360 L70 280 z"/>
    <path class="right" d="M230 340 L390 260 L390 280 L230 360 z"/>
    <path class="top" d="M230 180 l160 80 l-160 80 l-160 -80 z"/>
    <path class="sheen" d="M230 180 l160 80 l-160 80 l-160 -80 z"/>
    <g transform="matrix(1 0.5 -1 0.5 142 244)"><path class="obj" d="M21.6 -3.9 L21.6 3.9 L16.8 3.6 L14.4 9.3 L18.1 12.5 L12.5 18.1 L9.3 14.4 L3.6 16.8 L3.9 21.6 L-3.9 21.6 L-3.6 16.8 L-9.3 14.4 L-12.5 18.1 L-18.1 12.5 L-14.4 9.3 L-16.8 3.6 L-21.6 3.9 L-21.6 -3.9 L-16.8 -3.6 L-14.4 -9.3 L-18.1 -12.5 L-12.5 -18.1 L-9.3 -14.4 L-3.6 -16.8 L-3.9 -21.6 L3.9 -21.6 L3.6 -16.8 L9.3 -14.4 L12.5 -18.1 L18.1 -12.5 L14.4 -9.3 L16.8 -3.6 z"/><circle class="hole" r="7"/></g>
    <g transform="matrix(1 0.5 -1 0.5 172 264)"><path class="obj alt" d="M13.6 -3.3 L13.6 3.3 L10.5 3.1 L7.9 7.6 L9.7 10.1 L3.9 13.4 L2.6 10.6 L-2.6 10.6 L-3.9 13.4 L-9.7 10.1 L-7.9 7.6 L-10.5 3.1 L-13.6 3.3 L-13.6 -3.3 L-10.5 -3.1 L-7.9 -7.6 L-9.7 -10.1 L-3.9 -13.4 L-2.6 -10.6 L2.6 -10.6 L3.9 -13.4 L9.7 -10.1 L7.9 -7.6 L10.5 -3.1 z"/><circle class="hole" r="5"/></g>
    <text class="name" x="280" y="260">Model layer</text>
  </g>
  <g class="slab slab-app c2" data-flow-press="state=app" aria-label="App layer">
    <path class="left" d="M70 120 L230 200 L230 220 L70 140 z"/>
    <path class="right" d="M230 200 L390 120 L390 140 L230 220 z"/>
    <path class="top" d="M230 40 l160 80 l-160 80 l-160 -80 z"/>
    <path class="sheen" d="M230 40 l160 80 l-160 80 l-160 -80 z"/>
    <path class="obj" d="M124 118 l0 -40 l52 -18 l0 40 z"/>
    <path class="obj-line" d="M134 108 l0 -10 M145 104 l0 -16 M156 100 l0 -22 M167 96 l0 -12"/>
    <text class="name" x="280" y="120">App layer</text>
  </g>
  <text class="hint" x="430" y="260">Press a layer to read what it does.</text>
  <text class="note note-data" x="430" y="406"><tspan class="note-title">Data platform</tspan><tspan x="430" dy="20">Stores every customer event</tspan><tspan x="430" dy="18">and keeps it for two years.</tspan></text>
  <text class="note note-model" x="430" y="266"><tspan class="note-title">Model layer</tspan><tspan x="430" dy="20">Turns those events into</tspan><tspan x="430" dy="18">forecasts each night.</tspan></text>
  <text class="note note-app" x="430" y="126"><tspan class="note-title">App layer</tspan><tspan x="430" dy="20">Shows each team its forecast</tspan><tspan x="430" dy="18">and lets them adjust it.</tspan></text>
</svg>
```
