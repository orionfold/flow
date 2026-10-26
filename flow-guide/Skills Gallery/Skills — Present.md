---
title: Skills — Present
tags: [skills-gallery, reference, fictional-example]
---
# Skills — Present

[[Skills Gallery]] · Next: [[Skills — Living Example]]

**Show a piece of work, or a product, at a glance.** These skills draw the shape of a workflow, what goes in, the work and what comes out, a product being used, one step at a time, and both on one card with its proof. Each section shows a short passage, then everything one run of the skill returned, as one change for your review. The passages are fictional teaching examples.

## Workflow Path

A workflow drawn as what goes in, the work, and what comes out. Use it when a document describes a recurring piece of work and a reader should see its shape at a glance. **One run returns an animated path you step through.**

**What it read**

> At the start of each month I export the client's bank statement as a CSV and gather the receipts they emailed as PDFs. I reconcile both against the client's ledger and flag anything that does not match. Then I send the client a one-page summary as a PDF and the updated ledger as a spreadsheet.

**What it drew**

### The month's files become a summary and an updated ledger

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

The acts on the arrows, *Reconcile* and *Send*, are the two the passage names. A path names no step or tool the text leaves out.

To run it on your own words, select a passage like this one, open **Elements**, and press **Workflow Path** under **Skills**.

## Product Mock

A user journey played out in a mock of the product's window. Use it when a document describes how someone uses a product, a feature or a prototype, and a reader should see it happen. **One run returns an animated mock you step through.**

**What it read**

> In Tally, a freelancer's invoicing app, Maya opens her list of clients and picks Northwind. The client's page shows three unpaid invoices. She presses Send reminder on the oldest one, $1,200, due 14 days ago. Tally marks the invoice Reminder sent and adds the reminder to the client's timeline.

**What it drew**

### One press sends a reminder and records it

