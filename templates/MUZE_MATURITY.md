# Muze Maturity Model

## Purpose

This document defines the project's quality metrics, maturity levels, and minimum quality targets.

Not every quality metric must improve in every cycle, but quality should not silently regress.

## Scoring scale

| Score | Meaning |
|---|---|
| 1 | Rough, experimental, or provisional. |
| 2 | Basic, partially useful, known gaps. |
| 3 | Good enough for the current maturity level. |
| 4 | Reliable for broader use. |
| 5 | Mature, strong, reusable, or production-ready. |

## Selected quality metrics

Choose the smallest useful set.

| Metric | Why it matters for this project | Current score | Target next cycle |
|---|---|---:|---:|
| Usability | | | |
| Feedback value | | | |
| Conceptual simplicity | | | |
| Abstraction fitness | | | |
| Boundary clarity | | | |
| Data integrity | | | |
| Maintainability | | | |
| Security containment | | | |
| Human legibility | | | |

## Maturity levels

| Level | Name | Description |
|---|---|---|
| 1 | Usable concept | People can try the core idea and give meaningful feedback. |
| 2 | Abstraction validated | Core concepts reduce complexity and dependent code is simpler. |
| 3 | Structured implementation | Data, commands, boundaries, and tests are reliable enough to build on. |
| 4 | Reliable product | Security, maintainability, performance, and operations are good enough for broader use. |
| 5 | Mature ecosystem | Documentation, extension points, governance, and replacement paths are clear. |

## Quality targets by level

| Metric | L1 | L2 | L3 | L4 | L5 |
|---|---:|---:|---:|---:|---:|
| Usability | 3 | 4 | 4 | 4 | 4 |
| Feedback value | 3 | 4 | 4 | 4 | 4 |
| Conceptual simplicity | 2 | 4 | 4 | 4 | 5 |
| Abstraction fitness | 1 | 4 | 4 | 4 | 5 |
| Boundary clarity | 1 | 3 | 4 | 4 | 5 |
| Data integrity | 1 | 2 | 4 | 4 | 5 |
| Maintainability | 1 | 2 | 3 | 4 | 5 |
| Security containment | 1 | 1 | 2 | 4 | 5 |
| Human legibility | 2 | 3 | 4 | 4 | 5 |

## Current maturity estimate

| Metric | Score | Evidence | Uncertainty |
|---|---:|---|---|
| | | | |

## Spider graph data

Use this table to generate a spider/radar graph if useful.

| Metric | Current | Next target | L1 | L2 | L3 | L4 | L5 |
|---|---:|---:|---:|---:|---:|---:|---:|
| Usability | | | 3 | 4 | 4 | 4 | 4 |
| Feedback value | | | 3 | 4 | 4 | 4 | 4 |
| Conceptual simplicity | | | 2 | 4 | 4 | 4 | 5 |
| Abstraction fitness | | | 1 | 4 | 4 | 4 | 5 |
| Boundary clarity | | | 1 | 3 | 4 | 4 | 5 |
| Data integrity | | | 1 | 2 | 4 | 4 | 5 |
| Maintainability | | | 1 | 2 | 3 | 4 | 5 |
| Security containment | | | 1 | 1 | 2 | 4 | 5 |
| Human legibility | | | 2 | 3 | 4 | 4 | 5 |

## Non-regression checks

- [ ] No previously achieved metric silently regressed.
- [ ] Any accepted regression is documented as intentional debt.
- [ ] Current cycle targets are tied to roadmap direction.
- [ ] Evidence exists for each score.
