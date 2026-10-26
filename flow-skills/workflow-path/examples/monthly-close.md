# Worked example — Workflow Path

## Input

> At the start of each month I export the client's bank statement as a CSV
> and gather the receipts they emailed as PDFs. I reconcile both against
> the client's ledger and flag anything that does not match. Then I send
> the client a one-page summary as a PDF and the updated ledger as a
> spreadsheet.

## Output

```figure
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 656 220" role="img" aria-label="The bank statement, the receipts and the ledger are reconciled, mismatches are flagged, and the client is sent a one-page summary and the updated ledger.">
  <title>The month's files become a summary and an updated ledger</title>
  <style>
    .file { fill: none; stroke: #5aa1b0; stroke-width: 1.5; stroke-linejoin: round }
    .ext { font: 700 12px system-ui, sans-serif; fill: #5aa1b0; text-anchor: middle }
    .name { font: 12px system-ui, sans-serif; fill: #6e6e73; text-anchor: middle }
    .arrow { fill: none; stroke: rgb(48, 176, 199); stroke-width: 2; stroke-linecap: round }
    .head { fill: rgb(48, 176, 199) }
    .act { fill: rgb(48, 176, 199) }
    .page { fill: rgb(48, 176, 199); fill-opacity: 0.13; stroke: rgb(48, 176, 199); stroke-width: 1.5 }
    .md { font: 700 12px system-ui, sans-serif; fill: #6e6e73 }
    .text-line { fill: rgb(48, 176, 199); fill-opacity: 0.45 }
    .cite { fill: rgb(48, 176, 199) }
    .caption { font: 600 14px system-ui, sans-serif; fill: #1d1d1f }
    @media (prefers-color-scheme: dark) {
      .file { stroke: #68b2c2 }
      .ext { fill: #68b2c2 }
      .name, .md { fill: #98989d }
      .arrow { stroke: rgb(64, 200, 224) }
      .head, .act, .cite, .text-line { fill: rgb(64, 200, 224) }
      .page { fill: rgb(64, 200, 224); stroke: rgb(64, 200, 224) }
      .caption { fill: #f5f5f7 }
    }
    @media (prefers-reduced-motion: no-preference) {
      .arrow { stroke-dasharray: 6 4; animation: travel 1s linear infinite }
    }
    @keyframes travel { to { stroke-dashoffset: -10 } }
  </style>
  <defs>
    <symbol id="file" viewBox="0 0 46 52"><path class="file" d="M2 2 H30 L44 16 V50 H2 Z M30 2 V16 H44"/></symbol>
    <symbol id="check" viewBox="0 0 28 28"><path d="M8 14.5 L12.5 19 L20 9.5" fill="none" stroke="#ffffff" stroke-width="2.4" stroke-linecap="round" stroke-linejoin="round"/></symbol>
    <symbol id="plane" viewBox="0 0 28 28"><path d="M6.5 13.5 L21.5 7 L16.5 21.5 L13.5 15 Z M13.5 15 L21.5 7" fill="none" stroke="#ffffff" stroke-width="1.8" stroke-linejoin="round"/></symbol>
    <marker id="tip" viewBox="0 0 10 10" refX="8" refY="5" markerWidth="6" markerHeight="6" orient="auto"><path class="head" d="M0 0 L10 5 L0 10 z"/></marker>
  </defs>
  <g data-flow-step="1">
    <use href="#file" x="21" y="70" width="46" height="52"/>
    <text class="ext" x="44" y="112">CSV</text>
    <text class="name" x="44" y="142">statement</text>
    <use href="#file" x="85" y="70" width="46" height="52"/>
    <text class="ext" x="108" y="112">PDF</text>
    <text class="name" x="108" y="142">receipts</text>
    <use href="#file" x="149" y="70" width="46" height="52"/>
    <text class="ext" x="172" y="112">XLSX</text>
    <text class="name" x="172" y="142">ledger</text>
    <text class="caption" x="24" y="192">Statement, receipts, ledger</text>
  </g>
  <g data-flow-step="2">
    <line class="arrow" x1="200" y1="96" x2="230" y2="96"/>
    <rect class="act" x="236" y="82" width="28" height="28" rx="8"/>
    <use href="#check" x="236" y="82" width="28" height="28"/>
    <line class="arrow" x1="270" y1="96" x2="302" y2="96" marker-end="url(#tip)"/>
    <text class="name" x="250" y="132">Reconcile</text>
  </g>
  <g data-flow-step="3">
    <rect class="page" x="312" y="41" width="90" height="110" rx="7"/>
    <text class="md" x="321" y="60">M↓</text>
    <rect class="text-line" x="321" y="74" width="66" height="5" rx="2.5"/>
    <rect class="text-line" x="321" y="88" width="54" height="5" rx="2.5"/>
    <rect class="text-line" x="321" y="102" width="66" height="5" rx="2.5"/>
    <rect class="text-line" x="321" y="116" width="54" height="5" rx="2.5"/>
    <circle class="cite" cx="393" cy="76.5" r="2.5"/>
    <circle class="cite" cx="393" cy="104.5" r="2.5"/>
    <text class="caption" x="357" y="192" text-anchor="middle">Mismatches flagged</text>
  </g>
  <g data-flow-step="4">
    <line class="arrow" x1="412" y1="96" x2="444" y2="96"/>
    <rect class="act" x="450" y="82" width="28" height="28" rx="8"/>
    <use href="#plane" x="450" y="82" width="28" height="28"/>
    <line class="arrow" x1="484" y1="96" x2="516" y2="96" marker-end="url(#tip)"/>
    <text class="name" x="464" y="132">Send</text>
  </g>
  <g data-flow-step="5">
    <use href="#file" x="525" y="70" width="46" height="52"/>
    <text class="ext" x="548" y="112">PDF</text>
    <text class="name" x="548" y="142">summary</text>
    <use href="#file" x="589" y="70" width="46" height="52"/>
    <text class="ext" x="612" y="112">XLSX</text>
    <text class="name" x="612" y="142">ledger</text>
    <text class="caption" x="635" y="192" text-anchor="end">Summary, updated ledger</text>
  </g>
</svg>
```
