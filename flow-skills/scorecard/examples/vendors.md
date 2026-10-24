# Worked example — Scorecard

## Input

> We shortlisted two support desks. Price matters most, then the
> integrations, then setup time. Helpline is $40 a seat and needs a
> month to set up, but connects to our CRM and billing. Deskly is $25 a
> seat and sets up in a week, though it only connects to the CRM.

## Output

### Deskly leads on price and setup; Helpline on integrations

The text ranks the criteria, so the weights are rank-sum: price 3 parts,
integrations 2, setup 1, of 6.

| Criterion | Weight | Helpline | Deskly |
| --- | ---: | ---: | ---: |
| Price | 50 | 2 | 4 |
| Integrations | 33 | 5 | 3 |
| Setup time | 17 | 2 | 5 |
| **Total** | 100 | **3.0** | **3.8** |

- Price: $40 a seat against $25.
- Integrations: Helpline connects to the CRM and billing; Deskly to the CRM only.
- Setup: a month against a week.

```flowui
component: Form
title: Scorecard sign-off · Support desk shortlist
subtitle: Confirm before the choice goes to purchasing
fields:
  - label: Confirmed
    bind: done
    type: checklist
    options:
      - The criteria match what we need
      - The weights follow our priorities
      - Each score has its reason
  - {label: Signed by, bind: signer}
decision: {label: Sign off, action: sign-off}
```
