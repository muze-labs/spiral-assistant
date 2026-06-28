# Quickstart

This repository is a document-first minimum viable assistant. Use it to make Muze's spiral model repeatable before building custom tooling.

The first useful outcome is not a full plan. The first useful outcome is a small set of project-specific documents that make direction, maturity, risks, boundaries, and the next evidence-producing cycle explicit.

## When To Use It

Use Spiral Assistant when:

- starting a new software project;
- adopting Muze's model in an existing project;
- reviewing whether a project is ready for the next maturity level;
- deciding whether a new risk should pause the roadmap;
- checking whether AI-assisted work has made the project harder to understand.

Do not use it to justify adding features merely because they are easy to generate.

## Minimum Inputs

For a new project, provide as many of these as possible:

- project idea or short description;
- intended users;
- current roadmap pressure;
- constraints, deadlines, or client feedback;
- known risks;
- any prototype, screenshots, or demo notes.

For an existing project, provide:

- repository access or a source snapshot;
- intended branch, tag, or commit;
- README and roadmap;
- current issues or client feedback;
- test and build status if known;
- any existing architecture notes;
- related repositories or important internal dependencies;
- known AI-generated or AI-assisted work.

Missing information is allowed. The assistant should draft with assumptions rather than block on perfect input.

## Existing-Repository Audit Scope

Before reviewing an existing repository, record the audit scope:

- repository path or URL;
- branch, tag, or commit;
- whether the worktree is clean;
- whether untracked or experimental files are included;
- which related repositories or internal dependencies are in scope;
- which dependencies are intentionally treated as black boxes.

Ask the user before pulling related repositories into the review. Many projects depend on internal libraries that carry their own roadmap, maturity, risks, and abstractions. Including them can improve evidence, but it also increases review cost and can blur the current cycle.

Use three scope levels:

| Scope | Meaning |
|---|---|
| Primary repository | Always inspect. This is the project being reviewed. |
| In-scope related repository | Inspect because it affects the current roadmap, abstraction, or risk. |
| Out-of-scope dependency | Treat as an external assumption. Record the risk if that assumption matters. |

If the worktree is dirty, do not assume the current files represent the stable project state. Ask whether to review the dirty state, a clean branch, or both.

## First-Run Sequence

1. Read `AGENTS.md`.
2. Read this quickstart.
3. Read `docs/01-model-overview.md`.
4. Read `docs/04-assistant-workflow.md`.
5. Use the relevant prompt from `prompts/`.
6. Draft the project-specific Muze documents.
7. End with the proposed next cycle and the evidence it must produce.

For most projects, start with:

- `prompts/intake-prompt.md` for a new project;
- `prompts/current-state-audit-prompt.md` for an existing project;
- `prompts/roadmap-cycle-planning-prompt.md` when the project already has Muze documents.

## First Documents To Create

Create these first:

- `MUZE_PROJECT_BRIEF.md`
- `MUZE_ROADMAP.md`
- `MUZE_RISK_REGISTER.md`
- `MUZE_MATURITY.md`

Then create these when there is enough context:

- `MUZE_BOUNDARY_MAP.md`
- `MUZE_ABSTRACTION_REVIEW.md`
- `MUZE_CYCLE_LOG.md`
- `MUZE_AI_USAGE.md`

The boundary and abstraction documents can be rough at first. They are meant to expose uncertainty, not hide it.

## What A Good First Pass Contains

A good first pass includes:

- a short project hypothesis;
- audit scope, branch, and worktree state for existing repositories;
- facts separated from assumptions;
- the current roadmap direction;
- the main roadmap pressures;
- the smallest useful quality metric set;
- a maturity estimate with evidence and uncertainty;
- the top risks, including complexity risk;
- unclear abstractions or boundaries;
- one recommended next cycle;
- explicit non-goals for that cycle;
- evidence that would prove the cycle worked;
- conditions that would pause or change the roadmap.

If the assistant produces a broad feature list without risk, maturity, evidence, or non-goals, the pass is not good enough.

## Cycle Size Rule

A cycle should be small enough to answer one main question.

Good cycle shape:

> Validate whether the target user can complete the core workflow with a minimal usable interface, without hardening storage or permissions yet.

Weak cycle shape:

> Build the product.

Each cycle should name:

- the roadmap capability being validated;
- the risk being reduced;
- the maturity metrics that must improve;
- the metrics that must not regress;
- the evidence required;
- the debt accepted;
- the decision to make at the end.

## Stop Conditions

Pause normal roadmap progress when:

- a core abstraction creates many special cases;
- user feedback contradicts the roadmap;
- a security, data, or persistence assumption is wrong;
- performance fails earlier than expected;
- AI-generated code cannot be explained or reviewed;
- hardening the current design would lock in a weak boundary.

The next step should then be an evidence-based risk assessment: research, proof of concept, benchmark, prototype comparison, review, or code deletion.

## Project Directory

When adopting the model inside a project, place project-specific files here:

```text
docs/muze/
  MUZE_PROJECT_BRIEF.md
  MUZE_ROADMAP.md
  MUZE_MATURITY.md
  MUZE_RISK_REGISTER.md
  MUZE_BOUNDARY_MAP.md
  MUZE_ABSTRACTION_REVIEW.md
  MUZE_CYCLE_LOG.md
  MUZE_AI_USAGE.md
```

Keep these documents short enough that people actually read and update them.
