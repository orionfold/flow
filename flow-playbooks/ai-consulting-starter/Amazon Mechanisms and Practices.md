---
title: Amazon Mechanisms and Practices
order: 2
source: "https://chatgpt.com/share/6ade48da-a9dc-83e8-a2d1-e39baba5ed30"
source-fetched: "2026-10-25T18:23:02Z"
source-digest: 1e4d1683cd0650f251a8359acde9523cfd83601ac55cfd8192bf2be1e5f40085
---

# Amazon Mechanisms and Practices

## Executive summary

This page lists 24 Amazon mechanisms and practices that are described in public. Some are full mechanisms, with a tool, adoption and inspection. Others are decision rules and mental models that support them.

Not all of them belong in AI Consulting Starter. These are the ones the Domain uses, and where:

| Pick | Where it shows up in the Domain | Why it matters for adopting AI |
| --- | --- | --- |
| Six-page narrative and silent reading | [Press Release FAQ for AI project](Press%20Release%20FAQ%20for%20AI%20project.md), whose review starts with silent reading | Makes the case for an AI investment in full sentences, so the gaps in the reasoning show before the meeting decides. |
| Working Backwards | [Press Release FAQ for AI project](Press%20Release%20FAQ%20for%20AI%20project.md) | Starts from the customer's problem, not from the model, which is the easiest mistake to make with AI. |
| PR/FAQ | [Press Release FAQ for AI project](Press%20Release%20FAQ%20for%20AI%20project.md) | Describes the AI product from the customer's side before anything is built, and puts the hard questions about cost, accuracy and trust in the FAQ. |
| Tenets | [Mechanisms Primer](Mechanisms%20Primer.md); [Press Release FAQ for AI project](Press%20Release%20FAQ%20for%20AI%20project.md) | Settles recurring AI trade-offs, such as accuracy against speed or automation against human review, once instead of in every meeting. |
| Controllable input metrics | [Press Release FAQ for AI project](Press%20Release%20FAQ%20for%20AI%20project.md); [Pilot to Scale](Pilot%20to%20Scale.md) | Separates what an AI team can move, such as accuracy on real cases or adoption, from the business outcome it hopes for. |
| One-way versus two-way doors | [Press Release FAQ for AI project](Press%20Release%20FAQ%20for%20AI%20project.md); [Pilot to Scale](Pilot%20to%20Scale.md) | A pilot is usually a two-way door and should move fast. Committing customers, data or contracts to a model may be a one-way door. |
| Single-threaded leadership | [Pilot to Scale](Pilot%20to%20Scale.md) | Gives an AI initiative one owner whose whole job it is, so the pilot does not stall between teams. |
| WBR — Weekly Business Review | [Pilot to Scale](Pilot%20to%20Scale.md) | The inspection that keeps a pilot honest: the same metrics every week, with every change explained. |
| COE — Correction of Error, with Five Whys | [Pilot to Scale](Pilot%20to%20Scale.md) | Turns an AI failure, such as a wrong answer reaching a customer, into a fix in the system instead of a promise to try harder. |
| ORR — Operational Readiness Review | [Pilot to Scale](Pilot%20to%20Scale.md) | A checklist a pilot must pass before it reaches production, built from what has gone wrong before. |
| Andon Cord | [Pilot to Scale](Pilot%20to%20Scale.md), for pilots where a wrong answer could reach a customer | Lets anyone stop an AI feature that is harming customers at once, and every pull gets a COE, so stopping is safe and leads to a fix. |

The rest are kept here as reference: two-pizza teams, OP1 and OP2, MBR and QBR, S-Team goals, the Bar Raiser, the interview loop, the 70% guideline, Disagree and Commit, early escalation, flywheel thinking and the Leadership Principles. They matter at Amazon, but they are more about running a company or hiring than about adopting AI.

## What counts as a mechanism

Amazon calls a process a mechanism when it combines a tool, adoption and inspection, and runs again and again. The [front page of this Domain](README.md) explains the three parts and why a mechanism beats good intentions.

## Mechanisms

### Product development, communication and ownership

