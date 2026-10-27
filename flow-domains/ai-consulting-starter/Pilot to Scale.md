---
title: Pilot to Scale
order: 4
---

# Pilot to Scale

The [Press Release FAQ for AI project](Press%20Release%20FAQ%20for%20AI%20project.md) gets you to the right AI project, described from the customer's side before you build. This document covers what comes after the PR/FAQ is approved: running a pilot that answers a real question, then either carrying it into production or stopping it cleanly.

The AI pilots I have seen stall for the same reasons good intentions fail. No one owns them, no one agreed what success looks like, and no one inspects them on a schedule. The fix is the same one this Domain uses everywhere: a tool, adoption and inspection ([Mechanisms Primer](Mechanisms%20Primer.md)).

## A pilot is a question, not a demo

A demo shows that something can work. A pilot answers whether it works well enough, on real cases, at a cost the business accepts. Write the pilot down before it starts. The example column is illustrative, not a client result.

| Field | What to write | Example: an AI assistant for billing questions |
|---|---|---|
| The question | The one thing the pilot must answer | Can the assistant answer routine billing questions correctly without a person? |
| Input metric | What the team can move directly | Share of answers a reviewer accepts, on a fixed set of real past questions |
| Output metric | The business result you hope follows | Fewer billing tickets reaching staff |
| Pass bar | The result that means go | Taken from the acceptance standard in the PR/FAQ |
| Stop bar | The result or event that means stop | A wrong answer about money reaches a customer more than once |
| Time box | When you decide | A fixed number of weeks, agreed before the start |
| Door | Can you undo it? | Two-way while it runs on the test set. One-way once customers, data or contracts depend on it |

## The mechanisms that carry a pilot

Each of these is listed with its public source in [Amazon Mechanisms and Practices](Amazon%20Mechanisms%20and%20Practices.md).

| Mechanism | Tool | Adoption | Inspection |
|---|---|---|---|
| Single-threaded leadership | One named owner whose whole job is this pilot | The owner is named in the PR/FAQ before work starts | Every WBR starts with the owner's update |
| Controllable input metrics | A short list of metrics the team can move | Every change to the system is tied to one of them | Reviewed every week next to the output metric |
| One-way versus two-way doors | A label on each decision | The owner makes two-way decisions fast. One-way decisions go to whoever approved the PR/FAQ | The doors are checked again before production |
| WBR: Weekly Business Review | The same metrics, in the same order, every week | Held every week, even when nothing changed | Every movement in a metric is explained or flagged |
| COE: Correction of Error, with Five Whys | A written review of what went wrong and why | Written for every failure that reaches a customer | The fix goes into the system, the test set or the ORR, not into a promise to try harder |
| ORR: Operational Readiness Review | A checklist built from past failures | Passed before the pilot reaches production | The checklist grows with each COE |

When a wrong answer could reach a customer, add an Andon Cord as well: a way for anyone, whether the owner, a reviewer or a member of staff, to stop the assistant at once without asking permission. It lets people act on the stop bar the moment they see a problem, and every pull of the cord gets a COE.

## From pilot to production, step by step

1. **Name the owner.** One person, and this is their whole job.
2. **Turn the PR/FAQ into the pilot question.** The hardest answers in its FAQ usually become the question.
3. **Fix a test set of real cases,** and write down which data the pilot is allowed to use.
4. **Run the WBR every week,** starting in week one.
5. **Write a COE for every failure that reaches a customer,** and add the case to the test set.
6. **Pass the ORR** before any customer depends on the system.
7. **Decide at the time box.** Scale it, change the question and run again, or stop. Write the answer back into the PR/FAQ, so the next pilot starts from what you learned.

Stopping is a good outcome when the pilot answered its question.

## Ready for production?

- [ ] One owner is named, and the pilot is their whole job.
- [ ] The pass bar was met on a test set of real cases.
- [ ] Every failure that reached a customer has a COE, with the fix in the system.
- [ ] The ORR is passed, and whoever approved the PR/FAQ has signed it off.
- [ ] Someone knows the cost of each use at production volume.
- [ ] There is a plan for when the model or provider changes.
- [ ] The one-way doors are listed, and the approver has agreed to each.
- [ ] The WBR continues after launch.

## An example from this Domain

The loop in this document is the one Orionfold follows with its own products. In [Flow PR/FAQ](Flow%20PR-FAQ.md), a client building on Relay asked for private Git repository publishing, and the feature was documented as shipped the following day. A real user's need was inspected and written back into the product. That case describes what was done, not a business result, and no client result from a pilot is claimed here yet.

## Try it in Flow

1. Open your PR/FAQ from document 3, and ask Chat to draft the pilot table above from its FAQ.
2. Set the pass and stop bars yourself. They are your judgment, not the model's.
3. Ask Chat to turn the mechanism table into a WBR agenda and an ORR checklist for your project.
4. Run Proofread, review the result against your acceptance standard and publish it in the format your client needs.

This is the last document on the path. Go back to the [README](README.md) to start again with your next project.