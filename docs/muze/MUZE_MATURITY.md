# Muze Maturity Model

## Purpose

This document defines Spiral Assistant's quality metrics, maturity levels, and current maturity estimate.

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

| Metric | Why it matters for this project | Current score | Target next cycle |
|---|---|---:|---:|
| Feedback value | The assistant must produce useful project decisions, not just text. | 3 | 4 |
| Conceptual simplicity | Users must understand the model without a consulting background. | 3 | 4 |
| Workflow clarity | The first-run sequence must be easy to follow. | 3 | 4 |
| Boundary clarity | The repo must separate model docs, prompts, templates, catalogs, examples, and project output. | 3 | 3 |
| Evidence quality | Test-runs must prove the workflow reduces real uncertainty. | 2 | 3 |
| Human legibility | The repository must remain readable and maintainable by humans. | 4 | 4 |
| Bloat resistance | The assistant must resist adding prompts, templates, and process layers too early. | 3 | 4 |
| AI containment | The assistant must keep AI work bounded and reviewable. | 3 | 3 |

## Maturity levels

| Level | Name | Description |
|---|---|---|
| 1 | Usable instruction set | A user can point an AI assistant at the repo and get a useful first draft. |
| 2 | Repeatable audit workflow | Different repositories can be audited with consistent scope, evidence, risks, and next-cycle output. |
| 3 | Validated examples | Real examples show how to apply and evaluate the workflow. |
| 4 | Workflow-integrated assistant | The process can support PRs, issues, or CI without losing human ownership. |
| 5 | Mature assistant ecosystem | Tooling, docs, examples, and governance are stable and replaceable. |

## Quality targets by level

| Metric | L1 | L2 | L3 | L4 | L5 |
|---|---:|---:|---:|---:|---:|
| Feedback value | 3 | 4 | 4 | 4 | 5 |
| Conceptual simplicity | 3 | 4 | 4 | 4 | 5 |
| Workflow clarity | 3 | 4 | 4 | 5 | 5 |
| Boundary clarity | 2 | 3 | 4 | 4 | 5 |
| Evidence quality | 2 | 3 | 4 | 4 | 5 |
| Human legibility | 3 | 4 | 4 | 5 | 5 |
| Bloat resistance | 3 | 4 | 4 | 4 | 5 |
| AI containment | 2 | 3 | 4 | 4 | 5 |

## Current maturity estimate

Spiral Assistant is at Level 1 moving toward Level 2.

| Metric | Score | Evidence | Uncertainty |
|---|---:|---|---|
| Feedback value | 3 | SimplyStore test-run exposed two concrete documentation improvements. | Needs more than one external repo. |
| Conceptual simplicity | 3 | README and quickstart explain document-first assistant clearly. | Eight output docs may feel heavy. |
| Workflow clarity | 3 | Quickstart and workflow define first-run sequence and acceptance checks. | Repeatability across assistants not yet proven. |
| Boundary clarity | 3 | Repo separates docs, prompts, templates, catalogs, examples, and `docs/muze/`. | Some prompt and workflow content overlaps. |
| Evidence quality | 2 | Evidence comes from one external test-run plus this self-audit. | No external user validation yet. |
| Human legibility | 4 | Files are short Markdown documents with explicit purpose. | Could degrade if more prompts are added. |
| Bloat resistance | 3 | README warns against tooling before validation; self-audit prefers simplification. | The standard doc set may still be too large. |
| AI containment | 3 | `AGENTS.md` and AI-era docs define human review and unsafe areas. | No automated provenance or review boundary yet. |

## Spider graph data

| Metric | Current | Next target | L1 | L2 | L3 | L4 | L5 |
|---|---:|---:|---:|---:|---:|---:|---:|
| Feedback value | 3 | 4 | 3 | 4 | 4 | 4 | 5 |
| Conceptual simplicity | 3 | 4 | 3 | 4 | 4 | 4 | 5 |
| Workflow clarity | 3 | 4 | 3 | 4 | 4 | 5 | 5 |
| Boundary clarity | 3 | 3 | 2 | 3 | 4 | 4 | 5 |
| Evidence quality | 2 | 3 | 2 | 3 | 4 | 4 | 5 |
| Human legibility | 4 | 4 | 3 | 4 | 4 | 5 | 5 |
| Bloat resistance | 3 | 4 | 3 | 4 | 4 | 4 | 5 |
| AI containment | 3 | 3 | 2 | 3 | 4 | 4 | 5 |

## Non-regression checks

- [x] No previously achieved metric silently regressed.
- [x] Any accepted regression is documented as intentional debt.
- [x] Current cycle targets are tied to roadmap direction.
- [x] Evidence exists for each score.