| Mechanism | How it is useful |
| --- | --- |
| [**Working Backwards**](https://www.aboutamazon.com/news/workplace/an-insider-look-at-amazons-culture-and-processes) | Start with a specific customer, their problem, and the desired experience, then determine what to build. Helps establish customer value before committing resources. |
| [**PR/FAQ — Press Release and Frequently Asked Questions**](https://coda.io/@colin-bryar/working-backwards-how-write-an-amazon-pr-faq)**†** | Describe a proposed product as though it has launched, then answer difficult customer and business questions. Makes the Working Backwards idea concrete enough to challenge and refine. |
| [**Six-page narrative and silent reading**](https://www.aboutamazon.com/news/company-news/2017-letter-to-shareholders) | Write a coherent argument that participants read at the start of the meeting. Encourages deeper thinking and gives everyone shared context before discussion. |
| [**Tenets**](https://aws.amazon.com/blogs/enterprise-strategy/tenets-supercharging-decision-making/) | Define a small set of explicit principles for a team, product, or initiative. Helps people resolve recurring trade-offs consistently without escalating every decision. |
| [**Single-threaded leadership / ownership**](https://aws.amazon.com/blogs/enterprise-strategy/two-pizza-teams-are-just-the-start-accountability-and-empowerment-are-key-to-high-performing-agile-organizations-part-2/) | Give a leader focused responsibility for an initiative, with clear accountability. Reduces competing priorities and provides leadership support while preserving team autonomy. |
| [**Two-pizza teams**](https://aws.amazon.com/executive-insights/content/amazon-two-pizza-team/) | Organize small, autonomous teams around a bounded product or service with lifecycle ownership. Reduces coordination overhead and accelerates experimentation and delivery. |

### Planning, measurement and business inspection

| Mechanism | How it is useful |
| --- | --- |
| **OP1 — Operating Plan 1****†** | Develop and review annual plans connecting customer opportunities, initiatives, metrics, and resource requests. Makes investment choices and trade-offs explicit across teams. |
| **OP2 — Operating Plan 2****†** | Update OP1 using actual year-end results and revised priorities and allocations. Establishes the operating baseline for execution. |
| [**WBR — Weekly Business Review**](https://commoncog.com/the-amazon-weekly-business-review/) | Inspect business and customer metrics every week, investigating changes and checking progress toward goals. Creates a frequent opportunity to detect problems and correct course. |
| **MBR / QBR — Monthly and Quarterly Business Reviews** | Review metrics, trends, risks, tensions, and opportunities over longer intervals. Supports broader performance discussions and leadership oversight. |
| **Controllable input metrics****†** | Track customer-facing activities and conditions teams can influence, alongside business outcomes. Helps identify actionable levers for improvement. |
| [**Senior leadership goals / S-Team goals**](https://www.sec.gov/Archives/edgar/data/1018724/000119312510082914/dex991.htm) | Assign important goals explicit owners, deliverables, and completion dates, then review them regularly. Keeps leadership attention on consequential commitments. |

### Quality, operational learning and hiring

| Mechanism | How it is useful |
| --- | --- |
| [**COE — Correction of Error**](https://aws.amazon.com/blogs/mt/why-you-should-develop-a-correction-of-error-coe/) | Document an incident’s impact, causes, response, and preventive actions. Turns failures into improvements that reduce recurrence and improve detection and recovery. |
| [**Five Whys**](https://aws.amazon.com/blogs/mt/why-you-should-develop-a-correction-of-error-coe/) | Repeatedly ask why a problem occurred to uncover underlying conditions. Used within COEs to move beyond symptoms and individual blame toward systemic fixes. |
| [**ORR — Operational Readiness Review**](https://docs.aws.amazon.com/wellarchitected/latest/operational-readiness-reviews/wa-operational-readiness-reviews.html) | Inspect a service against readiness requirements before launch and periodically afterward. Converts lessons from past incidents into checks that prevent repeat failures. |
| [**Andon Cord**](https://www.aboutamazon.co.uk/news/retail/amazon-and-product-safety) | Empower employees to trigger intervention when they identify a serious customer problem. Amazon’s product-safety example triggers investigation and removal of unsafe products. |
| [**Bar Raiser**](https://www.aboutamazon.com/news/workplace/how-amazon-hires) | Include a trained interviewer outside the hiring team to provide an independent perspective. Protects long-term hiring standards against immediate staffing pressure. |
| [**Structured interview loop and debrief**](https://www.aboutamazon.com/news/workplace/how-amazon-hires) | Gather specific evidence through multiple interviews, then evaluate it against role requirements and Leadership Principles. Provides a consistent basis for hiring decisions. |

## Decision rules and mental models

These practices are not mechanisms on their own, but they support the mechanisms above.

| Practice | How it is useful |
| --- | --- |
| [**One-way versus two-way doors**](https://www.aboutamazon.com/news/company-news/2016-letter-to-shareholders) | Distinguish hard-to-reverse decisions from reversible ones. Apply greater deliberation to the former and lighter, faster processes to the latter. |
| [**The “70% information” guideline**](https://www.aboutamazon.com/news/company-news/2016-letter-to-shareholders) | Make many decisions before all desired information is available, while retaining the ability to recognize mistakes and course-correct. Helps avoid excessive analysis and delay. |
| [**Disagree and Commit**](https://www.aboutamazon.com/news/company-news/2016-letter-to-shareholders) | Encourage candid disagreement before a decision, followed by sincere support for execution. Enables progress without requiring unanimous agreement. |
| [**Early escalation of misalignment**](https://www.aboutamazon.com/news/company-news/2016-letter-to-shareholders) | Escalate fundamental conflicts in objectives or direction promptly. Prevents unresolved disagreements from becoming prolonged negotiations decided by exhaustion. |
| **Flywheel thinking** | Identify reinforcing relationships among customer value, experience, adoption, feedback, and experimentation. Helps select investments that compound one another’s benefits. |
| [**Leadership Principles**](https://www.amazon.jobs/content/en/our-workplace/leadership-principles) | Provide shared expectations for judgment, behavior, ownership, and standards. Give teams common language for making decisions and assessing how results are achieved. |

## About the sources

Links go to Amazon's or AWS's own pages where one exists. **†** marks a firsthand account from former Amazon executives Colin Bryar and Bill Carr, authors of *Working Backwards*. Entries without a link have no authoritative public source linked yet, and the WBR link goes to a secondary source.

```flowui
component: Sources
```
