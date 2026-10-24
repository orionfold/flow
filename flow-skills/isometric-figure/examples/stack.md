# Worked example — Isometric Figure

## Input

> Our product rests on three layers. At the bottom, the data platform
> stores every customer event and keeps it for two years. On top of it, the
> model layer turns those events into forecasts each night. The app layer,
> on top, shows each team its forecast and lets them adjust it.

## Output

```figure
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 640 390" role="img" aria-label="Three layers: the data platform at the bottom stores every customer event, the model layer on it turns events into forecasts each night, and the app layer on top shows each team its forecast." data-flow-state="all data model app">
  <title>The product rests on three layers</title>
  <style>
    .slab { cursor: pointer; transition: transform 0.2s }
    .top { fill: #d6e6fb }
    .left { fill: #a9c8ef }
    .right { fill: #86afe3 }
    .slab path { stroke: #ffffff; stroke-width: 1 }
    .name { font: 600 13px system-ui, sans-serif; fill: #10324f; text-anchor: middle }
    .note { font: 13px system-ui, sans-serif; fill: #1d1d1f; visibility: hidden }
    .note-title { font-weight: 600 }
    .hint { font: 12px system-ui, sans-serif; fill: #6e6e73 }
    .data .slab-data, .model .slab-model, .app .slab-app { transform: translateY(-14px) }
    .data .slab-data .top, .model .slab-model .top, .app .slab-app .top { fill: #64a8ff }
    .data .note-data, .model .note-model, .app .note-app { visibility: visible }
    .data .hint, .model .hint, .app .hint { visibility: hidden }
  </style>
  <rect width="640" height="390" rx="14" fill="#f5f5f7"/>
  <g class="slab slab-data" data-flow-press="state=data" aria-label="The data platform">
    <path class="left" d="M60 280 L200 350 L200 372 L60 302 z"/>
    <path class="right" d="M200 350 L340 280 L340 302 L200 372 z"/>
    <path class="top" d="M200 210 l140 70 l-140 70 l-140 -70 z"/>
    <text class="name" x="200" y="322">Data platform</text>
  </g>
  <g class="slab slab-model" data-flow-press="state=model" aria-label="The model layer">
    <path class="left" d="M60 190 L200 260 L200 282 L60 212 z"/>
    <path class="right" d="M200 260 L340 190 L340 212 L200 282 z"/>
    <path class="top" d="M200 120 l140 70 l-140 70 l-140 -70 z"/>
    <text class="name" x="200" y="232">Model layer</text>
  </g>
  <g class="slab slab-app" data-flow-press="state=app" aria-label="The app layer">
    <path class="left" d="M60 100 L200 170 L200 192 L60 122 z"/>
    <path class="right" d="M200 170 L340 100 L340 122 L200 192 z"/>
    <path class="top" d="M200 30 l140 70 l-140 70 l-140 -70 z"/>
    <text class="name" x="200" y="142">App layer</text>
  </g>
  <text class="hint" x="380" y="200">Press a layer to read what it does.</text>
  <text class="note note-data" x="380" y="300"><tspan class="note-title">Data platform</tspan><tspan x="380" dy="20">Stores every customer event</tspan><tspan x="380" dy="18">and keeps it for two years.</tspan></text>
  <text class="note note-model" x="380" y="210"><tspan class="note-title">Model layer</tspan><tspan x="380" dy="20">Turns those events into</tspan><tspan x="380" dy="18">forecasts each night.</tspan></text>
  <text class="note note-app" x="380" y="120"><tspan class="note-title">App layer</tspan><tspan x="380" dy="20">Shows each team its forecast</tspan><tspan x="380" dy="18">and lets them adjust it.</tspan></text>
</svg>
```
