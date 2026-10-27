---
title: AI Consulting Starter
---

# AI Consulting Starter

## What this Domain is

I spent nine years at Amazon leading product, solutions and business development across AWS, Alexa AI and Shopping. Most of that work came down to one job: helping Amazon businesses and AWS customers adopt AI to solve complex problems at scale. This Domain is what I would hand someone starting that job today. It launches with Flow 3.0, released on November 1, 2026.

It is for two kinds of reader. The first is a consultant who helps businesses adopt AI and wants a repeatable way to do it. The second is a leader inside a business who has been asked to "do something with AI" and wants to do it with discipline, not enthusiasm alone. If you are a subject matter expert in another field, you can adapt the same method to your own work.

The Domain does two things, in order. First it introduces Amazon Mechanisms: what makes one, and the ones Amazon has described in public. Then it applies the two I relied on most, Working Backwards and the PR/FAQ, to adopting AI, from finding the right opportunity to taking a pilot to scale.

When you finish it, you will have:

- A working understanding of what a mechanism is and how to build one.
- A reference to the Amazon mechanisms and practices described in public, and which of them matter most for adopting AI.
- A PR/FAQ for one real AI project, in your own business or a client's, that picks the right opportunity and describes it from the customer's side before anything is built.
- A plan for moving a pilot into production, with the inspection that keeps it honest.

## Amazon Mechanisms, briefly

At Amazon we said that good intentions don't work; mechanisms do. Good intentions assume people will try harder next time. They usually do, for a while, and then the same problem comes back, because nothing about the system changed.

A mechanism changes the system. It has three parts:

1. **A tool** that turns an input into the output you want: a template, a checklist, a review, a piece of software.
2. **Adoption**, so the people who need the tool actually use it, as part of how the work gets done and not as an extra.
3. **Inspection**, so someone checks whether the tool is producing the output and improves it when it is not.

Leave out any one part and you are back to good intentions. A tool nobody adopts is shelfware. Adoption without inspection drifts. Inspection without a tool is just criticism.

The mechanisms this Domain puts to work are tools in that sense. Working Backwards starts from the customer and the outcome, not from the technology. The PR/FAQ is the written form of Working Backwards: a press release for a product that does not exist yet, followed by the hard questions and their answers. Its review starts the way a 6-page narrative's does, with everyone reading the document in silence.

I have found these most useful in AI adoption, because there it is so easy to start from the model and go looking for a problem.

Amazon has many more mechanisms and practices than these. [Amazon Mechanisms and Practices](Amazon%20Mechanisms%20and%20Practices.md) lists 24 that are described in public, with a source for each, and says which ones this Domain uses and where.

