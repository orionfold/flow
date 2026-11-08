---
title: Press Release FAQ for AI project
order: 3
sources:
  - https://orionfold.com/about/
  - https://orionfold.com/story/
  - https://manavsehgal.substack.com/
  - https://www.linkedin.com/newsletters/ai-for-everyone-7147963517520740353/
---

# Press Release FAQ for AI project

This is where [AI Consulting Starter](README.md) puts the PR/FAQ to work on a real AI project, in your own business or a client's. It builds on the [Mechanisms Primer](Mechanisms%20Primer.md). The PR/FAQ is the tool, and this document shows how to get it adopted and how to inspect it.

By the end you will have a press release and an FAQ for one AI project. They will be ready for a review meeting that decides whether to fund the project, change it or stop it.

For a complete example, see [Flow PR/FAQ](Flow%20PR-FAQ.md), the PR/FAQ for Flow 3.0 and the launch of this Domain.

## What a PR/FAQ is

A PR/FAQ is a press release for a product that does not exist yet, followed by the hard questions and their answers. It is the written form of Working Backwards: you start from the customer and the result they get, not from the technology. [Amazon Mechanisms and Practices](Amazon%20Mechanisms%20and%20Practices.md) gives the public sources.

The press release is short, about one page, and the FAQ runs to about five. Most of the work is in the FAQ. That is where you answer the questions a doubtful customer, a finance lead and an engineer would ask.

## Why AI projects need one

The first row of the table in the [Mechanisms Primer](Mechanisms%20Primer.md) is the reason: teams start from the model and look for a problem. AI makes this easy. A good demo can win a room before anyone has said who the customer is or how we would know it works.

A PR/FAQ makes you answer those questions in writing before money is committed. If the press release only reads well when it talks about the model, the project is not ready.

## The PR/FAQ as a mechanism

| Part | For an AI project |
| --- | --- |
| Tool | This template: a one-page press release, then an external and an internal FAQ. |
| Adoption | No AI project gets budget or engineering time without a reviewed PR/FAQ. It is reviewed in the meeting where funding is decided. |
| Inspection | At each pilot review, read the press release again and ask whether customers are getting the result it promised. Update the FAQ with what you learned. |

## Write the press release

Write it as if the project has launched and worked. Use the words a customer would use. Keep model names out of the headline.

| Section | What to write |
| --- | --- |
| Headline | The customer and the result, in one line. |
| Subheading | Who it is for, and the one benefit that matters most to them. |
| Problem | The customer's problem today, in their terms. |
| Solution | What they can do now, and what it is like to use. Mention AI only if the customer would. |
| Leader quote | Why the business did this, from the person who owns the result. |
| How it works | Two or three sentences on how a customer gets started. |
| Customer quote | What a real customer would say after using it. |
| Call to action | Where to go to start. |

If you have to guess at the problem or the customer quote, talk to customers before you go further.

## Write the FAQ

The FAQ has two parts. The external FAQ answers a customer's questions. The internal FAQ answers the business's questions, and for an AI project it has to cover what a demo hides. These are the questions I ask first.

**External FAQ**

- What does it do, and what does it not do?
- What happens when it gets something wrong, and how do I reach a person?
- What happens to my data?
- What does it cost me?

**Internal FAQ**

- What one number tells us this is working? What is it today, and what is the target?
- Which test set will we check the output against, what acceptance standard must it meet, and who owns them?
- What data does it need, and do we have the right to use it?
- What does each use cost to run, and at what volume does it pay back?
- Who reviews a wrong answer before it reaches a customer, and when can that review stop?
- What happens when the model, the prompt or the data changes?
- What would make us stop?

## Before the review

Tick each one before you send the document out:

- [ ] The headline names a customer and a result, not a technology.
- [ ] The success number has a starting value and a target.
- [ ] The FAQ says who inspects the output, how often, against which test set and to what acceptance standard.
- [ ] The FAQ says what would make you stop.
- [ ] Someone who did not write it has read it and listed the questions it leaves unanswered.

## Run the review

Start the meeting with everyone reading the PR/FAQ in silence, the same way a 6-page narrative is read. Then take questions in the order of the document. End with one of three decisions: fund a pilot, rewrite the PR/FAQ, or stop.

Write the decision, its owner and the date at the top of the PR/FAQ. This prevents a symptom from the Primer: a decision made in a meeting that, a month later, nobody agrees on.

