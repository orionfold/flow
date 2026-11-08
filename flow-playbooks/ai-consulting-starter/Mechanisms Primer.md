---
title: Mechanisms Primer
order: 1
sources:
  - https://orionfold.com/about/
  - https://orionfold.com/story/
  - https://manavsehgal.substack.com/
  - https://www.linkedin.com/newsletters/ai-for-everyone-7147963517520740353/
  - https://www.linkedin.com/in/manavsehgal/
---

# Mechanisms Primer

This is the first document in [AI Consulting Starter](README.md). Everything after it puts mechanisms to work: [Amazon Mechanisms and Practices](Amazon%20Mechanisms%20and%20Practices.md), the [Press Release FAQ for AI project](Press%20Release%20FAQ%20for%20AI%20project.md) and [Pilot to Scale](Pilot%20to%20Scale.md). So it is worth getting the idea straight before using any of them.

By the end you will be able to say what a mechanism is, spot where one is missing, and build a small one for a real problem.

## What a mechanism is

A mechanism is a closed loop that produces the same good result whether or not anyone remembers to try hard. At Amazon it has three parts: a tool, adoption and inspection. The [README](README.md) explains each part. Here is the short test I use for each one.

| Part | The question it answers | What it looks like when it is missing |
| --- | --- | --- |
| Tool | What turns the input into the output we want? | Everyone does the work their own way, and the result depends on who did it. |
| Adoption | Is the tool part of how the work gets done? | The template exists, but people work around it when they are busy. |
| Inspection | Who checks the output, how often, and against what? | The tool runs every week, but nobody can say whether it is working. |

The part people skip most is inspection. A tool feels finished the day it ships. A mechanism is only finished when someone owns the question "is this still producing what we built it for?" and acts on the answer.

