---
title: AI Personal Assistants Market Watch
category: research-markets
featured: true
summary: "Follow the assistant market through sourced signals, comparisons and research decisions."
tags: [market-watch, ai-personal-assistants, research]
refresh: manual
jobs:
  - kind: gather
    definition: Assistant Market Refresh.md
    into: data
    as: market
  - kind: keep-sources-fresh
    watch: [Assistant Market Inputs.md, Research Mandate.md, Research Decisions.md, sources/current, https://www.raycast.com/blog/changing-how-raycast-ai-is-priced, https://www.apple.com/newsroom/2026/09/siri-ai-a-profoundly-more-capable-and-personal-assistant-is-here/, https://support.microsoft.com/en-us/microsoft-copilot/using-copilot-tasks]
  - kind: reconcile-against-folder
    folder: sources/current
  - kind: expand-with-sources
    section: Market interpretation
    sources: [sources/current, Research Mandate.md, Research Decisions.md]
---
# AI Personal Assistants Market Watch

**What is becoming practical to delegate—and what still deserves human attention?** A working market brief for an industry analyst, market entrant, investor or journalist studying AI Personal Assistants.

Start with eight selected products and twelve dated primary-source cards. All product capabilities remain publisher-described, not independently exercised. This is a research cohort, not a ranking or a measure of market share.

[Your research question](Research%20Mandate.md) · [Editable evidence](Assistant%20Market%20Inputs.md) · [Decision ledger](Research%20Decisions.md) · [Research method](Assistant%20Research%20Playbook.md)

## Start here

The saved input ledger contains **22 findings**. The bound views below begin as an **authored preview of the first 20**, not a previous product run. Run saved Jobs to incorporate the two additional Raycast findings, redraw the views, fill the source inventory and propose one expanded interpretation. The first successful Gather uses the complete saved ledger; its normal review controls show what changed.

## Research question and scope

Which personal-assistant tasks are becoming practical to delegate, through which distribution surfaces, with what checking effort, cost exposure and control? Begin with a daily briefing that a person can inspect and revisit. Keep the market question separate from a purchasing, investment or publication decision.

The starting scope is US / English and the source date is September 15, 2026. Explicitly retain rollout, regional, device and plan qualifications. Industry analyst is the default lens; change the mandate to suit the intended audience.

## What merits attention

| Event date | Newly retained event | Why inspect it |
| --- | --- | --- |
| 2026-09-14 | Siri AI English beta rollout [^S10] | Check the current device/region boundary rather than reusing an earlier announcement. |
| 2026-09-10 | Raycast pricing and packaging update [^S12] | Separate subscription value, model allowances and repeated-task exposure. |
| 2026-09-01 | Alexa+ offer clarification [^S09] | Distinguish a household membership bundle from a standalone limited chat tier. |

**Changed since last review: no baseline comparison yet.** These are dated events retained in the seed, not changes detected by an earlier run. A page digest changing is a prompt to inspect, not proof of a material market event.

## Market interpretation

For this study, follow the whole task: permitted context, delegated work, durable output, checking, correction and return. ChatGPT Work and Claude Cowork document project context and longer work; compare that contract with the actual task the operator wants to repeat. A task completing somewhere in the background is useful only if its result is available, understandable and correct enough for the next decision. [^S01] [^S05]

Timing and control deserve their own comparison. Gemini's scheduled output can be prepared before delivery; Raycast's automations depend on an awake device and coalesce missed runs. These contracts answer different operational questions. Ask when the evidence was gathered, what happens when the device is unavailable, and who must intervene before work can finish. [^S03] [^S11]

Keep business hypotheses proportional to the evidence. Distribution, personal context and packaging suggest questions worth testing; they do not establish customer demand, retention, margin or superiority. Preserve the counterargument and next resolving check beside every interpretation.

## Evidence at a glance

<!-- data: data/market-*.json#summary -->
| Metric | Value |
| --- | --- |
| Finding records | 20 |
| Retained source cards represented | 11 |
| Products represented | 8 |
| Human-reviewed findings | 0 |
| Exercised findings | 0 |

Counts measure the findings represented in the bound dataset. The initial preview represents eleven cards; all twelve retained cards are already available in the source directory. After a successful Gather the complete saved ledger represents 22 findings, twelve cards and eight products. Human review and exercised outcomes remain zero until actually performed and recorded.

```chart data: data/market-*.json#coverage
chartType: Bar Chart
title: Retained findings by product
subtitle: Coverage of this research set, not capability or market share
source: Assistant Market Inputs.md, Evidence table
data:
  - {"product": "Alexa+", "findings": 2}
  - {"product": "ChatGPT Work", "findings": 4}
  - {"product": "Claude Cowork", "findings": 2}
  - {"product": "Gemini", "findings": 4}
  - {"product": "Microsoft Copilot Tasks", "findings": 2}
  - {"product": "Perplexity Comet", "findings": 2}
  - {"product": "Raycast", "findings": 2}
  - {"product": "Siri AI", "findings": 2}
semantic_types: {product: Category, findings: Count}
encodings:
  y: {field: product}
  x: {field: findings}
  color: {field: product, scheme: teals}
```

<!-- data: data/market-*.json#coverage -->
| Product | Findings |
| --- | --- |
| Alexa+ | 2 |
| ChatGPT Work | 4 |
| Claude Cowork | 2 |
| Gemini | 4 |
| Microsoft Copilot Tasks | 2 |
| Perplexity Comet | 2 |
| Raycast | 2 |
| Siri AI | 2 |

## Where assistance enters the day

| Product | Entry surface | Research cohort |
| --- | --- | --- |
| ChatGPT Work | conversation and desktop | general task delegation |
| Gemini | Google apps and assistant | personal context and routines |
| Claude Cowork | conversation and desktop | knowledge-work delegation |
| Microsoft Copilot Tasks | conversation and Tasks | general task delegation |
| Perplexity Comet | browser | web-context assistance |
| Alexa+ | home devices and chat | household assistance |
| Siri AI | operating system | personal device assistance |
| Raycast | desktop launcher and chat | desktop work routines |

These are analyst groupings. The question is which surface makes the selected task easier to start, check and resume. Include a conventional search engine plus notes, calendar reminders, specialist apps, manual work and human assistance among the substitutes.

## Delegation and continuity

| Part of the task | Compare | Evidence or unresolved check |
| --- | --- | --- |
| Trigger | Immediate request, scheduled run, supported event | Document the exact entry and eligibility; do not assume every surface can create a trigger. [^S01] [^S03] |
| Work location | Cloud, desktop resources, browser session, local device schedule | Local execution and local data storage are different claims. [^S02] [^S05] [^S11] |
| Durable result | Document, file, chat, remembered context, app change | Reopen an output and check its version; a finished message alone is not a verified deliverable. |
| Intervention | Clarification, permission, approval, takeover | Record what the person must decide and whether a task can resume. [^S02] [^S06] |
| Next cycle | Current input, prior result and changed evidence | Test the return with one changed fact and one superseded instruction. |

## Memory, permissions and review

Use separate questions for what the assistant remembers, what it can access, what leaves the device, what it retains and what it may change. Gemini's connection/activity controls and Comet's request-specific context handling make these distinctions concrete. Removing an app connection and removing already-retained activity can be different operations. [^S04] [^S08]

A recurring approval can change the boundary for future work. For a real probe, record the chosen scope, the visible confirmation, the action performed and any opportunity to stop or undo it. Published approval controls do not independently establish correctness, safety or recoverability. [^S06]

## Research themes

```chart data: data/market-*.json#themes
chartType: Bar Chart
title: Where the retained evidence is concentrated
subtitle: Finding count by research theme; gaps guide the next inspection
source: Assistant Market Inputs.md, Evidence table
data:
  - {"theme": "context", "findings": 2}
  - {"theme": "delegation", "findings": 1}
  - {"theme": "distribution", "findings": 1}
  - {"theme": "execution", "findings": 2}
  - {"theme": "freshness", "findings": 1}
  - {"theme": "packaging", "findings": 2}
  - {"theme": "permissions", "findings": 1}
  - {"theme": "privacy", "findings": 2}
  - {"theme": "reach", "findings": 2}
  - {"theme": "recurrence", "findings": 4}
  - {"theme": "review", "findings": 2}
semantic_types: {theme: Category, findings: Count}
encodings:
  y: {field: theme}
  x: {field: findings}
  color: {field: theme, scheme: teals}
```

<!-- data: data/market-*.json#themes -->
| Theme | Findings |
| --- | --- |
| context | 2 |
| delegation | 1 |
| distribution | 1 |
| execution | 2 |
| freshness | 1 |
| packaging | 2 |
| permissions | 1 |
| privacy | 2 |
| reach | 2 |
| recurrence | 4 |
| review | 2 |

The ledger's themes are editorial labels. A theme with fewer findings is less researched in this package; it is not less important or less developed in the market.

## Packaging and distribution

The following Raycast offers share one publisher and comparable monthly individual billing units. Recheck the original before a purchase. This is subscription exposure, not cost per useful result or comparative model quality. [^S12]

<!-- data: data/market-*.json#comparableCosts -->
| Product | Plan | Minimum monthly USD | Twelve month scenario USD | Credits | Checked at | Source URL |
| --- | --- | --- | --- | --- | --- | --- |
| Raycast | Pro | 10 | 120 | 500 | 2026-09-15 | https://www.raycast.com/blog/changing-how-raycast-ai-is-priced |
| Raycast | Pro+ | 20 | 240 | 3000 | 2026-09-15 | https://www.raycast.com/blog/changing-how-raycast-ai-is-priced |
| Raycast | Max | 50 | 600 | 7500 | 2026-09-15 | https://www.raycast.com/blog/changing-how-raycast-ai-is-priced |

```chart data: data/market-*.json#comparableCosts
chartType: Bar Chart
title: Twelve monthly subscription payments
subtitle: USD scenario; excludes taxes, top-ups and external model subscriptions
source: Assistant Market Inputs.md, Plans table; Raycast announcement dated 2026-09-10
data:
  - {"plan": "Pro", "twelve_month_scenario_usd": 120}
  - {"plan": "Pro+", "twelve_month_scenario_usd": 240}
  - {"plan": "Max", "twelve_month_scenario_usd": 600}
semantic_types: {plan: Category, twelve_month_scenario_usd: Currency}
encodings:
  x: {field: plan}
  y: {field: twelve_month_scenario_usd}
  color: {field: plan, scheme: teals}
```

Keep Alexa's household membership inclusion and its limited free chat tier outside that individual subscription comparison. Likewise, variable limits or a future paid-access plan do not yet provide a comparable realized price. Investigate who pays, which existing distribution surface brings the user back, and which costs vary with repeated work. [^S09] [^S10]

## Four ways to use this watch

| Operator | Useful decision | Output to prepare | Avoid inferring |
| --- | --- | --- | --- |
| Industry analyst | Which task contracts or market boundaries changed? | Qualified market map and change brief | Adoption from a feature announcement |
| Market entrant | Which narrow task is worth a falsifiable pilot? | Task hypothesis, substitutes and stop condition | Demand from a gap in a matrix |
| Investor | Which business mechanisms merit deeper diligence? | Distribution, retention and cost questions | Revenue, margins or a trade recommendation from this seed |
| Journalist | What changed, for whom, and what can be shown? | Claim ledger and explanatory draft | Product proof from a staged demonstration |

[Choose your lens](Research%20Mandate.md) and [record a decision](Research%20Decisions.md) without changing the underlying facts to fit the conclusion.

## Investigation queue

| Investigation | Useful result | Current status |
| --- | --- | --- |
| Prepare my day | Correct synthetic inbox/calendar brief with uncertainty surfaced | not tested |
| Find a decision I made | Current decision, its origin and an explicit superseded version | not tested |
| Complete a bounded web task | Prepared result with a clear login/approval/takeover boundary | not tested |
| Maintain this watch | One useful second cycle, including an honest no-change outcome | not tested |

Use an independent answer key. Record setup time, correction effort, unsupported claims, wrong-account events, approval interruptions and whether the useful output can be reopened. Do not fabricate numbers to complete a chart. The [decision ledger](Research%20Decisions.md) begins undecided.

## Prepare the next useful output

| Document | Purpose |
| --- | --- |
| [Market Brief](Market%20Brief.md) | Condense material deliberately prepared for an audience |
| [Research Method](Research%20Method.md) | Propose a diagram of the evidence-to-decision method |
| [Field Notes](Field%20Notes.md) | Convert structured research observations into a table |
| [Assistant Comparison Narrative](Assistant%20Comparison%20Narrative.md) | Turn a compact comparison table into readable bullets |
| [Editorial Draft](Editorial%20Draft.md) | Proofread a short explanatory draft |
| [Regional Brief](Regional%20Brief.md) | Translate a qualified update while preserving links |

Each companion owns one action and one review. Prepare its content deliberately, then run it separately. Approval in this owner never starts another document's Jobs or publishes a result.

## Sources worth opening

- [S01 · ChatGPT Work and Codex](sources/current/S01-chatgpt-work.md) — ChatGPT Work; public help; retrieved 2026-09-15.
- [S02 · Using cloud browser in ChatGPT](sources/current/S02-chatgpt-browser.md) — ChatGPT Work; public help; retrieved 2026-09-15.
- [S03 · Schedule actions in Gemini Apps](sources/current/S03-gemini-schedules.md) — Gemini; public help; retrieved 2026-09-15.
- [S04 · About personalization with Connected Apps](sources/current/S04-gemini-context.md) — Gemini; public help and privacy explanation; retrieved 2026-09-15.
- [S05 · Get started with Claude Cowork](sources/current/S05-claude-cowork.md) — Claude Cowork; public help; retrieved 2026-09-15.
- [S06 · Using Copilot Tasks](sources/current/S06-copilot-tasks.md) — Microsoft Copilot Tasks; public help; retrieved 2026-09-15.
- [S07 · Advice and Use Cases](sources/current/S07-comet-use.md) — Perplexity Comet; public help; retrieved 2026-09-15.
- [S08 · Comet Assistant Privacy and Data Use](sources/current/S08-comet-privacy.md) — Perplexity Comet; public help and privacy explanation; retrieved 2026-09-15.
- [S09 · Alexa+ US availability and Prime membership](sources/current/S09-alexa-packaging.md) — Alexa+; official announcement; retrieved 2026-09-15.
- [S10 · Siri AI is here](sources/current/S10-siri-rollout.md) — Siri AI; official release update; retrieved 2026-09-15.
- [S11 · Automations](sources/current/S11-raycast-automations.md) — Raycast; public help; retrieved 2026-09-15.
- [S12 · Why We Are Changing How Raycast AI Is Priced](sources/current/S12-raycast-pricing.md) — Raycast; official announcement; retrieved 2026-09-15.

## Capture inventory

```flow-folder sources/current
| File | Size | Modified | Digest |
| --- | ---: | --- | --- |
```

Run saved Jobs to fill the inventory from the twelve actual source cards. The Watch step monitors local inputs and three public URLs; it does not discover every new article or silently update factual rows. All original URLs remain available for deliberate inspection.

## Next useful cycle

Read one consequential source. Retain a new dated finding, correction or explicit no-change check; update and save Assistant Market Inputs. Run the owner's Jobs, inspect the table/chart/inventory changes and review the proposed interpretation. Keep, revert, approve or discard according to the actual change type. Record the remaining uncertainty and next action.

Start manually. Adopt a recurring cadence only after the first and second useful cycles are worth repeating. No scheduled run is enabled by this package.

## Source appendix

[^S01]: [ChatGPT Work and Codex](sources/current/S01-chatgpt-work.md). OpenAI; retrieved 2026-09-15; published claim, product execution not tested.

[^S02]: [Using cloud browser in ChatGPT](sources/current/S02-chatgpt-browser.md). OpenAI; retrieved 2026-09-15; published claim, product execution not tested.

[^S03]: [Schedule actions in Gemini Apps](sources/current/S03-gemini-schedules.md). Google; retrieved 2026-09-15; published claim, product execution not tested.

[^S04]: [About personalization with Connected Apps](sources/current/S04-gemini-context.md). Google; retrieved 2026-09-15; published claim, product execution not tested.

[^S05]: [Get started with Claude Cowork](sources/current/S05-claude-cowork.md). Anthropic; retrieved 2026-09-15; published claim, product execution not tested.

[^S06]: [Using Copilot Tasks](sources/current/S06-copilot-tasks.md). Microsoft; retrieved 2026-09-15; published claim, product execution not tested.

[^S07]: [Advice and Use Cases](sources/current/S07-comet-use.md). Perplexity; retrieved 2026-09-15; published claim, product execution not tested.

[^S08]: [Comet Assistant Privacy and Data Use](sources/current/S08-comet-privacy.md). Perplexity; retrieved 2026-09-15; published claim, product execution not tested.

[^S09]: [Alexa+ US availability and Prime membership](sources/current/S09-alexa-packaging.md). Amazon; retrieved 2026-09-15; published claim, product execution not tested.

[^S10]: [Siri AI is here](sources/current/S10-siri-rollout.md). Apple; retrieved 2026-09-15; published claim, product execution not tested.

[^S11]: [Automations](sources/current/S11-raycast-automations.md). Raycast; retrieved 2026-09-15; published claim, product execution not tested.

[^S12]: [Why We Are Changing How Raycast AI Is Priced](sources/current/S12-raycast-pricing.md). Raycast; retrieved 2026-09-15; published claim, product execution not tested.
