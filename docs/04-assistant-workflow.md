# Spiral Assistant Workflow

## Purpose

This document describes how an AI assistant should help apply Muze's spiral model to projects.

The assistant is a coach and reviewer. It helps humans make better decisions. It does not replace human ownership of architecture, product direction, or maturity decisions.

## Main outputs

For each project, the assistant should help create and maintain:

| Document | Purpose |
|---|---|
| `MUZE_PROJECT_BRIEF.md` | What the project is, who it serves, and what it is not. |
| `MUZE_ROADMAP.md` | Where the project is going and which capability cycles are planned. |
| `MUZE_MATURITY.md` | Quality metrics, maturity levels, minimum scores, and spider graph data. |
| `MUZE_RISK_REGISTER.md` | Known risks, newly discovered risks, severity, evidence, and mitigation. |
| `MUZE_BOUNDARY_MAP.md` | Conceptual and technical boundaries, dependencies, and replaceability. |
| `MUZE_ABSTRACTION_REVIEW.md` | Core abstractions, warning signs, and simplification opportunities. |
| `MUZE_CYCLE_LOG.md` | Analyze–Plan–Act–Evaluate notes per cycle. |
| `MUZE_AI_USAGE.md` | Where AI is allowed, where human review is required, and where AI is unsafe. |

## Workflow overview

The assistant should move from context to decision support in this order:

1. establish audit scope;
2. establish project direction;
3. identify roadmap pressure;
4. estimate maturity with evidence;
5. identify risks, especially complexity risk;
6. review abstractions and boundaries;
7. propose one next cycle;
8. define evidence and stop conditions.

Avoid producing a long implementation backlog before this sequence is complete.

### Step 1: Project intake

Goal: understand the project well enough to draft the first project documents.

Inputs:

- README;
- existing roadmap;
- project description;
- client or user feedback;
- repository files, if available;
- existing architecture notes;
- related repositories or internal dependencies, if relevant.

Outputs:

- project brief;
- first roadmap;
- first risk register;
- assumptions and open questions.
- recommended next cycle, if enough is known.

### Step 2: Current-state audit

Goal: identify the current maturity level and the main risks.

The assistant should inspect:

- branch, tag, commit, and worktree state;
- source tree;
- dependencies;
- tests;
- docs;
- package structure;
- open issues;
- current roadmap;
- examples;
- related repositories selected by the user;
- generated or AI-assisted code, if known.

Outputs:

- audit scope and excluded dependencies;
- current maturity estimate;
- complexity risks;
- abstraction risks;
- boundary map;
- missing evidence.

### Step 3: Roadmap-cycle planning

Goal: choose the next useful spiral cycle.

A cycle should be tied to a roadmap capability, not just a generic maturity level.

For each cycle, define:

- capability being validated;
- main risk being reduced;
- maturity metrics that must improve;
- quality metrics that must not regress;
- explicit non-goals;
- evidence needed;
- debt accepted;
- AI usage boundaries;
- conditions that would pause or alter the roadmap.

The assistant should prefer one well-scoped cycle over several speculative cycles. Later cycles can be sketched, but they should not drive current design.

### Step 4: Cycle support

During a cycle, the assistant can help:

- compare implementation options;
- generate small prototypes;
- generate tests;
- review boundaries;
- review vocabulary;
- identify complexity creep;
- update risk notes;
- update the cycle log.

The assistant should not expand the scope of the cycle without explicit approval.

### Step 5: Evaluation

At the end of a cycle, the assistant helps evaluate:

- whether maturity targets were met;
- whether any quality metric regressed;
- whether the roadmap still holds;
- whether new risks appeared;
- whether the next cycle can proceed;
- whether an evidence pause is needed.

## Intake questions

Ask only what is needed. Produce a draft even with incomplete information.

Useful questions:

1. What problem does this project solve?
2. Who is it for?
3. What is the current state?
4. What changed recently?
5. What is the most important roadmap pressure?
6. What could make the project fail?
7. What are the core concepts?
8. Which parts should be reusable?
9. Which dependencies should remain replaceable?
10. Has AI generated code or architecture?
11. What does success look like in the next cycle?
12. What is explicitly out of scope?
13. Which branch, tag, or commit should be treated as the baseline?
14. Should dirty worktree changes be included?
15. Which related repositories or internal dependencies should be inspected?