```figure skill: isometric-figure
<svg xmlns="http://www.w3.org/2000/svg" aria-label="A mechanism is a stack of three parts: the tool at the base turns input into output, adoption rests on it and makes the tool part of how the work gets done, and inspection sits on top and checks the output." class="all" data-flow-state="all tool adoption inspection" role="img" viewBox="0 0 720 540">
  <title>A mechanism rests on three parts: tool, adoption and inspection</title>
  <defs>
    <linearGradient id="sheen" x1="0" x2="0.4" y1="0" y2="1">
      <stop offset="0" stop-color="#ffffff" stop-opacity="0.7"/>
      <stop offset="1" stop-color="#ffffff" stop-opacity="0"/>
    </linearGradient>
  </defs>
  <style>
.bg { fill: #f8fafc }
.head { font: 700 15px sans-serif; fill: #0f172a }
.name { font: 600 15px sans-serif; fill: #0f172a; text-anchor: middle }
.note text { font: 13px sans-serif; fill: #334155 }
.note .h { font-weight: 700; fill: #0f172a }
.hint { font: 12px sans-serif; fill: #64748b }
.slab { cursor: pointer; transition: transform 0.3s ease }
.face { stroke: #ffffff; stroke-width: 1 }
.t-tool { fill: #ccfbf1 }
.d-tool { fill: #0d9488; fill-opacity: 0.85 }
.t-adoption { fill: #ede9fe }
.d-adoption { fill: #7c3aed; fill-opacity: 0.85 }
.t-inspection { fill: #dbeafe }
.d-inspection { fill: #2563eb; fill-opacity: 0.85 }
.obj { fill: #ffffff; stroke: #334155; stroke-width: 1.5 }
.gear { fill: none; stroke: #0f766e; stroke-width: 5; stroke-dasharray: 3 2.5 }
.hub { fill: #0f766e }
.ink { fill: none; stroke: #334155; stroke-width: 1.5; stroke-linecap: round }
.person { fill: #6d28d9 }
.tool .s-tool, .adoption .s-adoption, .inspection .s-inspection { transform: translate(0px, -14px) }
.tool .s-tool .face, .adoption .s-adoption .face, .inspection .s-inspection .face { stroke: #f59e0b; stroke-width: 3 }
.tool .note, .adoption .note, .inspection .note { display: none }
.tool .n-tool, .adoption .n-adoption, .inspection .n-inspection { display: inline }
@media (prefers-color-scheme: dark) { .bg { fill: #0f172a } .head, .name, .note .h { fill: #f1f5f9 } .note text { fill: #cbd5e1 } .hint { fill: #94a3b8 } .face { stroke: #1e293b } .t-tool { fill: #0d9488; fill-opacity: 0.35 } .t-adoption { fill: #7c3aed; fill-opacity: 0.35 } .t-inspection { fill: #2563eb; fill-opacity: 0.35 } .sheen { opacity: 0.4 } .gear { stroke: #5eead4 } .hub { fill: #5eead4 } .person { fill: #c4b5fd } }
</style>
  <rect class="bg" height="540" width="720" x="0" y="0"/>
  <text class="head" x="430" y="40">A mechanism: tool, adoption, inspection</text>

  <g class="slab s-tool" data-flow-press="state=tool">
    <polygon class="d-tool" points="70,400 230,480 230,500 70,420"/>
    <polygon class="d-tool" points="230,480 390,400 390,420 230,500"/>
    <path class="face t-tool" d="M 230 320 l 160 80 l -160 80 l -160 -80 z"/>
    <path class="sheen" d="M 230 320 l 160 80 l -160 80 l -160 -80 z" fill="url(#sheen)"/>
    <circle class="gear" cx="142" cy="388" r="11"/>
    <circle class="hub" cx="142" cy="388" r="4"/>
    <circle class="gear" cx="164" cy="405" r="8"/>
    <circle class="hub" cx="164" cy="405" r="3"/>
    <text class="name" x="280" y="400">Tool</text>
  </g>

  <g class="slab s-adoption" data-flow-press="state=adoption">
    <polygon class="d-adoption" points="70,260 230,340 230,360 70,280"/>
    <polygon class="d-adoption" points="230,340 390,260 390,280 230,360"/>
    <path class="face t-adoption" d="M 230 180 l 160 80 l -160 80 l -160 -80 z"/>
    <path class="sheen" d="M 230 180 l 160 80 l -160 80 l -160 -80 z" fill="url(#sheen)"/>
    <circle class="person" cx="140" cy="236" r="6"/>
    <rect class="person" height="18" rx="7" width="16" x="132" y="244"/>
    <circle class="person" cx="162" cy="236" r="6"/>
    <rect class="person" height="18" rx="7" width="16" x="154" y="244"/>
    <text class="name" x="280" y="260">Adoption</text>
  </g>

  <g class="slab s-inspection" data-flow-press="state=inspection">
    <polygon class="d-inspection" points="70,120 230,200 230,220 70,140"/>
    <polygon class="d-inspection" points="230,200 390,120 390,140 230,220"/>
    <path class="face t-inspection" d="M 230 40 l 160 80 l -160 80 l -160 -80 z"/>
    <path class="sheen" d="M 230 40 l 160 80 l -160 80 l -160 -80 z" fill="url(#sheen)"/>
    <rect class="obj" height="42" rx="3" width="34" x="136" y="92"/>
    <line class="ink" x1="142" x2="164" y1="102" y2="102"/>
    <line class="ink" x1="142" x2="160" y1="110" y2="110"/>
    <polyline class="ink" points="144,121 150,127 162,115"/>
    <text class="name" x="280" y="120">Inspection</text>
  </g>

  <g class="note n-inspection">
    <text class="h" x="430" y="86">Inspection</text>
    <text x="430" y="104">Who checks the output, how often,</text>
    <text x="430" y="122">and against what?</text>
    <text x="430" y="144">When missing: nobody can say</text>
    <text x="430" y="162">whether it is working.</text>
  </g>
  <g class="note n-adoption">
    <text class="h" x="430" y="226">Adoption</text>
    <text x="430" y="244">Is the tool part of how the work</text>
    <text x="430" y="262">gets done?</text>
    <text x="430" y="284">When missing: people work around</text>
    <text x="430" y="302">it when they are busy.</text>
  </g>
  <g class="note n-tool">
    <text class="h" x="430" y="366">Tool</text>
    <text x="430" y="384">What turns the input into the</text>
    <text x="430" y="402">output we want?</text>
    <text x="430" y="424">When missing: the result depends</text>
    <text x="430" y="442">on who did it.</text>
  </g>

  <text class="hint" x="430" y="525">Press a slab to lift it</text>
</svg>
```

A mechanism is not two things. It is not a policy: a policy says what should happen, and a mechanism makes it happen. And it is not a person. If the result depends on one strong owner remembering, you have a hero, not a mechanism, and the result leaves when they do.

## How to spot a missing mechanism

You usually find a missing mechanism by its symptoms, not by looking for it. These are the ones I look for first:

- [ ] The same problem has come back more than once, and the fix each time was "we'll be more careful."
- [ ] The result depends on who happened to do the work.
- [ ] A decision was made in a meeting, and a month later nobody agrees on what was decided.
- [ ] A project is "going well," but nobody can name the number that says so.
- [ ] A good practice exists in one team and nowhere else.

If you tick two or more for one area of a business, that area needs a mechanism. The figure below shows which part is most likely missing for each symptom.