```figure skill: visual-explainer
<svg xmlns="http://www.w3.org/2000/svg" aria-label="Good intentions let the same problem come back; a mechanism changes the system by joining a tool, adoption of that tool, and inspection that checks its output and improves the tool when it is not working." role="img" viewBox="0 0 960 380">
  <title>A mechanism needs a tool, adoption and inspection</title>
  <desc>Four steps from left to right: good intentions, a tool, adoption, inspection, with an arrow from inspection back to the tool.</desc>
  <defs>
    <marker id="arrow" markerHeight="8" markerWidth="8" orient="auto-start-reverse" refX="9" refY="5" viewBox="0 0 10 10">
      <path d="M0,0 L10,5 L0,10 z" fill="#5f6670"/>
    </marker>
    <marker id="arrowAccent" markerHeight="8" markerWidth="8" orient="auto-start-reverse" refX="9" refY="5" viewBox="0 0 10 10">
      <path d="M0,0 L10,5 L0,10 z" fill="#c4581f"/>
    </marker>
  </defs>
  <style>
.label { font: 600 17px sans-serif; fill: #1d2228 }
.line { font: 13px sans-serif; fill: #3a4048 }
.head { font: 600 14px sans-serif; fill: #2a5f99 }
.note { font: italic 13px sans-serif; fill: #c4581f }
.grey { fill: #eceef0; stroke: #8a8f98; stroke-width: 2 }
.blue { fill: #e6eef7; stroke: #2a5f99; stroke-width: 2 }
.accent { fill: #fbebe1; stroke: #c4581f; stroke-width: 2.5 }
.conn { stroke: #5f6670; stroke-width: 2; fill: none }
.loop { stroke: #c4581f; stroke-width: 2.5; fill: none; stroke-dasharray: 6 4 }
@keyframes flow { to { stroke-dashoffset: -20 } }
.loop { animation: flow 1.2s linear infinite }
@media (prefers-reduced-motion: reduce) { .loop { animation: none } }
</style>
  <rect fill="#f7f7f5" height="380" width="960" x="0" y="0"/>
  <text style="font: 700 20px sans-serif; fill: #1d2228" text-anchor="middle" x="480" y="40">Good intentions don't work; mechanisms do</text>

  <g data-flow-step="1">
    <rect class="grey" height="150" rx="10" width="200" x="30" y="110"/>
    <text class="label" text-anchor="middle" x="130" y="145">Good intentions</text>
    <text class="line" text-anchor="middle" x="130" y="180">
      <tspan x="130">The same problem comes</tspan>
      <tspan dy="18" x="130">back, because nothing</tspan>
      <tspan dy="18" x="130">about the system changed.</tspan>
    </text>
  </g>

  <g data-flow-step="2">
    <text class="head" text-anchor="middle" x="600" y="85">A mechanism changes the system</text>
    <line class="conn" marker-end="url(#arrow)" x1="232" x2="262" y1="185" y2="185"/>
    <rect class="blue" height="150" rx="10" width="200" x="270" y="110"/>
    <text class="label" text-anchor="middle" x="370" y="145">1. A tool</text>
    <text class="line" text-anchor="middle" x="370" y="180">
      <tspan x="370">Turns an input into</tspan>
      <tspan dy="18" x="370">the output you want.</tspan>
    </text>
  </g>

  <g data-flow-step="3">
    <line class="conn" marker-end="url(#arrow)" x1="472" x2="502" y1="185" y2="185"/>
    <rect class="blue" height="150" rx="10" width="200" x="510" y="110"/>
    <text class="label" text-anchor="middle" x="610" y="145">2. Adoption</text>
    <text class="line" text-anchor="middle" x="610" y="180">
      <tspan x="610">Part of how the work</tspan>
      <tspan dy="18" x="610">gets done, not an extra.</tspan>
    </text>
  </g>

  <g data-flow-step="4">
    <line class="conn" marker-end="url(#arrow)" x1="712" x2="742" y1="185" y2="185"/>
    <rect class="accent" height="150" rx="10" width="190" x="750" y="110"/>
    <text class="label" text-anchor="middle" x="845" y="145">3. Inspection</text>
    <text class="line" text-anchor="middle" x="845" y="180">
      <tspan x="845">Someone checks whether</tspan>
      <tspan dy="18" x="845">the tool is producing</tspan>
      <tspan dy="18" x="845">the output.</tspan>
    </text>
    <path class="loop" d="M845,262 V320 H370 V268" marker-end="url(#arrowAccent)"/>
    <text class="note" text-anchor="middle" x="607" y="345">…and improves it when it is not</text>
  </g>
</svg>
```

## The path through the Domain

1. **[Mechanisms Primer](Mechanisms%20Primer.md)**: what a mechanism is, how to spot a missing one, and how to build one from a tool, adoption and inspection.
2. **[Amazon Mechanisms and Practices](Amazon%20Mechanisms%20and%20Practices.md)**: 24 Amazon mechanisms and practices described in public, each with a source, and which ones this Domain uses and where.
3. **[Press Release FAQ for AI project](Press%20Release%20FAQ%20for%20AI%20project.md)**: how to work backwards from the customer and write the press release and FAQ for a real AI project, in your own business or a client's, before you build.
4. **[Pilot to Scale](Pilot%20to%20Scale.md)**: how to run a pilot that answers a real question, and the mechanisms that take it into production.

Each document builds on the ones before it. If you already know Amazon's mechanisms well, you can start at 3.

