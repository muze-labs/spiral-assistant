# Current-State Audit Prompt

Use this prompt when applying the model to an existing project.

```text
Use the Spiral Assistant repository as background.

Review the current project state and help us adopt Muze's spiral model.

Inspect the available README, roadmap, docs, source tree, tests, dependencies, and issues if available.

Produce:

1. a current-state summary;
2. an initial maturity estimate;
3. a risk register;
4. a boundary map;
5. an abstraction review;
6. a recommendation for the first roadmap-driven spiral cycle.
7. explicit evidence and pause conditions for that cycle.

Pay special attention to:

- complexity creep;
- unclear conceptual boundaries;
- technical boundaries that do not match concepts;
- leaky abstractions;
- dependency lock-in;
- prototype debt;
- AI-generated code or AI-era risks;
- missing evidence.

Separate facts from assumptions. Mark uncertainty clearly.

Do not start by suggesting features. Start by identifying the most important risks and evidence needed.

If the roadmap is missing or outdated, recommend Cycle 0: Roadmap Calibration before proposing implementation work.
```
