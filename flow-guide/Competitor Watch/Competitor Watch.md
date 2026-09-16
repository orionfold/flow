---
title: Competitor Watch
category: research-markets
summary: "Dated competitor observations, refreshed evidence and changes worth reviewing."
tags: [competitive, ai-market, founder]
refresh: manual
jobs:
  - kind: gather
    definition: Market Refresh.md
    into: data
    as: market
  - kind: keep-sources-fresh
    watch: [Market Inputs.md, Founder Profile.md, Founder Decisions.md, sources/current]
  - kind: reconcile-against-folder
    folder: sources/current
  - kind: expand-with-sources
    section: Decision context
    sources: [sources/current, Founder Profile.md, Founder Decisions.md]
---
# Competitor Watch

**What deserves a response, and what can you ignore?** A working research brief for a solo founder building an AI website, Mac app or web app.

Start with eight products and twelve short public source records observed on September 14, 2026. They are dated research inputs, not a current market ranking or firsthand product evaluation. All founder decisions begin undecided.

[Your product and customer](Founder%20Profile.md) · [Editable market inputs](Market%20Inputs.md) · [Decision ledger](Founder%20Decisions.md) · [Research playbook](Research%20Playbook.md)

## This week's decision

**Question:** which recurring customer task deserves our next small experiment? Choose one in the founder profile. Compare the customer's alternatives, the useful result, checking effort, and what happens when they return a week later.

## Decision context

Compare the whole customer task before adding another AI feature. Summation and Raycast publish different ways to define and repeat work. Investigate where results accumulate, how a person corrects them and whether useful context survives a return. Published documentation describes a contract; it does not establish comparative task quality.[^S01][^S04]

Review and permissions affect the cost of trusting a result. Notion's suggested edits and resource grants, together with Lovable's draft and shared-data distinction, offer concrete questions for a founder: what is proposed, what already changed, who can see an input, and which decisions remain with the person? Inspect those boundaries before treating a feature label as evidence.[^S05][^S06][^S07]

Consider a small existing tool as a credible alternative to a new product feature. A purpose-specific app, an AI assistant plus notes, or a simple manual process may satisfy the task. Keep one contrary observation and one affordable experiment beside each proposed response. A quiet week with a trustworthy result can be more valuable than a long report of weak signals.[^S09]

## Evidence at a glance


<!-- data: data/market-*.json#summary -->
| Metric | Value |
| --- | ---: |
| Finding records | 12 |
| Distinct captures | 12 |
| Human-reviewed findings | 0 |

The chart and table below share one Gather output. Counts measure retained research coverage only. The main comparison remains linked to the finding-level Evidence table and source cards.

```chart data: data/market-*.json#coverage
chartType: Bar Chart
title: Retained findings by product
subtitle: This 12-source seed; coverage counts, not capability or market share
source: Market Inputs.md, Evidence table
data:
  - {product: "Bolt", findings: 1}
  - {product: "Glaze", findings: 1}
  - {product: "Lovable", findings: 2}
  - {product: "Notion", findings: 2}
  - {product: "Raycast", findings: 3}
  - {product: "Replit", findings: 1}
  - {product: "Summation", findings: 1}
  - {product: "Underdog", findings: 1}
semantic_types: {product: Category, findings: Count}
encodings:
  y: {field: product}
  x: {field: findings}
  color: {field: product, scheme: teals}
```

<!-- data: data/market-*.json#coverage -->
| Product | Findings |
| --- | --- |
| Bolt | 1 |
| Glaze | 1 |
| Lovable | 2 |
| Notion | 2 |
| Raycast | 3 |
| Replit | 1 |
| Summation | 1 |
| Underdog | 1 |

## Packaging lens

Three Raycast monthly individual offers retained on September 14, 2026 give a concrete, same-publisher comparison. Recheck the original page before a buying decision. This is a dated subscription exposure scenario, not cost per useful AI result or a cross-company ranking.[^S03]

<!-- data: data/market-*.json#comparableCosts -->
| Product | Plan | Minimum monthly USD | Twelve month scenario USD | Credits | Checked at | Source URL |
| --- | --- | --- | --- | --- | --- | --- |
| Raycast | Pro | 10 | 120 | 500 | 2026-09-14 | https://www.raycast.com/blog/changing-how-raycast-ai-is-priced |
| Raycast | Pro+ | 20 | 240 | 3000 | 2026-09-14 | https://www.raycast.com/blog/changing-how-raycast-ai-is-priced |
| Raycast | Max | 50 | 600 | 7500 | 2026-09-14 | https://www.raycast.com/blog/changing-how-raycast-ai-is-priced |


## Founder decisions

Use the [decision ledger](Founder%20Decisions.md) to choose act, investigate, watch or ignore. Record why, the counterevidence and the event that should reopen the decision. Jobs expands decision context; it does not choose a disposition for you.

## Work on the next useful output