```figure
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 640 400" role="img" aria-label="In Tally, Maya picks Northwind from her clients, sees three unpaid invoices, presses Send reminder on the oldest, $1,200 due 14 days ago, and Tally marks it Reminder sent and adds it to the timeline.">
  <title>One press sends a reminder and records it</title>
  <style>
    .window { fill: #ffffff; stroke: #cfd6d3; stroke-width: 1 }
    .bar { fill: #f5f6f4 }
    .side { fill: #f5f6f4 }
    .edge { stroke: #e3e7e4; stroke-width: 1 }
    .light-red { fill: #ff5f57 } .light-amber { fill: #febc2e } .light-green { fill: #28c840 }
    .chrome { font: 600 13px system-ui, sans-serif; fill: #3b4541; text-anchor: middle }
    .head { font: 700 12px system-ui, sans-serif; letter-spacing: 0.08em; fill: #6b7672 }
    .item { font: 13px system-ui, sans-serif; fill: #171c1a }
    .title { font: 700 20px system-ui, sans-serif; fill: #171c1a }
    .sub { font: 13px system-ui, sans-serif; fill: #56635e }
    .amount { font: 700 14px system-ui, sans-serif; fill: #171c1a }
    .due { font: 12px system-ui, sans-serif; fill: #56635e }
    .row { fill: #ffffff; stroke: #d9dfdb; stroke-width: 1 }
    .stub { fill: #e3e7e4 }
    .chosen { fill: #2f6fd6; fill-opacity: 0.14 }
    .focus { fill: none; stroke: #2f6fd6; stroke-width: 2 }
    .button { fill: #2f6fd6 }
    .pressed { fill: #1d4fa8 }
    .label { font: 600 13px system-ui, sans-serif; fill: #ffffff; text-anchor: middle }
    .pointer { fill: #171c1a; stroke: #ffffff; stroke-width: 1.2 }
    .done { fill: #dff3e7 }
    .done-text { font: 600 12px system-ui, sans-serif; fill: #146a3f; text-anchor: middle }
    .dot { fill: #2fa36b }
    @media (prefers-color-scheme: dark) {
      .window { fill: #232528; stroke: #3a3f45 }
      .bar, .side { fill: #2b2e32 }
      .edge { stroke: #3a3f45 }
      .chrome { fill: #c9d0cc }
      .head, .sub, .due { fill: #98a29e }
      .item, .title, .amount { fill: #eef1ef }
      .row { fill: #232528; stroke: #3a3f45 }
      .stub { fill: #3a3f45 }
      .chosen { fill: #5b8ff0 }
      .focus { stroke: #5b8ff0 }
      .button { fill: #3f7ae0 }
      .pressed { fill: #2a5cb8 }
      .pointer { fill: #eef1ef; stroke: #171c1a }
      .done { fill: #1d3b2b }
      .done-text { fill: #7fd6a4 }
      .dot { fill: #4cc488 }
    }
    @media (prefers-reduced-motion: no-preference) {
      g:not(.flow-figure-ahead) .rise { animation: rise 0.35s ease-out both }
      g:not(.flow-figure-ahead) .press { animation: press 0.4s ease-out both; transform-box: fill-box; transform-origin: center }
    }
    @keyframes rise { from { opacity: 0; transform: translateY(6px) } }
    @keyframes press { 40% { transform: scale(0.94) } }
  </style>
  <rect class="window" x="8" y="8" width="624" height="384" rx="12"/>
  <path class="bar" d="M20 8 H620 A12 12 0 0 1 632 20 V44 H8 V20 A12 12 0 0 1 20 8 Z"/>
  <line class="edge" x1="8" y1="44" x2="632" y2="44"/>
  <circle class="light-red" cx="28" cy="26" r="6"/>
  <circle class="light-amber" cx="46" cy="26" r="6"/>
  <circle class="light-green" cx="64" cy="26" r="6"/>
  <text class="chrome" x="320" y="31">Tally</text>
  <path class="side" d="M8 44 H168 V392 H20 A12 12 0 0 1 8 380 Z"/>
  <line class="edge" x1="168" y1="44" x2="168" y2="392"/>
  <text class="head" x="24" y="72">CLIENTS</text>
  <rect class="stub" x="24" y="88" width="88" height="8" rx="4"/>
  <text class="item" x="24" y="128">Northwind</text>
  <rect class="stub" x="24" y="148" width="72" height="8" rx="4"/>
  <line class="edge" x1="456" y1="44" x2="456" y2="392"/>
  <text class="head" x="472" y="72">TIMELINE</text>
  <rect class="stub" x="472" y="128" width="120" height="8" rx="4"/>
  <rect class="stub" x="472" y="152" width="96" height="8" rx="4"/>
  <g data-flow-step="1">
    <rect class="chosen" x="16" y="110" width="144" height="28" rx="7"/>
    <text class="title rise" x="200" y="84">Northwind</text>
    <text class="sub rise" x="200" y="106">Three unpaid invoices</text>
    <rect class="row rise" x="200" y="126" width="240" height="48" rx="8"/>
    <text class="amount rise" x="214" y="147">$1,200</text>
    <text class="due rise" x="214" y="164">due 14 days ago</text>
    <rect class="row rise" x="200" y="184" width="240" height="48" rx="8"/>
    <rect class="stub rise" x="214" y="204" width="90" height="8" rx="4"/>
    <rect class="row rise" x="200" y="242" width="240" height="48" rx="8"/>
    <rect class="stub rise" x="214" y="262" width="70" height="8" rx="4"/>
  </g>
  <g data-flow-step="2">
    <rect class="focus" x="200" y="126" width="240" height="48" rx="8"/>
    <rect class="button rise" x="200" y="310" width="132" height="32" rx="7"/>
    <text class="label rise" x="266" y="331">Send reminder</text>
  </g>
  <g data-flow-step="3">
    <rect class="pressed press" x="200" y="310" width="132" height="32" rx="7"/>
    <text class="label" x="266" y="331">Send reminder</text>
    <path class="pointer rise" d="M326 334 L326 354 L331 349 L335 358 L339 356 L335 348 L342 348 Z"/>
  </g>
  <g data-flow-step="4">
    <rect class="done rise" x="336" y="139" width="96" height="22" rx="11"/>
    <text class="done-text rise" x="384" y="154">Reminder sent</text>
    <circle class="dot rise" cx="477" cy="100" r="4"/>
    <text class="item rise" x="488" y="105">Reminder sent</text>
  </g>
</svg>
```

Only what the passage names is written on screen: the client, the oldest invoice, the button and the status. The other invoices and clients are grey bars.

To run it on your own words, select a passage like this one, open **Elements**, and press **Product Mock** under **Skills**.

## Path Card

A feature on one card: who it is for, the steps, the path, proof. Use it when a document introduces a feature, a service or an offer, and a reader should grasp it at a glance. **One run returns an animated card you step through.**

**What it read**

> Tally's reminders are for freelancers whose invoices are paid late. Import your invoices from a spreadsheet, Tally flags the overdue ones, and one press sends each client a reminder with the invoice attached as a PDF. In a pilot with 40 invoices, freelancers were paid 9 days sooner on average.

**What it drew**

### Overdue invoices, reminded in one press

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

The stat line is there because the passage gives a number and what it was measured on. Given a passage with no number, the card ends after the mock.

To run it on your own words, select a passage like this one, open **Elements**, and press **Path Card** under **Skills**.

Back: [[Skills Gallery]] · Next: [[Skills — Living Example]]
