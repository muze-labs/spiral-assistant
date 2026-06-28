# Muze AI Usage

## Purpose

This document records how AI should and should not be used in Spiral Assistant.

AI is part of the product surface: the repository is meant to be read and applied by AI assistants. That makes AI usage central to the risk model.

## AI use policy

| Area | AI usage | Human responsibility |
|---|---|---|
| Drafting project Muze docs | Allowed and expected | Review assumptions, scores, risks, and roadmap decisions |
| Summarizing project context | Allowed | Check against source files |
| Risk identification | Allowed | Decide priority and ownership |
| Maturity scoring | Allowed as proposal | Accept, reject, or revise scores |
| Architecture decisions | AI may compare options | Humans own final decisions |
| Security-sensitive guidance | AI may flag risks | Human expert review required |
| Tooling implementation | Defer for now | Only after document workflow is validated |

## Current AI-assisted work

| Artifact | AI role | Review status |
|---|---|---|
| Repository skeleton | AI-assisted draft | Needs ongoing human review |
| Quickstart/workflow refinements | AI-assisted from SimplyStore test-run | Reviewed in conversation, should be reviewed before release |
| `docs/muze/` self-audit docs | AI-drafted | Pending human review |

## AI risks

| Risk | Why it matters | Mitigation |
|---|---|---|
| Output volume replaces understanding | The assistant can generate many docs quickly. | Keep first-pass docs concise; require evidence and non-goals. |
| Vocabulary drift | AI may invent terms that blur Muze concepts. | Use catalogs and templates; review terminology. |
| False maturity | AI may make a prototype look complete. | Require maturity scores and evidence quality. |
| Prompt overfitting | Docs may work only for one assistant. | Test with another assistant or less guided prompt. |
| Process bloat | AI can easily add more templates and prompts. | Do not add framework artifacts without evidence from a cycle. |

## Safe uses

- Drafting first-pass project documents.
- Producing alternative cycle plans.
- Generating risk lists from catalogs.
- Comparing abstraction candidates.
- Drafting tests or checklists after a risk is named.
- Summarizing cycle evaluations.

## Cautious uses

- Security advice.
- Architecture hardening.
- Permission and access-control design.
- Persistence or recovery recommendations.
- Broad rewrites of the assistant framework.

## Prohibited without explicit human approval

- Adding new standard Muze documents.
- Building workflow automation.
- Treating AI-generated scores as accepted maturity.
- Publishing the AI-era update as validated research.

## Review checklist

- [ ] Did AI separate facts from assumptions?
- [ ] Did AI identify evidence, not just recommendations?
- [ ] Did AI add concepts that need naming review?
- [ ] Did AI keep the next cycle bounded?
- [ ] Did AI reduce complexity or increase output?
