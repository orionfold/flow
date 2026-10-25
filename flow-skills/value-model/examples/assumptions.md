# Worked example — Value Model

## Input

> Support handles about 1,200 tickets a month. Their lead estimates
> self-serve intake would remove a third of them. Finance puts the
> loaded cost of a ticket at $18.

## Output

### Self-serve intake saves about $86,400 a year

1,200 tickets a month × a third removed × $18 a ticket = $7,200 a month,
or $86,400 a year.

| Assumption | Value | Unit | From |
| --- | ---: | --- | --- |
| Tickets a month | 1,200 | tickets | Support |
| Share removed | 1/3 | of tickets | Support's lead |
| Cost per ticket | 18 | $ | Finance |

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
