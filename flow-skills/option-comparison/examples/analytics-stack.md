# Worked example — Option Comparison

## Input

> For the new analytics stack we can build on our warehouse, which the
> data team prices at $120k in the first year and four months of work;
> rent a hosted product at $40k a year, live in three weeks, though our
> data then leaves our cloud; or keep the spreadsheets we have, which
> costs nothing new but cannot handle next year's volume.

## Output

### The spreadsheets cost nothing new but cannot grow; renting is the cheapest change

| Option | First-year cost | Time to live | Data stays in our cloud |
| --- | --- | --- | --- |
| Build on the warehouse | $120k | Four months | Yes |
| Rent a hosted product | $40k | Three weeks | No |
| Keep the spreadsheets | Nothing new | Already live | Yes |

```chart
chartType: Bar Chart
title: Renting costs a third of building in the first year
source: The data team's pricing
data:
  - {option: Build on the warehouse, cost: 120000}
  - {option: Rent a hosted product, cost: 40000}
  - {option: Keep the spreadsheets, cost: 0}
encodings:
  x: {field: option}
  y: {field: cost}
```

Renting costs $80k less than building but the data leaves our cloud, and
the spreadsheets, which cost nothing new, cannot handle next year's volume.
