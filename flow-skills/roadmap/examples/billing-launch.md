# Worked example — Roadmap

## Input

> Design for the new billing flow wraps on 3 November 2026. Engineering
> starts the same day and needs six weeks, then two weeks of hardening.
> Finance wants a pricing review once hardening is done, and the launch
> is set for 12 January 2027. Marketing will start the launch page in
> December.

## Output

### Billing hardening ends just before the January launch

```mermaid
gantt
  title Billing hardening ends just before the January launch
  dateFormat YYYY-MM-DD
  section Design
    Design wraps          :milestone, des, 2026-11-03, 0d
  section Engineering
    Build                 :build, 2026-11-03, 42d
    Hardening             :hard, after build, 14d
  section Finance
    Pricing review        :milestone, review, after hard, 0d
  section Launch
    Launch                :milestone, launch, 2027-01-12, 0d
```

Not placed: the marketing launch page has a month (December) but no
length.