```figure skill: visual-explainer
<svg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 960 410' role='img' aria-label='Three symptoms, each pointing to the part of a mechanism most likely missing: work done differently by everyone points to a missing tool, a tool people work around points to missing adoption, and a tool nobody checks points to missing inspection.'>
  <title>Which part is missing?</title>
  <desc>Three columns. Each starts with a symptom and points down to the part of the mechanism that is missing and what to do about it.</desc>
  <defs>
    <marker id='arrow' markerHeight='8' markerWidth='8' orient='auto-start-reverse' refX='9' refY='5' viewBox='0 0 10 10'>
      <path d='M0,0 L10,5 L0,10 z' fill='#5f6670'/>
    </marker>
  </defs>
  <style>
.label { font: 600 17px sans-serif; fill: #1d2228 }
.line { font: 13px sans-serif; fill: #3a4048 }
.head { font: 600 14px sans-serif; fill: #2a5f99 }
.grey { fill: #eceef0; stroke: #8a8f98; stroke-width: 2 }
.blue { fill: #e6eef7; stroke: #2a5f99; stroke-width: 2 }
.accent { fill: #fbebe1; stroke: #c4581f; stroke-width: 2.5 }
.conn { stroke: #5f6670; stroke-width: 2; fill: none }
</style>
  <rect fill='#f7f7f5' height='410' width='960' x='0' y='0'/>
  <text style='font: 700 20px sans-serif; fill: #1d2228' text-anchor='middle' x='480' y='40'>Which part is missing?</text>
  <text class='head' text-anchor='middle' x='480' y='68'>Start from the symptom you see</text>

  <g data-flow-step='1'>
    <rect class='grey' height='120' rx='10' width='270' x='40' y='90'/>
    <text class='label' text-anchor='middle' x='175' y='120'>Symptom</text>
    <text class='line' text-anchor='middle' x='175' y='150'>
      <tspan x='175'>Everyone does the work</tspan>
      <tspan dy='18' x='175'>their own way, and the result</tspan>
      <tspan dy='18' x='175'>depends on who did it.</tspan>
    </text>
    <line class='conn' marker-end='url(#arrow)' x1='175' x2='175' y1='212' y2='258'/>
    <rect class='blue' height='110' rx='10' width='270' x='40' y='266'/>
    <text class='label' text-anchor='middle' x='175' y='300'>Missing: a tool</text>
    <text class='line' text-anchor='middle' x='175' y='330'>
      <tspan x='175'>Write down the one way</tspan>
      <tspan dy='18' x='175'>the work should be done.</tspan>
    </text>
  </g>

  <g data-flow-step='2'>
    <rect class='grey' height='120' rx='10' width='270' x='345' y='90'/>
    <text class='label' text-anchor='middle' x='480' y='120'>Symptom</text>
    <text class='line' text-anchor='middle' x='480' y='150'>
      <tspan x='480'>The template exists, but</tspan>
      <tspan dy='18' x='480'>people work around it</tspan>
      <tspan dy='18' x='480'>when they are busy.</tspan>
    </text>
    <line class='conn' marker-end='url(#arrow)' x1='480' x2='480' y1='212' y2='258'/>
    <rect class='blue' height='110' rx='10' width='270' x='345' y='266'/>
    <text class='label' text-anchor='middle' x='480' y='300'>Missing: adoption</text>
    <text class='line' text-anchor='middle' x='480' y='330'>
      <tspan x='480'>Attach the tool to a meeting</tspan>
      <tspan dy='18' x='480'>people already attend.</tspan>
    </text>
  </g>

  <g data-flow-step='3'>
    <rect class='grey' height='120' rx='10' width='270' x='650' y='90'/>
    <text class='label' text-anchor='middle' x='785' y='120'>Symptom</text>
    <text class='line' text-anchor='middle' x='785' y='150'>
      <tspan x='785'>The tool runs every week,</tspan>
      <tspan dy='18' x='785'>but nobody can say</tspan>
      <tspan dy='18' x='785'>whether it is working.</tspan>
    </text>
    <line class='conn' marker-end='url(#arrow)' x1='785' x2='785' y1='212' y2='258'/>
    <rect class='accent' height='110' rx='10' width='270' x='650' y='266'/>
    <text class='label' text-anchor='middle' x='785' y='300'>Missing: inspection</text>
    <text class='line' text-anchor='middle' x='785' y='330'>
      <tspan x='785'>Name who checks, how often,</tspan>
      <tspan dy='18' x='785'>and against which measure.</tspan>
    </text>
  </g>
</svg>
```

## How to build one

Start small. The first version of a mechanism should be something one team can use next week.

