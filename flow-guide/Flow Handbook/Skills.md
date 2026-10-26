---
title: Skills
tags: ["flow", "reference", "skills"]
---
# Skills

A skill is a method Flow knows how to apply to your words: lay initiatives on a value-and-effort map, turn a plan into a roadmap, log the risks a meeting raised. Each one reads what you selected, or the whole document when nothing is selected, and draws its answer with Flow's own blocks — a chart, a diagram, a table, a form. What it draws comes back in **Review Changes** for you to keep or discard, like every other Agency action.

## Run one

Open **Elements** and press a card under **Skills**. Select the passage first when the skill should read only that; otherwise it reads the whole document. The skill runs on the model Flow picks for it (below), with the same instruction whichever model that is, and its result is added after what it read.

A skill uses only what your text says. When the text lacks something the method needs — a date, an owner, a second number — it says so in a line instead of guessing.

**Change it…** sits beside Ask on a chart or diagram a skill drew. It runs the same skill again with that block as its input and puts the new drawing in its place, again through Review Changes. A table carries no skill's name, so redraw a table by selecting its passage and pressing the card.

The receipt for the run names the skill and its version beside the model that ran it.

To see what each skill draws before you run one, open [[Skills Gallery]]: every skill's worked example, what it read and what it drew, and a living map that Jobs keep current.

## Find the skill for a section

**Ideas** notices when a document has sections a skill could work on: at least two sections of forty words or more, each with the points, numbers or dates some skill needs, and no chart, diagram or table after it yet. It offers **Find skills for 6 sections of …**. That count is made on your Mac without a model, so it only says where to look.

You can also ask in Chat — **Which skill fits each section of …?** is offered as a suggestion — and Chat answers in the conversation: each section, its skill and why, with the same suggestions waiting in Ideas. Pressing the card, or the **Suggest Ideas** button at the top of Ideas, opens a sheet that lists the sections it will read, what it costs and which model runs it — the one you pinned in the toolbar, or Smart Routing's pick — before anything runs. When that model is off your Mac, the sheet asks before the sections leave. **Suggest Ideas** asks that model to name the one skill that fits each section, if any, and checks every answer: a skill not in the list, or one whose needs the section does not meet, is dropped. Nothing in the document changes. Each suggestion becomes an idea — **Run Option Comparison on "2. Option Comparison"**, with the model's reason — and pressing it opens that skill's sheet on that section, where you see the run's own cost and decide.

## Which model runs a skill

Flow measured each skill on the models it can run, on one planning document, and reads each draft back: did it pass the skill's check, and did it invent nothing and say what was missing. A skill runs on the model that drew it best of those you have set up. On that test a frontier model such as Claude Code drew all twelve method skills whole, while a small model on your Mac drew few of them well. The rule that does this is **Skills: the model that drew each best**, first in **Settings ▸ Smart Routing ▸ Rules**. It only prefers: a model you pinned still runs everything, **Stays on this Mac** still keeps a skill on your Mac, and a run that would leave your Mac still asks first. To change it for one skill, add a rule there that applies **When it runs a skill** and pick the skill. Settings ▸ Skills shows each skill's model and the reason.

## The skills

| Skill | What it draws |
| --- | --- |
| Architecture Diagram | The parts of a system, where they run, and what flows between |
| Decision Brief | The decision, the options, a recommendation and its sources |
| Delegation Map | Who does each step, and where the work changes hands |
| Guided Exercise | A passage turned into steps a learner works through and signs |
| Landscape Map | Who is in a market or field, grouped, with each one's source |
| Opportunity Map | Initiatives placed by value and effort, with the case for each |
| Option Comparison | Options side by side on the facts that tell them apart |
| Register | Risks, issues or decisions logged with an owner and a check |
| Roadmap | Work laid out over time, by workstream, with its milestones |
| Scenario Model | Low, base and high cases from stated ranges, and a choice |
| Scorecard | Each candidate scored against weighted criteria, then signed off |
| Value Model | The value a change creates, from its stated assumptions |

The skills are general techniques. They know how to draw an opportunity map, not which opportunities matter to you; that comes from your document.

## Figures

These skills draw a figure rather than a chart: a picture made for its one idea, which you can press and step through in the document.

