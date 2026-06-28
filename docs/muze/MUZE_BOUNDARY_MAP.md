# Muze Boundary Map

## Purpose

This document describes Spiral Assistant's conceptual and technical boundaries.

A boundary is useful when it makes change easier. A boundary is harmful when it adds ceremony without reducing coupling.

Core question:

> What decision does this boundary protect us from changing later?

## Conceptual boundaries

| Concept | Responsibility | Related concepts | Confusions or overlaps |
|---|---|---|---|
| Model docs | Explain Muze's development model and principles. | Catalogs, prompts | Can drift into a long methodology manual. |
| Quickstart | Tell users how to run a first pass. | Workflow, prompts | Can duplicate workflow details. |
| Workflow | Describe assistant operating sequence and acceptance checks. | Quickstart, prompts | Can become too process-heavy. |
| Prompts | Give copyable task instructions to assistants. | Workflow, templates | Can duplicate docs or become model-specific. |
| Templates | Provide project-specific output structure. | Prompts, examples | Can encourage completion theater if too many are required at once. |
| Catalogs | Provide reusable risk, metric, boundary, and abstraction options. | Templates | Can be copied blindly instead of selected. |
| Examples | Show expected use. | Templates, prompts | Currently generic; may not prove real-world usefulness. |
| Project-specific Muze docs | Record application of the model to a project. | Templates | Must stay shorter than the project work they support. |

## Technical boundaries

| Boundary | Responsibility | Depends on | Must not depend on | Change protected | Current risk |
|---|---|---|---|---|---|
| Repository-as-context | Make the assistant usable by any AI that can read files. | Markdown files | Specific assistant APIs or tools | Changing assistant surface | Low |
| Templates | Shape project-specific output. | Model vocabulary | A specific project | Changing project domain | Medium |
| Prompts | Trigger common assistant workflows. | AGENTS.md, docs, templates | Hidden assistant memory | Changing AI provider | Medium |
| Catalogs | Offer reusable options. | Muze model | Project-specific decisions | Changing project type | Low |
| `docs/muze/` | Store this project's own Muze adoption docs. | Templates | Generic template changes | Reviewing Spiral Assistant itself | Low |

## Dependency boundaries

| Dependency | Used for | Scope | Wrapped by | Replaceability risk | Notes |
|---|---|---|---|---|---|
| ChatGPT / Codex | Current drafting and audit run | Out of scope | Markdown instructions | Medium | The repo should remain assistant-agnostic. |
| GitHub Copilot Chat / Claude / local agents | Intended assistant surfaces | Out of scope | Markdown instructions | Medium | Cross-assistant validation is future evidence. |
| Git | Branch/worktree audit context | Out of scope | User/assistant commands | Low | Not a runtime dependency. |

## Related repositories

| Repository | Relationship | Review scope | Reason | Risk if excluded |
|---|---|---|---|---|
| SimplyStore | First external test-run | Deferred | Useful as evidence for assistant workflow, not part of this self-audit. | Lessons may not be reflected in examples. |

## Thin application layer check

- [x] Reusable model content is separate from project-specific Muze docs.
- [x] Product-specific composition is visible in `docs/muze/`.
- [x] Templates do not depend on a specific project.
- [x] Prompts can be copied without requiring tooling.
- [ ] Examples are still generic and not yet proven as teaching artifacts.
- [x] External assistant dependencies are behind plain Markdown instructions.

## Boundary risks

| Risk | Evidence | Mitigation |
|---|---|---|
| Quickstart, workflow, and prompts duplicate each other. | All three describe first-pass behavior. | Keep quickstart user-facing, workflow behavioral, prompts task-specific. Simplify if drift appears. |
| Templates create ceremony. | Eight standard outputs exist. | Use staged adoption: start with four, add the rest when useful. |
| Examples are too thin. | Existing examples are generic. | Add one real compact example only after another audit confirms the need. |

## Boundary changes

| Date | Change | Reason | Impact |
|---|---|---|---|
| 2026-06-28 | Added `docs/muze/` | Self-audit Spiral Assistant | Separates project-specific evidence from reusable framework files |