| Document | Purpose |
| --- | --- |
| [Founder Briefing](Founder%20Briefing.md) | Summarize analysis you deliberately prepare |
| [Launch Copy](Launch%20Copy.md) | Proofread a short announcement |
| [Localized Update](Localized%20Update.md) | Translate an update while keeping its reference |
| [Launch Notes](Launch%20Notes.md) | Turn structured observations into a table |
| [Comparison Narrative](Comparison%20Narrative.md) | Explain a comparison table as bullets |
| [Research Map](Research%20Map.md) | Add a diagram of the research process |
| [Research Image](Research%20Image.md) | Describe the supplied picture for accessible alt text |

Each document owns its Jobs and its review. Choose a document, inspect its method and Inputs, then Run Jobs. Ask can propose edits to the method; Apply changes the draft, and Save Jobs writes it. Neither action starts a run.

## Sources worth opening


- [S01 · Workflows — Summation](sources/current/S01-summation.md) — Separate method, trigger and delivery; make test/run effects explicit.
- [S02 · Underdog — The Most Loyal AI](sources/current/S02-underdog.md) — State where inference, memory and network activity happen separately.
- [S03 · Why Raycast AI pricing is changing](sources/current/S03-raycast.md) — Explain application value, model cost and recurring-work exposure separately.
- [S04 · Automations — Raycast Manual](sources/current/S04-raycast.md) — Compare accumulated outputs and correction quality, plus sleep/permission/recovery behavior.
- [S05 · What is new — suggested edits and model controls](sources/current/S05-notion.md) — Treat proposed editing as a baseline expectation; test evidence, scope and correction.
- [S06 · Custom Agents sharing and permissions](sources/current/S06-notion.md) — Make adopted methods separate from adopted credentials and access grants.
- [S07 · Lovable changelog — drafts and usage](sources/current/S07-lovable.md) — Explain what a draft isolates and what remains shared; attribute multi-tool cost.
- [S08 · Security overview — Lovable](sources/current/S08-lovable.md) — Display coverage and freshness of checks; re-read sources before repeating old claims.
- [S09 · Meet Glaze — Raycast](sources/current/S09-glaze.md) — Test whether a custom small app can substitute for the proposed feature.
- [S10 · stackblitz/bolt.new — public repository](sources/current/S10-bolt.md) — Inspect reusable infrastructure; separate visible source facts from inferred implementation.
- [S11 · Replit incident history](sources/current/S11-replit.md) — Design recovery for model/tool failure and distinguish builder versus hosted-app incidents.
- [S12 · Raycast AI, Notes and more — US App Store](sources/current/S12-raycast.md) — Investigate where useful outputs go after an AI session and what breaks that handoff.


## Capture inventory

```flow-folder sources/current
| File | Size | Modified | Digest |
| --- | ---: | --- | --- |
```

Run Jobs to fill the inventory from your source cards. The twelve cards are short retained paraphrases with original links and dates. The profile and decision ledger supply founder context, not competitor facts. Add a public URL to Watch sources only when you want its subsequent changes checked; a watched page is separate from the local evidence used for expansion.

## Next useful cycle

Inspect a material source, retain a dated finding, and update Market Inputs. A second distinct finding from the same capture increases finding count without increasing distinct captures. Mark human review only after doing it. Run saved Jobs to redraw the linked chart and tables, then review the proposed expansion beside the document.

After accepting analysis, explicitly prepare the material in Founder Briefing and run its Summary Job afresh. Approval never starts another document's Jobs. This copy starts with manual timing; change Jobs timing explicitly when you are ready for automatic repeat work.

## Source appendix



[^S01]: [Workflows — Summation](sources/current/S01-summation.md). Summation; retrieved 2026-09-14; published / public documentation.

[^S02]: [Underdog — The Most Loyal AI](sources/current/S02-underdog.md). Underdog; retrieved 2026-09-14; published / live browser marketing.

[^S03]: [Why Raycast AI pricing is changing](sources/current/S03-raycast.md). Raycast; retrieved 2026-09-14; published / official announcement.

[^S04]: [Automations — Raycast Manual](sources/current/S04-raycast.md). Raycast; retrieved 2026-09-14; published / public documentation.

[^S05]: [What is new — suggested edits and model controls](sources/current/S05-notion.md). Notion; retrieved 2026-09-14; published / official release log.

[^S06]: [Custom Agents sharing and permissions](sources/current/S06-notion.md). Notion; retrieved 2026-09-14; published / public documentation.

[^S07]: [Lovable changelog — drafts and usage](sources/current/S07-lovable.md). Lovable; retrieved 2026-09-14; published / official release log.

[^S08]: [Security overview — Lovable](sources/current/S08-lovable.md). Lovable; retrieved 2026-09-14; published / live public documentation.

[^S09]: [Meet Glaze — Raycast](sources/current/S09-glaze.md). Glaze; retrieved 2026-09-14; published / official launch.

[^S10]: [stackblitz/bolt.new — public repository](sources/current/S10-bolt.md). Bolt; retrieved 2026-09-14; published / public source repository.

[^S11]: [Replit incident history](sources/current/S11-replit.md). Replit; retrieved 2026-09-14; published / official operational record.

[^S12]: [Raycast AI, Notes and more — US App Store](sources/current/S12-raycast.md). Raycast; retrieved 2026-09-14; published / developer listing and customer anecdote.
