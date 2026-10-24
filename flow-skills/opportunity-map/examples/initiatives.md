# Worked example — Opportunity Map

## Input

> This quarter we could ship self-serve intake, which support says would
> remove a third of their tickets and takes one engineer two weeks. A
> billing rewrite would fix the invoicing errors finance complains about
> but needs three engineers for a quarter and a migration. A dark-mode
> theme is a common request with little revenue behind it; a designer
> estimates a week. Replatforming search onto a new engine would cut
> hosting cost slightly and take two months of the platform team.

## Output

### One quick win leads the list

```chart
chartType: Scatter Plot
title: Self-serve intake is the clear quick win
source: Quarter planning notes
data:
  - {initiative: Self-serve intake, effort: 2, value: 8, quadrant: Quick win}
  - {initiative: Billing rewrite, effort: 9, value: 7, quadrant: Big bet}
  - {initiative: Dark mode, effort: 2, value: 3, quadrant: Fill-in}
  - {initiative: Search replatform, effort: 8, value: 3, quadrant: Reconsider}
encodings:
  x: {field: effort}
  y: {field: value}
```

| Initiative | Value | Effort | Quadrant | Why |
| --- | ---: | ---: | --- | --- |
| Self-serve intake | 8 | 2 | Quick win | Removes a third of support tickets for two engineer-weeks. |
| Billing rewrite | 7 | 9 | Big bet | Fixes finance's invoicing errors but takes three engineers a quarter and a migration. |
| Dark mode | 3 | 2 | Fill-in | Often asked for, little revenue, about a designer-week. |
| Search replatform | 3 | 8 | Reconsider | A slight hosting saving for two months of the platform team. |