1. **Name the output and who it is for.** Write one sentence: "When this works, this customer gets this result." If you cannot write it, you are not ready to build a tool.
2. **Find the input.** What does the work start from: a request, a document, a data set, a meeting?
3. **Build the smallest tool that turns the input into the output.** A one-page template or a checklist is often enough. Software can come later.
4. **Put the tool where the work already happens.** Attach it to a meeting, review or hand-off people already attend. Adoption is easier when the tool replaces a step instead of adding one.
5. **Decide the inspection.** Name who looks, how often, and which measure tells them whether the output is good. Put it on a calendar.
6. **Change the tool when inspection says so.** Then write down what changed and why, so the next person inherits the lesson and not just the template.

Step 6 is what makes it a loop. Without it you have built a process, and processes drift.

## Why AI adoption needs mechanisms

With AI, the distance between a good intention and a working mechanism gets bigger. A model's output can change when the data, the prompt or the model version changes, and nobody announces it. A pilot can look great in a demo and then quietly stop being used. "We'll keep an eye on it" is a good intention.

Most of my years at Amazon were spent putting AI in front of customers. At Alexa I led product for Alexa Conversations as it grew from one language to nine. Later I worked in Amazon AGI, in the Amazon store, and with frontier AI labs building on AWS ([About](https://orionfold.com/about/)). In my experience, the AI work that lasted had mechanisms around it, and the work that faded did not.

Here is how the same problem looks as a good intention and as a mechanism:

| AI adoption problem | Good intention | Mechanism |
| --- | --- | --- |
| Teams start from the model and look for a problem. | "We'll focus on customer value." | A PR/FAQ written before any build, and reviewed before money is committed. |
| Model quality slips without anyone noticing. | "We'll monitor the outputs." | A fixed test set the model runs against on every change, with results reviewed in a weekly business review. |
| A pilot launches before it is ready. | "We'll be careful at launch." | A readiness checklist, like an Operational Readiness Review, that must pass before launch and again after. |
| The same AI failure happens twice. | "Lessons learned." | A Correction of Error write-up after each serious failure, with actions that have owners and dates. |

Each mechanism in this table is one Amazon has described in public. [Amazon Mechanisms and Practices](Amazon%20Mechanisms%20and%20Practices.md) gives the source for each one and says which document in this Domain uses it.

### This Domain is a mechanism too

AI Consulting Starter runs on the same three parts. [Flow PR/FAQ](Flow%20PR-FAQ.md) describes this loop from the customer's side.

| Part | In this Domain |
| --- | --- |
| Tool | The maintained source: these documents, kept in one place and kept current. |
| Adoption | Applying the source to every engagement, through Flow's Jobs and Chat, instead of starting from a blank page. |
| Inspection | Reviewing each result against your acceptance standard, then writing the correction back into the source so the next engagement starts from it. |

The write-back is what keeps it a loop. Without it, the Domain would be a set of templates, and templates drift.

## Try it: your first mechanism

Pick one area of your business, or a client's, where AI is in use or being planned. Answer these seven questions in a few sentences each:

1. What result do you need, and who is it for?
2. Which inputs are you allowed to use?
3. Which symptoms from the checklist above do you see?
4. What is the smallest tool that would turn those inputs into the result?
5. Which existing meeting or hand-off will it live in?
6. Who inspects it, how often, and against which acceptance standard?
7. Who makes the final decision?

When you have answers, ask Flow Chat to turn them into a one-page mechanism note. Then run Proofread on it, and review the result before you keep it. You will use this note again in the [Press Release FAQ for AI project](Press%20Release%20FAQ%20for%20AI%20project.md) and in [Pilot to Scale](Pilot%20to%20Scale.md).

## Where I write about this

This document will grow as I write more. These are the places I publish, and I will link specific pieces here where they apply:

- [About me](https://orionfold.com/about/) and [my builder journey](https://orionfold.com/story/) at Orionfold.
- [My Substack](https://manavsehgal.substack.com/), on AI-native systems, agentic products and the operating models behind them.
- [AI for Everyone](https://www.linkedin.com/newsletters/ai-for-everyone-7147963517520740353/), my weekly newsletter on LinkedIn. [AI You Can Check](https://www.linkedin.com/pulse/ai-you-can-check-manav-sehgal-yjcmc) is the piece closest to the idea of inspection in this document.
- [LinkedIn](https://www.linkedin.com/in/manavsehgal/).

Next: **[Amazon Mechanisms and Practices](Amazon%20Mechanisms%20and%20Practices.md)**, the 24 Amazon mechanisms and practices described in public, and which ones this Domain uses.
