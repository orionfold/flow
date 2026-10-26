# Worked example — System Explainer

## Input

> Customers place orders on the storefront, which writes each order to the
> order queue. The fulfilment service takes orders from the queue, asks the
> inventory service to reserve the stock, then sends a pick request to the
> warehouse. The queue is the single point of failure: if it goes down, the
> storefront keeps taking orders but cannot hand them on, so they wait in
> its retry buffer and nothing reaches the warehouse until the queue
> recovers.

## Output

```figure
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 680 300" role="img" aria-label="An order goes from the storefront to the order queue, then to fulfilment, which reserves stock with inventory and sends a pick request to the warehouse; if the queue goes down, orders wait in the storefront's retry buffer and nothing reaches the warehouse." data-flow-state="normal failed">
  <title>Orders reach the warehouse through one queue</title>
  <style>
    .part { fill: #ffffff; stroke: #8e8e93; stroke-width: 1.5 }
    .name { font: 600 14px system-ui, sans-serif; fill: #1d1d1f; text-anchor: middle }
    .label { font: 12px system-ui, sans-serif; fill: #3a3a3c; text-anchor: middle }
    .flow { fill: none; stroke: #0a7aff; stroke-width: 2.5 }
    .queue { cursor: pointer }
    .hint { font: 12px system-ui, sans-serif; fill: #6e6e73 }
    .note { font: 600 12px system-ui, sans-serif; fill: #d70015; visibility: hidden }
    .failed .queue rect { stroke: #d70015; stroke-width: 3; fill: #fff1f1 }
    .failed .depends { stroke: #d70015; stroke-dasharray: 5 4 }
    .failed .note { visibility: visible }
    .failed .hint { visibility: hidden }
    @media (prefers-color-scheme: dark) {
      .part { fill: #2c2c2e }
      .name { fill: #f5f5f7 }
      .label { fill: #d1d1d6 }
      .hint { fill: #aeaeb2 }
      .note { fill: #ff6961 }
      .failed .queue rect { stroke: #ff6961; fill: #3a1d1f }
    }
  </style>
  <defs>
    <marker id="head" viewBox="0 0 10 10" refX="9" refY="5" markerWidth="6" markerHeight="6" orient="auto-start-reverse"><path d="M0 0 L10 5 L0 10 z" fill="#0a7aff"/></marker>
  </defs>
  <rect class="part" x="20" y="50" width="120" height="56" rx="10"/>
  <text class="name" x="80" y="83">Storefront</text>
  <g class="queue" data-flow-press="state=failed" aria-label="The order queue: press to see it fail">
    <rect class="part" x="190" y="50" width="120" height="56" rx="10"/>
    <text class="name" x="250" y="83">Order queue</text>
  </g>
  <rect class="part" x="360" y="50" width="120" height="56" rx="10"/>
  <text class="name" x="420" y="83">Fulfilment</text>
  <rect class="part" x="360" y="190" width="120" height="56" rx="10"/>
  <text class="name" x="420" y="223">Inventory</text>
  <rect class="part" x="540" y="50" width="120" height="56" rx="10"/>
  <text class="name" x="600" y="83">Warehouse</text>
  <g data-flow-step="1">
    <line class="flow" x1="140" y1="78" x2="186" y2="78" marker-end="url(#head)"/>
    <text class="label" x="165" y="132">writes each order</text>
  </g>
  <g data-flow-step="2">
    <line class="flow depends" x1="310" y1="78" x2="356" y2="78" marker-end="url(#head)"/>
    <text class="label" x="335" y="40">takes orders</text>
  </g>
  <g data-flow-step="3">
    <line class="flow" x1="420" y1="106" x2="420" y2="186" marker-end="url(#head)"/>
    <text class="label" x="490" y="152">reserves the stock</text>
  </g>
  <g data-flow-step="4">
    <line class="flow depends" x1="480" y1="78" x2="536" y2="78" marker-end="url(#head)"/>
    <text class="label" x="510" y="40">sends a pick request</text>
  </g>
  <text class="hint" x="20" y="284">Press the order queue to see what happens when it goes down.</text>
  <text class="note" x="20" y="200">Orders wait in the storefront's retry buffer</text>
  <text class="note" x="20" y="284">Nothing reaches the warehouse until the queue recovers.</text>
</svg>
```
