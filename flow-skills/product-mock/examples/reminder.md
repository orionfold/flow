# Worked example — Product Mock

## Input

> In Tally, a freelancer's invoicing app, Maya opens her list of clients
> and picks Northwind. The client's page shows three unpaid invoices. She
> presses Send reminder on the oldest one, $1,200, due 14 days ago. Tally
> marks the invoice Reminder sent and adds the reminder to the client's
> timeline.

## Output

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
