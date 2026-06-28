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

### Step 1: Project intake

Goal: understand the project well enough to draft the first project documents.

Inputs:

- README;
- existing roadmap;
- project description;
- client or user feedback;
- repository files, if available;
- existing architecture notes.

Outputs:

- project brief;
- first roadmap;
- first risk register;
- assumptions and open questions.

### Step 2: Current-state audit

Goal: identify the current maturity level and the main risks.

The assistant should inspect:

- source tree;
- dependencies;
- tests;
- docs;
- package structure;
- open issues;
- current roadmap;
- examples;
- generated or AI-assisted code, if known.

Outputs:

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
- AI usage boundaries.

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
