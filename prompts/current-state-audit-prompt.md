# Current-State Audit Prompt

Use this prompt when applying the model to an existing project.

```text
Use the Spiral Assistant repository as background.

Review the current project state and help us adopt Muze's spiral model.

Inspect the available README, roadmap, docs, source tree, tests, dependencies, and issues if available.

Before judging the project, record:

- repository path or URL;
- branch, tag, or commit;
- worktree cleanliness;
- whether dirty or untracked files are included;
- related repositories or internal dependencies;
- which related repositories are in scope for this audit.

Produce:

1. audit scope;
2. a current-state summary;
3. an initial maturity estimate;
4. a risk register;
5. a boundary map;
6. an abstraction review;
7. a recommendation for the first roadmap-driven spiral cycle.
8. explicit evidence and pause conditions for that cycle.

Pay special attention to:

- complexity creep;
- unclear conceptual boundaries;
- technical boundaries that do not match concepts;
- leaky abstractions;
- dependency lock-in;
- dependency scope and replaceability;
- prototype debt;
- AI-generated code or AI-era risks;
- missing evidence.

Separate facts from assumptions. Mark uncertainty clearly.

Do not start by suggesting features. Start by identifying the most important risks and evidence needed.

If the roadmap is missing or outdated, recommend Cycle 0: Roadmap Calibration before proposing implementation work.
```