```figure skill: visual-explainer
<svg xmlns="http://www.w3.org/2000/svg" aria-label="The PR/FAQ meeting starts with everyone reading in silence, then takes questions in document order, ends with one of three decisions (fund a pilot, rewrite the PR/FAQ, or stop), and the decision, its owner and the date are written at the top of the PR/FAQ so nobody disputes it a month later." role="img" viewBox="0 0 960 340">
  <title>A PR/FAQ meeting runs read, question, decide, then write it down</title>
  <style>
.t { font-family: system-ui, -apple-system, sans-serif; fill: #1f2430 }
.h { font-size: 16px; font-weight: 700 }
.b { font-size: 13px; fill: #4a5060 }
.n { font-size: 13px; font-weight: 700; fill: #ffffff }
.box { fill: #ffffff; stroke: #2b6cb0; stroke-width: 2 }
.opt { fill: #eaf1fa; stroke: #2b6cb0; stroke-width: 1.5 }
.accent { fill: #fff4ec; stroke: #c2410c; stroke-width: 2.5 }
.arrow { stroke: #8a8f9c; stroke-width: 2; fill: none }
</style>
  <defs>
    <marker id="ah" markerHeight="8" markerWidth="8" orient="auto" refX="9" refY="5" viewBox="0 0 10 10">
      <path d="M0 0 L10 5 L0 10 z" fill="#8a8f9c"/>
    </marker>
  </defs>
  <rect fill="#f7f6f2" height="340" width="960" x="0" y="0"/>
  <text class="t" font-size="20" font-weight="700" x="20" y="38">Read, question, decide — then write the decision down</text>

  <g data-flow-step="1">
    <rect class="box" height="240" rx="10" width="200" x="20" y="70"/>
    <circle cx="44" cy="96" fill="#2b6cb0" r="13"/>
    <text class="t n" text-anchor="middle" x="44" y="101">1</text>
    <text class="t h" x="64" y="102">Read in silence</text>
    <text class="t b" x="36" y="140">
      <tspan dy="0" x="36">Everyone reads the PR/FAQ</tspan>
      <tspan dy="20" x="36">in silence, the same way</tspan>
      <tspan dy="20" x="36">a 6-page narrative is read.</tspan>
    </text>
  </g>

  <g data-flow-step="2">
    <line class="arrow" marker-end="url(#ah)" x1="222" x2="256" y1="190" y2="190"/>
    <rect class="box" height="240" rx="10" width="200" x="260" y="70"/>
    <circle cx="284" cy="96" fill="#2b6cb0" r="13"/>
    <text class="t n" text-anchor="middle" x="284" y="101">2</text>
    <text class="t h" x="304" y="102">Questions, in order</text>
    <text class="t b" x="276" y="140">
      <tspan dy="0" x="276">Then take questions in</tspan>
      <tspan dy="20" x="276">the order of the document.</tspan>
    </text>
  </g>

  <g data-flow-step="3">
    <line class="arrow" marker-end="url(#ah)" x1="462" x2="496" y1="190" y2="190"/>
    <rect class="box" height="240" rx="10" width="200" x="500" y="70"/>
    <circle cx="524" cy="96" fill="#2b6cb0" r="13"/>
    <text class="t n" text-anchor="middle" x="524" y="101">3</text>
    <text class="t h" x="544" y="102">One of three</text>
    <text class="t b" x="516" y="134">End with one decision:</text>
    <rect class="opt" height="36" rx="6" width="170" x="515" y="150"/>
    <text class="t" font-size="13" text-anchor="middle" x="600" y="173">Fund a pilot</text>
    <rect class="opt" height="36" rx="6" width="170" x="515" y="198"/>
    <text class="t" font-size="13" text-anchor="middle" x="600" y="221">Rewrite the PR/FAQ</text>
    <rect class="opt" height="36" rx="6" width="170" x="515" y="246"/>
    <text class="t" font-size="13" text-anchor="middle" x="600" y="269">Stop</text>
  </g>

  <g data-flow-step="4">
    <line class="arrow" marker-end="url(#ah)" x1="702" x2="736" y1="190" y2="190"/>
    <rect class="accent" height="240" rx="10" width="200" x="740" y="70"/>
    <circle cx="764" cy="96" fill="#c2410c" r="13"/>
    <text class="t n" text-anchor="middle" x="764" y="101">4</text>
    <text class="t h" fill="#c2410c" x="784" y="102">Write it at the top</text>
    <text class="t b" x="756" y="140">
      <tspan dy="0" x="756">The decision, its owner</tspan>
      <tspan dy="20" x="756">and the date, at the top</tspan>
      <tspan dy="20" x="756">of the PR/FAQ.</tspan>
    </text>
    <line stroke="#c2410c" stroke-dasharray="4 4" stroke-width="1" x1="756" x2="924" y1="210" y2="210"/>
    <text class="t b" x="756" y="236">
      <tspan dy="0" fill="#c2410c" font-weight="700" x="756">Prevents:</tspan>
      <tspan dy="20" x="756">a decision that, a month</tspan>
      <tspan dy="20" x="756">later, nobody agrees on.</tspan>
    </text>
  </g>
</svg>
```

## Try it in Flow

1. Create a note for your project, copy the press release table into it, and fill in each row.
2. Answer the FAQ questions in a few sentences each. Use your mechanism note from the Primer for the inspection answers.
3. Ask Flow Chat to read it as a doubtful finance lead and list the questions it leaves unanswered.
4. Run Proofread, and review the result before you keep it.

[Pilot to Scale](Pilot%20to%20Scale.md) takes the approved PR/FAQ and turns its success number and inspection into a pilot plan.

## Where I write about this

I will link specific pieces here as I write about PR/FAQs for AI projects, on [my Substack](https://manavsehgal.substack.com/) and in [AI for Everyone](https://www.linkedin.com/newsletters/ai-for-everyone-7147963517520740353/). For background on my work, see [About me](https://orionfold.com/about/) and [my builder journey](https://orionfold.com/story/).

Next: [Pilot to Scale](Pilot%20to%20Scale.md), the mechanism for taking an approved AI project from pilot to everyday use.
