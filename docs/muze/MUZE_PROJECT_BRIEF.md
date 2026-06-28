# Muze Project Brief

## Project name

Spiral Assistant

## Audit scope

| Field | Value |
|---|---|
| Repository | `/home/auke/git/muze-labs/spiral-assistant` |
| Branch | `main` |
| Worktree | Clean at audit time |
| Dirty/untracked files included | No |
| Related repositories in scope | None |
| Dependencies treated as black boxes | ChatGPT, GitHub Copilot Chat, Claude, local coding agents, and similar assistant surfaces |

## Summary

Spiral Assistant is a document-first framework for applying Muze's frontend-first, maturity-gated spiral model to new and existing software projects.

It is not an application yet. Its current form is a set of model documents, templates, catalogs, prompts, and examples that an AI assistant can read and use to produce project-specific Muze documents.

## Product hypothesis

> A repository of concise instructions, prompts, catalogs, and templates can make Muze's spiral model repeatable enough for AI-assisted first-pass project audits, without requiring custom tooling yet.

## Facts and assumptions

### Facts

1. The repository contains `AGENTS.md`, model docs, catalogs, prompts, templates, and examples.
2. The quickstart defines what a good first pass should contain.
3. The workflow now requires audit scope, branch/worktree state, dependency scope, maturity evidence, risks, boundaries, and a next cycle.
4. The SimplyStore test-run produced immediate improvements to the assistant docs.
5. There is no application, automated validation, or real project-specific example output committed yet.

### Assumptions

| Assumption | Why we believe it | What could disprove it |
|---|---|---|
| A document-first assistant is enough for the current maturity level. | The SimplyStore test-run was useful without tooling. | Repeated test-runs fail because assistants miss context, drift, or produce unusable docs. |
| The standard Muze document set is small enough to maintain. | Eight documents cover direction, roadmap, maturity, risk, boundaries, abstractions, cycle log, and AI usage. | Users avoid updating them, or first-pass reviews become ceremonial. |
| Prompts can guide different AI assistants consistently. | The instructions are explicit and repository-local. | Different assistants produce incompatible or overly broad outputs from the same project. |
| More tooling should wait. | The README explicitly says not to add automation until the document workflow proves useful. | Manual use becomes repetitive enough that tooling clearly reduces complexity rather than adding it. |

## Intended users

- Muze maintainers applying the spiral model to internal projects.
- AI assistants that can read repository context.
- Project teams adopting Muze's model in an existing repository.
- Future reviewers deciding whether a project should continue, pause, simplify, or gather evidence.

## Main use cases

1. Start a new project with a first project brief, roadmap, maturity model, and risk register.
2. Audit an existing project and identify the next roadmap-driven cycle.
3. Evaluate a completed cycle and decide whether to continue, adjust, pause, or simplify.

## Non-goals

1. No custom application or hosted service yet.
2. No automated GitHub workflow or PR reviewer yet.
3. No attempt to replace human product or architecture ownership.
4. No exhaustive methodology manual.

## Current state

- [ ] Idea
- [x] Usable prototype
- [x] Internal tool
- [ ] Public library
- [ ] Production system
- [x] Other: document-first assistant framework

## Current roadmap pressure

The main pressure is to prove that the assistant works on real repositories without expanding into a heavy process. The SimplyStore test-run showed value, but also exposed missing audit-scope and dependency-scope guidance. The next pressure is to validate repeatability and resist adding templates before evidence shows they are needed.

## Main open questions

1. Can another assistant use this repository and produce similarly bounded first-pass outputs?
2. Are eight project-specific Muze documents too many for first adoption?
3. Which parts should remain prompts/docs, and which parts eventually deserve tooling?
4. What is the smallest real example that would prove the workflow to a new user?

## Links

- Repository: `/home/auke/git/muze-labs/spiral-assistant`
- Core instructions: `AGENTS.md`
- Quickstart: `docs/00-quickstart.md`
- Workflow: `docs/04-assistant-workflow.md`