```figure skill: isometric-figure
<svg xmlns="http://www.w3.org/2000/svg" aria-label="The path through the Domain stacks four documents: Mechanisms Primer at the base, then Amazon Mechanisms and Practices, then Press Release FAQ for AI project, with Pilot to Scale on top." class="all" data-flow-state="all primer amazon prfaq pilot" role="img" viewBox="0 0 720 680">
  <title>The path through the Domain rests on four documents</title>
  <defs>
    <linearGradient id="sheen" x1="0" x2="0" y1="0" y2="1">
      <stop offset="0" stop-color="#ffffff" stop-opacity="0.7"/>
      <stop offset="1" stop-color="#ffffff" stop-opacity="0"/>
    </linearGradient>
  </defs>
  <style>
.bg { fill: #f8fafc }
.txt { fill: #0f172a; font-family: system-ui, -apple-system, Segoe UI, sans-serif }
.name { font-size: 14px; font-weight: 600; text-anchor: middle }
.num { fill: #ffffff; font-family: system-ui, sans-serif; font-size: 12px; font-weight: 700; text-anchor: middle }
.note text { font-size: 13px }
.slab { cursor: pointer; transition: transform 0.3s ease }
.f-teal { fill: #ccfbf1 }
.s-teal { fill: #14b8a6; fill-opacity: 0.85 }
.f-violet { fill: #ede9fe }
.s-violet { fill: #8b5cf6; fill-opacity: 0.85 }
.f-blue { fill: #dbeafe }
.s-blue { fill: #3b82f6; fill-opacity: 0.85 }
.f-orange { fill: #ffedd5 }
.s-orange { fill: #f97316; fill-opacity: 0.85 }
.sheen { fill: url(#sheen); pointer-events: none }
.outline { fill: none; stroke: none }
.obj { fill: #ffffff; stroke: #334155; stroke-width: 1.5 }
.ink { fill: none; stroke: #334155; stroke-width: 1.5; stroke-linecap: round }
.inkfill { fill: #334155 }
.hole { fill: #f8fafc }
.teeth { fill: none; stroke: #6d28d9; stroke-width: 5 }
.gear { transform-box: fill-box; transform-origin: center; animation: spin 10s linear infinite }
.gear.rev { animation-direction: reverse; animation-duration: 7s }
@keyframes spin { from { transform: rotate(0deg) } to { transform: rotate(360deg) } }
@media (prefers-reduced-motion: reduce) { .gear { animation: none } .slab { transition: none } }
.note { display: none }
.all .n-all { display: inline }
.primer .n-primer, .amazon .n-amazon, .prfaq .n-prfaq, .pilot .n-pilot { display: inline }
.primer .l-primer, .amazon .l-amazon, .prfaq .l-prfaq, .pilot .l-pilot { transform: translateY(-14px) }
.primer .l-primer .outline, .amazon .l-amazon .outline, .prfaq .l-prfaq .outline, .pilot .l-pilot .outline { stroke: #db2777; stroke-width: 3 }
@media (prefers-color-scheme: dark) { .bg, .hole { fill: #0f172a } .txt { fill: #f1f5f9 } .f-teal { fill: #14b8a6; fill-opacity: 0.35 } .f-violet { fill: #8b5cf6; fill-opacity: 0.35 } .f-blue { fill: #3b82f6; fill-opacity: 0.35 } .f-orange { fill: #f97316; fill-opacity: 0.35 } .obj { fill: #1e293b; stroke: #e2e8f0 } .ink { stroke: #e2e8f0 } .inkfill { fill: #e2e8f0 } .teeth { stroke: #c4b5fd } .primer .l-primer .outline, .amazon .l-amazon .outline, .prfaq .l-prfaq .outline, .pilot .l-pilot .outline { stroke: #f472b6 } }
</style>
  <rect class="bg" height="680" width="720" x="0" y="0"/>

  
  <g class="slab l-primer" data-flow-press="state=primer">
    <polygon class="s-teal" points="70,540 230,620 230,640 70,560"/>
    <polygon class="s-teal" points="230,620 390,540 390,560 230,640"/>
    <path class="f-teal" d="M 230 460 l 160 80 l -160 80 l -160 -80 z"/>
    <path class="sheen" d="M 230 460 l 160 80 l -160 80 l -160 -80 z"/>
    <path class="outline" d="M 230 460 l 160 80 l -160 80 l -160 -80 z"/>
    <text class="num" x="100" y="570">1</text>
    <path class="obj" d="M130 516 h28 l10 10 v34 h-38 z"/>
    <path class="ink" d="M158 516 v10 h10 M136 532 h26 M136 540 h26 M136 548 h26 M136 554 h16"/>
    <text class="txt name" x="280" y="540">Mechanisms Primer</text>
  </g>

  
  <g class="slab l-amazon" data-flow-press="state=amazon">
    <polygon class="s-violet" points="70,400 230,480 230,500 70,420"/>
    <polygon class="s-violet" points="230,480 390,400 390,420 230,500"/>
    <path class="f-violet" d="M 230 320 l 160 80 l -160 80 l -160 -80 z"/>
    <path class="sheen" d="M 230 320 l 160 80 l -160 80 l -160 -80 z"/>
    <path class="outline" d="M 230 320 l 160 80 l -160 80 l -160 -80 z"/>
    <text class="num" x="100" y="430">2</text>
    <g class="gear">
      <circle class="teeth" cx="142" cy="384" r="13" stroke-dasharray="4 4.17"/>
      <circle class="obj" cx="142" cy="384" r="10"/>
      <circle class="hole" cx="142" cy="384" r="3"/>
    </g>
    <g class="gear rev">
      <circle class="teeth" cx="168" cy="402" r="9" stroke-dasharray="3.5 3.57"/>
      <circle class="obj" cx="168" cy="402" r="7"/>
      <circle class="hole" cx="168" cy="402" r="2"/>
    </g>
    <text class="txt name" x="280" y="388">Amazon Mechanisms</text>
    <text class="txt name" x="280" y="404">and Practices</text>
  </g>

  
  <g class="slab l-prfaq" data-flow-press="state=prfaq">
    <polygon class="s-blue" points="70,260 230,340 230,360 70,280"/>
    <polygon class="s-blue" points="230,340 390,260 390,280 230,360"/>
    <path class="f-blue" d="M 230 180 l 160 80 l -160 80 l -160 -80 z"/>
    <path class="sheen" d="M 230 180 l 160 80 l -160 80 l -160 -80 z"/>
    <path class="outline" d="M 230 180 l 160 80 l -160 80 l -160 -80 z"/>
    <text class="num" x="100" y="290">3</text>
    <path class="obj" d="M130 236 h28 l10 10 v34 h-38 z"/>
    <rect class="inkfill" height="4" width="16" x="136" y="242"/>
    <path class="ink" d="M158 236 v10 h10 M136 254 h26 M136 262 h26 M136 270 h26 M136 276 h16"/>
    <text class="txt name" x="280" y="248">Press Release FAQ</text>
    <text class="txt name" x="280" y="264">for AI project</text>
  </g>

  
  <g class="slab l-pilot" data-flow-press="state=pilot">
    <polygon class="s-orange" points="70,120 230,200 230,220 70,140"/>
    <polygon class="s-orange" points="230,200 390,120 390,140 230,220"/>
    <path class="f-orange" d="M 230 40 l 160 80 l -160 80 l -160 -80 z"/>
    <path class="sheen" d="M 230 40 l 160 80 l -160 80 l -160 -80 z"/>
    <path class="outline" d="M 230 40 l 160 80 l -160 80 l -160 -80 z"/>
    <text class="num" x="100" y="150">4</text>
    <rect class="obj" height="14" width="10" x="128" y="132"/>
    <rect class="obj" height="24" width="10" x="144" y="122"/>
    <rect class="obj" height="36" width="10" x="160" y="110"/>
    <path class="ink" d="M124 124 L166 98"/>
    <polygon class="inkfill" points="172,95 161,96 167,104"/>
    <text class="txt name" x="280" y="120">Pilot to Scale</text>
  </g>

  
  <g class="note n-all txt">
    <text x="430" y="80">Each document builds on the ones</text>
    <text x="430" y="98">before it.</text>
    <text x="430" y="124">If you already know Amazon's</text>
    <text x="430" y="142">mechanisms well, you can start at 3.</text>
  </g>
  <g class="note n-pilot txt">
    <text x="430" y="80">How to run a pilot that answers a</text>
    <text x="430" y="98">real question, and the mechanisms</text>
    <text x="430" y="116">that take it into production.</text>
  </g>
  <g class="note n-prfaq txt">
    <text x="430" y="220">How to work backwards from the</text>
    <text x="430" y="238">customer and write the press</text>
    <text x="430" y="256">release and FAQ for a real AI</text>
    <text x="430" y="274">project, in your own business or a</text>
    <text x="430" y="292">client's, before you build.</text>
  </g>
  <g class="note n-amazon txt">
    <text x="430" y="360">24 Amazon mechanisms and practices</text>
    <text x="430" y="378">described in public, each with a</text>
    <text x="430" y="396">source, and which ones this Domain</text>
    <text x="430" y="414">uses and where.</text>
  </g>
  <g class="note n-primer txt">
    <text x="430" y="500">What a mechanism is, how to spot a</text>
    <text x="430" y="518">missing one, and how to build one</text>
    <text x="430" y="536">from a tool, adoption and</text>
    <text x="430" y="554">inspection.</text>
  </g>
</svg>
```

