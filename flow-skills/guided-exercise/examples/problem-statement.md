# Worked example — Guided Exercise

## Input

> A good problem statement names who has the problem, what they are
> trying to do, and what gets in the way — before it mentions any
> solution. Write it in one sentence, then test it by asking whether a
> customer would recognise it.

## Output

### Try it: write a problem statement

Work through the prompts for a problem you are looking at now.

```flowui
component: Form
title: Exercise · Writing a problem statement
subtitle: For a problem you are working on now
fields:
  - {label: Who has the problem, bind: who}
  - {label: What they are trying to do, bind: goal}
  - {label: What gets in the way, bind: obstacle}
  - {label: Your problem statement in one sentence, bind: statement}
  - label: Done
    bind: done
    type: checklist
    options:
      - It names who, what and the obstacle
      - It mentions no solution
      - A customer would recognise it
  - {label: Your name, bind: signer}
decision: {label: Sign off, action: sign-off}
```
