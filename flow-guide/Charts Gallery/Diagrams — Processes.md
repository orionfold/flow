---
title: Diagrams — Processes
tags: [charts-gallery, reference, fictional-example]
---
# Diagrams — Processes

[[Charts Gallery]] · Previous: [[Charts — Patterns]] · Next: [[Diagrams — Structures]]

**Explain what happens, who acts and what changes state.**

> Every exhibit on this page uses fictional teaching data or an authored scenario. Source labels describe the example; they are not reports, measured Flow benchmarks or product guarantees.

| Form | Use it for |
| --- | --- |
| Flowchart | Explain steps and decisions, including the paths a person can take |
| Sequence diagram | Show actors exchanging messages in order |
| State diagram | Define allowed states and the events between them |
| Gantt (Mermaid) | Write a dependency-oriented schedule as text |
| User journey | Summarize a sequence of tasks and an explicitly subjective experience rating |
| Kanban board | Group an authored task list by status |

Choose sequence for exchanges, state for permitted transitions and a flowchart for decisions. They explain different aspects of a process.

## The exhibits

### Flowchart

Explain steps and decisions, including the paths a person can take. Treat arrows as an authored process; they do not execute an approval or send a message.

Source: a numbered list of steps with decisions written as questions: a process, an approval path, a troubleshooting guide.

```mermaid
flowchart TD
  A[Customer submits request] --> B{Within policy?}
  B -->|Yes| C[Auto-approve]
  B -->|No| D[Route to reviewer]
  D --> E{Needs legal?}
  E -->|Yes| F[Legal review]
  E -->|No| G[Manager decision]
  F --> G
  G -->|Approved| C
  G -->|Declined| H[Send decline with reason]
  C --> I[Notify customer]
  H --> I
  I --> J([Close ticket])
```

[[Charts Gallery]]

### Sequence diagram

Show actors exchanging messages in order. Name the boundary and failure path; the diagram is a scenario, not a trace captured from a live system.

Source: prose or a list describing who sends what to whom, in order: an integration, a support escalation, an approval exchange between people or systems.

```mermaid
sequenceDiagram
  autonumber
  actor U as User
  participant F as Example editor
  participant R as Local processor
  participant K as Example key store
  U->>F: Select text, press ⇧⌘V
  F->>F: Build proposal request
  F->>R: Generate chart fence
  R-->>F: ```chart body
  F->>F: Render gate: does it draw?
  alt Renders
    F-->>U: Review pane with the chart drawn
    U->>F: Approve
    F->>F: Write file, record receipt
  else Fails to render
    F-->>U: Notice with the renderer's reason
  end
  Note over F,K: This fictional scenario uses only the local processor
```

[[Charts Gallery]]

### State diagram

Define allowed states and the events between them. Keep state names distinct from actions and account for endings or reversals.

Source: a list of states and the events that move between them: a document lifecycle, an order status, a subscription.

```mermaid
stateDiagram-v2
  [*] --> Draft
  Draft --> InReview: submit
  InReview --> Draft: request changes
  InReview --> Approved: approve
  Approved --> Published: publish
  Published --> Archived: retire
  Draft --> Archived: abandon
  Archived --> [*]
  state InReview {
    [*] --> Assigned
    Assigned --> Reviewing: reviewer opens
    Reviewing --> Commented: leaves notes
    Commented --> Reviewing: author replies
  }
```

[[Charts Gallery]]

### Gantt (Mermaid)

Write a dependency-oriented schedule as text. This example is separate from the chart Gantt; neither proves a planned task completed.

Source: a list of tasks with durations and dependencies, in sections: a project plan written as prose, when you want milestones and "after X" dependencies rather than fixed dates.

```mermaid
gantt
  title Q4 release plan
  dateFormat YYYY-MM-DD
  axisFormat %b %d
  section Design
    Design freeze          :done, des, 2026-09-01, 12d
  section Engineering
    Build                  :active, build, 2026-09-08, 40d
    Hardening              :hard, after build, 10d
  section Beta
    Private beta           :beta, 2026-10-06, 54d
    Beta exit review       :milestone, m1, 2026-11-28, 0d
  section Launch
    Docs and briefs        :docs, 2026-10-20, 32d
    Launch prep            :prep, after docs, 14d
    Launch                 :crit, milestone, 2026-12-08, 0d
```

[[Charts Gallery]]

### User journey

Summarize a sequence of tasks and an explicitly subjective experience rating. Say whose experience the ratings describe; this sample is not a user-research result.

Source: a walkthrough of what a person does, step by step, with how each step felt: research synthesis, a support transcript, an onboarding review.

```mermaid
journey
  title A fictional writer's first review
  section Install
    Read the brief: 4: User
    Open the project folder: 5: User
    Locate the source table: 3: User
  section First write
    Open a folder: 4: User
    Update a paragraph: 5: User
    Review the chart: 5: User, Reviewer
  section Trust
    Compare with the source: 4: User
    Approve the change: 5: User
```

[[Charts Gallery]]

### Kanban board

Group an authored task list by status. Moving a card in text changes this document; it does not update an external project-management system.

Source: a task list grouped by status: the sprint board as columns of cards with owners.

```mermaid
kanban
  Backlog
    gallery[Source inventory]@{ assigned: 'Dana', priority: 'High' }
    onboard[Review agenda]@{ assigned: 'Dana' }
  In progress
    shots[Figures for the review pack]@{ assigned: 'Dana', priority: 'High' }
  Review
    newline[Check source references]@{ ticket: 'EX-02' }
  Done
    visualize[First chart]@{ ticket: 'EX-03' }
    dictate[Meeting notes]@{ ticket: 'EX-04' }
```

[[Charts Gallery]]

## Use a form with your own records

Copy the whole **Charts Gallery** folder and add that copy to Flow first. Open [[Gallery Data]] to practise with a table you can edit. [[Charts — Living Example]] shows the refresh path. These reference exhibits keep their own embedded examples; they do not change when the practice table changes.

For a new exhibit, open a suitable example in the chart editor or select your own source rows and use Visualize. Keep the units and source explanation with the result. Visualize uses your configured Agency route; inspect its proposal before applying. Authored Mermaid diagrams need deliberate text edits; they are not automatically maintained from the table.

[[Charts Gallery]] · Previous: [[Charts — Patterns]] · Next: [[Diagrams — Structures]]
