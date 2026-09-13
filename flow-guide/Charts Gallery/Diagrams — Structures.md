---
title: Diagrams — Structures
tags: [charts-gallery, reference, fictional-example]
---
# Diagrams — Structures

[[Charts Gallery]] · Previous: [[Diagrams — Processes]] · Next: [[Diagrams — Connections]]

**Make relationships and boundaries explicit.**

> Every exhibit on this page uses fictional teaching data or an authored scenario. Source labels describe the example; they are not reports, measured Flow benchmarks or product guarantees.

| Form | Use it for |
| --- | --- |
| Class diagram | Describe conceptual entities, their fields and relationships |
| Entity-relationship diagram | Describe records, keys and relationships |
| Block diagram | Arrange a small set of components to explain responsibilities |
| Requirement diagram | Connect an authored requirement to its proposed verification and components |
| C4 context diagram | Show people, a system and its external neighbours |
| Architecture diagram | Describe services, stores and deployment groups |
| Packet diagram | Describe the bit layout of a fictional binary header |

Use the smallest structural view that answers the question: conceptual records, components, system context or a physical record layout.

## The exhibits

### Class diagram

Describe conceptual entities, their fields and relationships. Multiplicity and ownership should have a defined meaning; this is an illustrative model, not Flow source code.

Source: a description of the nouns in a system and how they relate: the data model behind a product, with fields and one-to-many relationships.

```mermaid
classDiagram
  class Workspace {
    +UUID id
    +String name
    +open(folder)
  }
  class Folder {
    +URL root
    +Bookmark bookmark
    +enumerate()
  }
  class Note {
    +String path
    +Data bytes
    +Frontmatter metadata
    +save()
  }
  class Receipt {
    +String action
    +String provider
    +Digest afterSHA256
  }
  class Proposal {
    +String baseText
    +String proposedText
    +approve()
    +discard()
  }
  Workspace "1" o-- "*" Folder
  Folder "1" *-- "*" Note
  Note "1" --> "*" Receipt : records
  Note "1" --> "0..1" Proposal : pending
  Proposal --> Receipt : produces
```

[[Charts Gallery]]

### Entity-relationship diagram

Describe records, keys and relationships. Confirm cardinality with the data owner; a diagram is not a database migration.

Source: a list of tables with their keys and how rows reference one another: a database schema, or a CRM's objects.

```mermaid
erDiagram
  ACCOUNT ||--o{ CONTACT : has
  ACCOUNT ||--o{ SUBSCRIPTION : pays
  SUBSCRIPTION ||--|{ SEAT : allocates
  CONTACT ||--o{ SEAT : occupies
  SUBSCRIPTION ||--o{ INVOICE : bills
  ACCOUNT {
    uuid id PK
    string name
    string segment
    date created_at
  }
  CONTACT {
    uuid id PK
    uuid account_id FK
    string email
    string role
  }
  SUBSCRIPTION {
    uuid id PK
    uuid account_id FK
    string plan
    int seats
    date renews_at
  }
  SEAT {
    uuid id PK
    uuid subscription_id FK
    uuid contact_id FK
  }
  INVOICE {
    uuid id PK
    uuid subscription_id FK
    decimal amount
    string status
  }
```

[[Charts Gallery]]

### Block diagram

Arrange a small set of components to explain responsibilities. Keep arrows labelled or obvious and avoid implying that visual proximity is a connection.

Source: a description of components and how they sit beside and connect to each other: an architecture sketch, a deployment layout.

```mermaid
block-beta
  columns 3
  App["Example workspace"]:3
  Editor["Editor\nMarkdown, rendered in place"] Agency["Agency\napproval + receipts"] Search["Search\nexact + semantic"]
  space:3
  Runtime["Local processor\non this device"] Apple["Text tools"] Hosted["Hosted API\n(optional)"]
  Agency --> Runtime
  Agency --> Apple
  Agency --> Hosted
  Editor --> Agency
  Search --> Editor
```

