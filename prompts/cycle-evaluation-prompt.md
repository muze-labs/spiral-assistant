# Cycle Evaluation Prompt

Use this prompt at the end of a cycle.

```text
Use the Spiral Assistant repository as background.

Evaluate this completed cycle using Analyze–Plan–Act–Evaluate.

Inputs:
- original cycle plan;
- work performed;
- artifacts produced;
- tests, demos, feedback, or benchmark results;
- current risk register;
- current maturity matrix.

Evaluate:

1. Did the cycle reduce the intended risk?
2. Did it produce the expected evidence?
3. Which maturity targets were met?
4. Did any quality metric regress?
5. Did complexity increase or decrease?
6. Did the abstraction simplify dependent code?
7. Did any boundary become clearer or blurrier?
8. Did AI introduce bloat, vocabulary drift, or review burden?
9. Were new risks discovered?
10. Should the roadmap continue, change, or pause for evidence?
11. Is a stakeholder note needed to explain the result outside the implementation team?

Update or draft:

- MUZE_CYCLE_LOG.md entry;
- maturity score changes;
- risk register changes;
- abstraction review changes;
- optional stakeholder note for MUZE_CYCLE_LOG.md;
- recommended next cycle.

Be explicit about uncertainty.
```
