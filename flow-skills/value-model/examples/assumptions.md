# Worked example — Value Model

## Input

> Support handles about 1,200 tickets a month. Their lead estimates
> self-serve intake would remove a third of them. Finance puts the
> loaded cost of a ticket at $18.

## Output

### Self-serve intake saves about $86,400 a year

1,200 tickets a month × a third removed × $18 a ticket = $7,200 a month,
or $86,400 a year.

```flowui
component: Form
title: Value model assumptions · Self-serve intake
subtitle: Change a number and update to keep it in the document
fields:
  - {label: Tickets a month, bind: tickets-per-month, type: number, min: 0}
  - {label: Share removed (%), bind: share-removed, type: number, min: 0, max: 100}
  - {label: Cost per ticket ($), bind: cost-per-ticket, type: number, min: 0}
decision: {label: Update assumptions, action: update}
```

```chart
chartType: Bar Chart
title: Self-serve intake removes a third of the yearly ticket cost
source: Support volume, the lead's estimate and finance's ticket cost
highlight: Saved
data:
  - {part: Ticket cost today, dollars: 259200}
  - {part: Saved, dollars: 86400}
  - {part: Remaining, dollars: 172800}
encodings:
  x: {field: part}
  y: {field: dollars}
```
