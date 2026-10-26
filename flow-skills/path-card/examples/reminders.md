# Worked example — Path Card

## Input

> Tally's reminders are for freelancers whose invoices are paid late.
> Import your invoices from a spreadsheet, Tally flags the overdue ones,
> and one press sends each client a reminder with the invoice attached as
> a PDF. In a pilot with 40 invoices, freelancers were paid 9 days sooner
> on average.

## Output

```figure
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 640 600" role="img" aria-label="For freelancers whose invoices are paid late: import invoices from a spreadsheet, Tally flags the overdue ones, and one press sends each client a reminder with the invoice as a PDF. In a pilot with 40 invoices, freelancers were paid 9 days sooner on average.">
  <title>Overdue invoices, reminded in one press</title>
  <style>
    .card { fill: #ffffff; stroke: #d5dbd6; stroke-width: 1 }
    .persona { font: 700 12px system-ui, sans-serif; letter-spacing: 0.08em; fill: #56635e }
    .name { font: 700 22px system-ui, sans-serif; fill: #171c1a }
    .num { font: 700 15px system-ui, sans-serif; fill: #0e9e98 }
    .step { font: 15px system-ui, sans-serif; fill: #2b3431 }
    .file { fill: none; stroke: #5aa1b0; stroke-width: 1.5; stroke-linejoin: round }
    .ext { font: 700 12px system-ui, sans-serif; fill: #5aa1b0; text-anchor: middle }
    .small { font: 12px system-ui, sans-serif; fill: #6e6e73; text-anchor: middle }
    .arrow { fill: none; stroke: #0e9e98; stroke-width: 2; stroke-linecap: round }
    .head, .act, .cite { fill: #0e9e98 }
    .page { fill: #0e9e98; fill-opacity: 0.13; stroke: #0e9e98; stroke-width: 1.5 }
    .text-line { fill: #0e9e98; fill-opacity: 0.45 }
    .md { font: 700 12px system-ui, sans-serif; fill: #6e6e73 }
    .caption { font: 600 14px system-ui, sans-serif; fill: #171c1a }
    .window { fill: #ffffff; stroke: #cfd6d3; stroke-width: 1 }
    .bar { fill: #f5f6f4 }
    .edge { stroke: #e3e7e4; stroke-width: 1 }
    .light-red { fill: #ff5f57 } .light-amber { fill: #febc2e } .light-green { fill: #28c840 }
    .chrome { font: 600 12px system-ui, sans-serif; fill: #3b4541; text-anchor: middle }
    .stub { fill: #e3e7e4 }
    .late { fill: #fde5e2 }
    .late-text { font: 600 12px system-ui, sans-serif; fill: #a2271c; text-anchor: middle }
    .button { fill: #0e9e98 }
    .pressed { fill: #0b7a75 }
    .pointer { fill: #171c1a; stroke: #ffffff; stroke-width: 1.2 }
    .rule { stroke: #d5dbd6; stroke-width: 1 }
    .stat { font: 700 24px system-ui, sans-serif; fill: #ba2d21 }
    .stat-label { font: 13px system-ui, sans-serif; fill: #56635e }
    @media (prefers-color-scheme: dark) {
      .card, .window { fill: #232528; stroke: #3a3f45 }
      .persona, .stat-label { fill: #98a29e }
      .name, .caption { fill: #eef1ef }
      .step { fill: #d6dbd8 }
      .num, .head, .act, .cite, .button { fill: #14c8c0 }
      .file { stroke: #68b2c2 }
      .ext { fill: #68b2c2 }
      .small, .md { fill: #98989d }
      .arrow { stroke: #14c8c0 }
      .page { fill: #14c8c0; stroke: #14c8c0 }
      .text-line { fill: #14c8c0 }
      .bar { fill: #2b2e32 }
      .edge, .rule { stroke: #3a3f45 }
      .chrome { fill: #c9d0cc }
      .stub { fill: #3a3f45 }
      .late { fill: #3d2220 }
      .late-text { fill: #f0968c }
      .pressed { fill: #0f9e98 }
      .pointer { fill: #eef1ef; stroke: #171c1a }
      .stat { fill: #f07a72 }
    }
    @media (prefers-reduced-motion: no-preference) {
      g:not(.flow-figure-ahead) .rise { animation: rise 0.4s ease-out both }
      g:not(.flow-figure-ahead) .press { animation: press 0.4s ease-out both; transform-box: fill-box; transform-origin: center }
    }
    @keyframes rise { from { opacity: 0; transform: translateY(6px) } }
    @keyframes press { 40% { transform: scale(0.92) } }
  </style>
  <defs>
    <symbol id="file" viewBox="0 0 46 52"><path class="file" d="M2 2 H30 L44 16 V50 H2 Z M30 2 V16 H44"/></symbol>
    <symbol id="check" viewBox="0 0 28 28"><path d="M8 14.5 L12.5 19 L20 9.5" fill="none" stroke="#ffffff" stroke-width="2.4" stroke-linecap="round" stroke-linejoin="round"/></symbol>
    <symbol id="plane" viewBox="0 0 28 28"><path d="M6.5 13.5 L21.5 7 L16.5 21.5 L13.5 15 Z M13.5 15 L21.5 7" fill="none" stroke="#ffffff" stroke-width="1.8" stroke-linejoin="round"/></symbol>
    <marker id="tip" viewBox="0 0 10 10" refX="8" refY="5" markerWidth="6" markerHeight="6" orient="auto"><path class="head" d="M0 0 L10 5 L0 10 z"/></marker>
  </defs>
  <rect class="card" x="8" y="8" width="624" height="584" rx="14"/>
  <text class="persona" x="32" y="46">FOR FREELANCERS WHOSE INVOICES ARE PAID LATE</text>
  <text class="name" x="32" y="82">Overdue invoices, reminded in one press</text>
  <text class="num" x="32" y="118">1</text>
  <text class="step" x="52" y="118">Import your invoices from a spreadsheet</text>
  <text class="num" x="32" y="144">2</text>
  <text class="step" x="52" y="144">Tally flags the overdue ones</text>
  <text class="num" x="32" y="170">3</text>
  <text class="step" x="52" y="170">One press sends each client a reminder</text>
  <rect class="window" x="132" y="376" width="376" height="128" rx="10"/>
  <path class="bar" d="M142 376 H498 A10 10 0 0 1 508 386 V402 H132 V386 A10 10 0 0 1 142 376 Z"/>
  <line class="edge" x1="132" y1="402" x2="508" y2="402"/>
  <circle class="light-red" cx="148" cy="389" r="4.5"/>
  <circle class="light-amber" cx="162" cy="389" r="4.5"/>
  <circle class="light-green" cx="176" cy="389" r="4.5"/>
  <text class="chrome" x="320" y="393">Tally</text>
  <rect class="stub" x="150" y="420" width="120" height="8" rx="4"/>
  <rect class="late" x="290" y="414" width="76" height="20" rx="10"/>
  <text class="late-text" x="328" y="428">Overdue</text>
  <rect class="stub" x="150" y="448" width="96" height="8" rx="4"/>
  <rect class="stub" x="150" y="476" width="108" height="8" rx="4"/>
  <rect class="late" x="290" y="470" width="76" height="20" rx="10"/>
  <text class="late-text" x="328" y="484">Overdue</text>
  <rect class="button" x="416" y="440" width="72" height="30" rx="7"/>
  <use href="#plane" x="438" y="441" width="28" height="28"/>
  <g data-flow-step="1">
    <use href="#file" x="127" y="230" width="46" height="52"/>
    <text class="ext rise" x="150" y="272">XLSX</text>
    <text class="small rise" x="150" y="302">invoices</text>
    <text class="caption rise" x="100" y="342">Your invoices</text>
  </g>
  <g data-flow-step="2">
    <line class="arrow" x1="186" y1="256" x2="212" y2="256"/>
    <rect class="act" x="217" y="242" width="28" height="28" rx="8"/>
    <use href="#check" x="217" y="242" width="28" height="28"/>
    <line class="arrow" x1="250" y1="256" x2="274" y2="256" marker-end="url(#tip)"/>
    <text class="small rise" x="231" y="292">Flags</text>
    <rect class="page" x="282" y="206" width="80" height="100" rx="7"/>
    <text class="md" x="290" y="224">M↓</text>
    <rect class="text-line" x="290" y="236" width="58" height="5" rx="2.5"/>
    <rect class="text-line" x="290" y="250" width="46" height="5" rx="2.5"/>
    <rect class="text-line" x="290" y="264" width="58" height="5" rx="2.5"/>
    <rect class="text-line" x="290" y="278" width="46" height="5" rx="2.5"/>
    <circle class="cite" cx="354" cy="238.5" r="2.5"/>
    <circle class="cite" cx="354" cy="266.5" r="2.5"/>
    <text class="caption rise" x="322" y="342" text-anchor="middle">Overdue flagged</text>
  </g>
  <g data-flow-step="3">
    <line class="arrow" x1="372" y1="256" x2="398" y2="256"/>
    <rect class="act" x="403" y="242" width="28" height="28" rx="8"/>
    <use href="#plane" x="403" y="242" width="28" height="28"/>
    <line class="arrow" x1="436" y1="256" x2="462" y2="256" marker-end="url(#tip)"/>
    <text class="small rise" x="417" y="292">Sends</text>
    <use href="#file" x="477" y="230" width="46" height="52"/>
    <text class="ext rise" x="500" y="272">PDF</text>
    <text class="small rise" x="500" y="302">invoice</text>
    <text class="caption rise" x="560" y="342" text-anchor="end">Reminder with PDF</text>
  </g>
  <g data-flow-step="4">
    <rect class="pressed press" x="416" y="440" width="72" height="30" rx="7"/>
    <use href="#plane" x="438" y="441" width="28" height="28"/>
    <path class="pointer rise" d="M476 460 L476 480 L481 475 L485 484 L489 482 L485 474 L492 474 Z"/>
  </g>
  <g data-flow-step="5">
    <line class="rule" x1="32" y1="532" x2="608" y2="532"/>
    <text class="stat rise" x="32" y="570">9 days sooner</text>
    <text class="stat-label rise" x="200" y="568">paid on average, in a pilot with 40 invoices</text>
  </g>
</svg>
```