## How to use this Domain in Flow

This Domain is a set of Markdown documents in one Flow folder. Each is a living document: I will keep improving them as I learn.

- **Open a document.** Read the documents in order the first time. I am writing each to be read in one sitting, the way a 6-pager is.
- **Run its Jobs.** Each document will carry Jobs that do the work with you, such as drafting your own PR/FAQ or proofreading it. Run them on your own business or a client's, then review what they produce before you keep it.
- **Ask Chat.** When something is unclear, ask Flow Chat about the folder. It answers from these documents and links each answer to where it came from, so you can check it.
- **Review, write back and publish.** Check what a Job produces against your acceptance standard. When it falls short, write the correction back into the source document, so the next run starts from it. When it passes, publish it in the format your customer needs: GitHub Pages, a GitHub repository, PDF, Office or EPUB. That loop is a mechanism too: the source is the tool, using it on every engagement is adoption, and the review is inspection.

Start with the [Mechanisms Primer](Mechanisms%20Primer.md).

## A worked example

[Flow PR/FAQ](Flow%20PR-FAQ.md) is a complete PR/FAQ, written with the method in [Press Release FAQ for AI project](Press%20Release%20FAQ%20for%20AI%20project.md). It covers the product this Domain is built in, with two case studies: a client building on Relay, and the building of this Domain itself.