| Skill | What it draws |
| --- | --- |
| Field-Notes Diagram | A technical idea's numbers drawn to scale, field-notes style |
| Isometric Figure | A layered stack in depth; press a layer to read what it does |
| Path Card | A feature on one card: who it is for, the steps, the path, proof |
| Product Mock | A user journey played out in a mock of the product's window |
| System Explainer | A system's parts, its flows, and what a failure changes |
| Visual Explainer | One idea from the text, drawn so it builds step by step |
| Workflow Path | A workflow drawn as what goes in, the work, and what comes out |

A figure built in steps has **Previous**, **Play** and **Next** under it, and Left and Right step it once you click it. A part drawn as a switch changes the figure when you click it or press Return or Space, and changes it back when you press it again. A figure's own motion stops when Reduce Motion is on in System Settings ▸ Accessibility, leaving it at rest; its steps still play. This one shows a skill's run, a step at a time:

```figure
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 640 170" role="img" aria-label="A skill runs in five steps: you select a passage, press the skill's card, a model draws the answer, Flow checks the draft, and you keep it in Review Changes.">
  <title>How a skill runs</title>
  <style>
    .box { fill: #ffffff; stroke: #8e8e93; stroke-width: 1.5 }
    .yours { stroke: #0a7aff; stroke-width: 2 }
    .name { font: 600 13px system-ui, sans-serif; fill: #1d1d1f; text-anchor: middle }
    .flow { stroke: #8e8e93; stroke-width: 2 }
  </style>
  <defs>
    <marker id="head" viewBox="0 0 10 10" refX="9" refY="5" markerWidth="6" markerHeight="6" orient="auto-start-reverse"><path d="M0 0 L10 5 L0 10 z" fill="#8e8e93"/></marker>
  </defs>
  <rect width="640" height="170" rx="14" fill="#f5f5f7"/>
  <g data-flow-step="1">
    <rect class="box yours" x="14" y="50" width="108" height="64" rx="10"/>
    <text class="name" x="68" y="78">Select a<tspan x="68" dy="17">passage</tspan></text>
  </g>
  <g data-flow-step="2">
    <line class="flow" x1="122" y1="82" x2="137" y2="82" marker-end="url(#head)"/>
    <rect class="box yours" x="140" y="50" width="108" height="64" rx="10"/>
    <text class="name" x="194" y="78">Press the<tspan x="194" dy="17">skill's card</tspan></text>
  </g>
  <g data-flow-step="3">
    <line class="flow" x1="248" y1="82" x2="263" y2="82" marker-end="url(#head)"/>
    <rect class="box" x="266" y="50" width="108" height="64" rx="10"/>
    <text class="name" x="320" y="78">A model<tspan x="320" dy="17">draws it</tspan></text>
  </g>
  <g data-flow-step="4">
    <line class="flow" x1="374" y1="82" x2="389" y2="82" marker-end="url(#head)"/>
    <rect class="box" x="392" y="50" width="108" height="64" rx="10"/>
    <text class="name" x="446" y="78">Flow checks<tspan x="446" dy="17">the draft</tspan></text>
  </g>
  <g data-flow-step="5">
    <line class="flow" x1="500" y1="82" x2="515" y2="82" marker-end="url(#head)"/>
    <rect class="box yours" x="518" y="50" width="108" height="64" rx="10"/>
    <text class="name" x="572" y="78">You keep it<tspan x="572" dy="17">in Review</tspan></text>
  </g>
</svg>
```

Publish draws a figure as stills: the website, PDF and book show each step in order, Word holds a picture per step, and a PowerPoint deck shows its first state.

## Settings ▸ Skills

Every skill is on until you switch it off. **Settings ▸ Skills** lists each with its version, its licence and where it comes from; switching one off removes its card from Elements. **Check for Updates…** fetches Flow's newest skills and shows what changed before anything is replaced. A skill you edited yourself is offered as a review rather than overwritten.

Flow's skills carry no programs. A skill folder holding a script or an executable file is refused when Flow loads it, and Settings names it.

## Your own skills

If Claude Code or Codex has skills of your own, Flow does not load them into its runs. They load only when Agency has **Full access**, where the CLI uses its own settings; They are not cards in Elements: the CLI uses one when your request calls for it. Settings ▸ Skills says how many there are and links to Agency's mode.