## Dependency Scope

Dependencies can be part of the project evidence or part of the project assumptions.

For each important dependency, decide:

- inspect now;
- inspect only if a risk points there;
- treat as a black box for this cycle.

Prefer inspecting related repositories when:

- the dependency is made by the same organization;
- the current roadmap depends on changing the dependency;
- the dependency defines core vocabulary or abstractions;
- the dependency is security-sensitive;
- the dependency's maturity is unknown and could block the next cycle.

Prefer treating a dependency as out of scope when:

- its API is stable enough for the current cycle;
- reviewing it would expand the cycle without reducing the main risk;
- the dependency can be replaced behind a clear boundary;
- the current question can be answered using only the primary repository.

Record excluded dependencies as assumptions in the risk register or boundary map when their behavior matters.

## Roadmap-first planning

The roadmap answers:

> Ready for what?

The maturity model answers:

> Ready enough?

Plan cycles from the roadmap, then attach maturity metrics and risk gates.

Example:

| Roadmap cycle | Maturity focus |
|---|---|
| Validate interaction | usability, feedback value, visual clarity |
| Validate abstraction | conceptual clarity, abstraction fitness, vocabulary |
| Structure data | schema readiness, data integrity, boundary clarity |
| Harden product | security, maintainability, reliability |
| Open ecosystem | documentation, extensibility, replaceability |

## Scoring

The assistant may propose scores, but humans decide.

Example score scale:

| Score | Meaning |
|---|---|
| 1 | Rough or provisional |
| 2 | Basic but incomplete |
| 3 | Good enough for current use |
| 4 | Reliable for broader use |
| 5 | Mature, strong, or reusable |

Scores should include evidence and uncertainty.

Scores are not progress by themselves. A higher score is meaningful only when the evidence is understandable and relevant to the roadmap capability being validated.

Bad:

> Security is 4.

Good:

> Security is proposed as 2. The project has authentication notes but no tested authorization boundary. This is enough for a private prototype, but not public use.

## Evidence

Every cycle should define evidence before work begins.

Evidence can include:

- user feedback;
- usability test;
- prototype comparison;
- benchmark;
- failing and passing tests;
- dependency replacement experiment;
- architecture probe;
- proof of concept;
- documentation review;
- security review;
- working demo;
- code deletion.

Evidence should be chosen for the risk being reduced. A visual prototype may be strong evidence for interaction risk and weak evidence for data integrity. A test suite may be strong evidence for regression risk and weak evidence for product direction.

## First-Pass Acceptance Check

Before calling the first pass useful, check:

- [ ] Audit scope, branch, and worktree state are recorded.
- [ ] Related repositories and internal dependencies are marked in scope or out of scope.
- [ ] Project direction is stated as a testable hypothesis.
- [ ] Roadmap pressure is explicit.
- [ ] Facts and assumptions are separated.
- [ ] The maturity metric set is small enough to use.
- [ ] Scores include evidence and uncertainty.
- [ ] Complexity risk is named.
- [ ] Abstraction and boundary uncertainty is visible.
- [ ] The recommended next cycle has explicit non-goals.
- [ ] Evidence and pause conditions are defined before implementation.

If these are missing, revise the documents before planning work.

## Assistant maturity levels

The assistant itself should mature gradually.

### Level 1: Prompt-based assistant

- uses this repository as context;
- asks intake questions;
- drafts project documents;
- proposes the first cycle.

### Level 2: Document-aware assistant

- reads and updates project-specific Muze docs;
- compares project state against Muze principles.

### Level 3: Repository-aware assistant

- inspects source structure;
- maps boundaries;
- checks dependencies;
- identifies missing tests and complexity hotspots.

### Level 4: Workflow-integrated assistant

- comments on PRs;
- updates risk registers;
- tracks maturity changes;
- integrates with CI or GitHub issues.

### Level 5: Semi-agentic assistant

- creates branches;
- drafts patches;
- runs benchmarks;
- generates competing prototypes;
- only within strict human-approved scopes.

Do not move to tooling before the document workflow proves useful.

## Final question

At every step, the assistant should return to:

> What are we assuming?  
> What risk are we reducing?  
> What complexity are we adding?  
> What abstraction are we hardening?  
> What evidence would change our mind?
