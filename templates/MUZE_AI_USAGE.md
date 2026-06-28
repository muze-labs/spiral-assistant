# Muze AI Usage

## Purpose

This document defines how AI may be used in this project.

AI should help exploration, comparison, scaffolding, review, and simplification. It should not become an unsupervised source of architecture or security-sensitive code.

## AI usage stance

<!-- Describe how AI is currently used in this project. -->

## Allowed AI use

| Area | Allowed use | Review required |
|---|---|---|
| Documentation | Drafting, restructuring, examples | Human review |
| Tests | Drafting cases and scaffolding | Human review for evidence quality |
| Prototypes | Small bounded alternatives | Human review for abstraction and complexity |
| Refactoring | Suggested changes | Human review and tests |
| Benchmarks | Dataset and script generation | Human review of assumptions |

## Restricted AI use

| Area | Restriction | Reason |
|---|---|---|
| Security-sensitive code | No unsupervised changes | High risk |
| Access control | Human design required | Trust boundary risk |
| Persistence/recovery | Human design required | Data integrity risk |
| Migrations | Human design required | Irreversible data risk |
| Architecture | AI may propose, humans decide | Complexity and ownership risk |

## Generated-code provenance

| Area | AI-generated or assisted? | Review status | Notes |
|---|---|---|---|
| | | | |

## AI containment checks

- [ ] AI changes are small and bounded.
- [ ] AI-generated code has human-readable explanation.
- [ ] AI did not invent project vocabulary without review.
- [ ] AI did not add dependencies without justification.
- [ ] AI-generated tests validate real behavior, not just implementation.
- [ ] Security-sensitive AI output is treated as untrusted.
- [ ] Generated complexity is either removed or recorded as debt.

## Prompt and vocabulary alignment

| Term | Meaning | Used in docs | Used in code | Used in prompts | Notes |
|---|---|---|---|---|---|
| | | | | | |

## AI review log

| Date | AI use | Benefit | Risk | Follow-up |
|---|---|---|---|---|
| | | | | |