[[Charts Gallery]]

### Requirement diagram

Connect an authored requirement to its proposed verification and components. A satisfies arrow records an assertion, not completed compliance or test evidence.

Source: a list of requirements with identifiers, risk and verification method, and which components satisfy them: a compliance or safety document. These are fictional requirements and components, not verified Flow guarantees.

```mermaid
requirementDiagram
  requirement privacy_req {
    id: R1
    text: "Example requirement - document processing stays on the device."
    risk: high
    verifymethod: test
  }
  requirement receipt_req {
    id: R2
    text: "Example requirement - approved edits have an audit record."
    risk: medium
    verifymethod: inspection
  }
  element runtime {
    type: component
    docref: Example Processor
  }
  element receipts {
    type: component
    docref: Example Audit Store
  }
  runtime - satisfies -> privacy_req
  receipts - satisfies -> receipt_req
  receipt_req - refines -> privacy_req
```

[[Charts Gallery]]

### C4 context diagram

Show people, a system and its external neighbours. Keep the level of detail consistent and state the system boundary before drilling into components.

Source: a paragraph naming the system, the people who use it, and the external systems it talks to: the top of an architecture document.

```mermaid
C4Context
  title Example workspace: system context
  Person(writer, "Writer", "Creates source-based working documents")
  Person(reviewer, "Reviewer", "Approves or discards proposed changes")
  System(flow, "Example workspace", "Editor, proposals and review records")
  System_Ext(apple, "Local processor", "Text transformations on this device")
  System_Ext(hosted, "Hosted model API", "Optional, key held in Keychain")
  SystemDb_Ext(vault, "Markdown folders", "Plain .md files the user owns")
  Rel(writer, flow, "Writes, dictates, runs actions")
  Rel(reviewer, flow, "Reviews proposals")
  Rel(flow, apple, "Requests rewrites", "on-device")
  Rel(flow, hosted, "Requests generations", "HTTPS, opt-in")
  Rel(flow, vault, "Reads and writes")
```

[[Charts Gallery]]

### Architecture diagram

Describe services, stores and deployment groups. The picture records an intended arrangement; it neither provisions infrastructure nor proves a privacy boundary.

Source: a list of services, the stores they use and the edges between them, grouped by where they run: a deployment diagram.

```mermaid
architecture-beta
  group mac(cloud)[Mac]
  service app(server)[Example app] in mac
  service runtime(server)[Local processor] in mac
  service disk(disk)[Markdown folders] in mac
  service keychain(database)[Keychain] in mac
  group cloud(cloud)[Internet]
  service api(internet)[Hosted model API] in cloud
  app:R --> L:runtime
  app:B --> T:disk
  app:L --> R:keychain
  app:T --> B:api
```

[[Charts Gallery]]

### Packet diagram

Describe the bit layout of a fictional binary header. State field widths and total size; do not use this sample as an actual Flow file-format specification.

Source: a field-by-field layout of a binary record or header, with bit offsets: a protocol note or a file-format spec.

```mermaid
packet-beta
  title Fictional record header
  0-7: "Version"
  8-15: "Action"
  16-31: "Provider id"
  32-63: "Timestamp"
  64-95: "Document id"
  96-127: "Length"
  128-255: "After-digest (SHA-256, first half)"
```

[[Charts Gallery]]

## Use a form with your own records

Copy the whole **Charts Gallery** folder and add that copy to Flow first. Open [[Gallery Data]] to practise with a table you can edit. [[Charts — Living Example]] shows the refresh path. These reference exhibits keep their own embedded examples; they do not change when the practice table changes.

For a new exhibit, open a suitable example in the chart editor or select your own source rows and use Visualize. Keep the units and source explanation with the result. Visualize uses your configured Agency route; inspect its proposal before applying. Authored Mermaid diagrams need deliberate text edits; they are not automatically maintained from the table.

[[Charts Gallery]] · Previous: [[Diagrams — Processes]] · Next: [[Diagrams — Connections]]
