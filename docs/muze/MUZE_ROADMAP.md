# Muze Roadmap

## Purpose

This roadmap describes where Spiral Assistant is going. It should drive spiral cycle planning.

The maturity model answers "ready enough?"
The roadmap answers "ready for what?"

## Current direction

Spiral Assistant should remain a document-first assistant until repeated project audits show that the workflow is useful, bounded, and understandable. The next improvements should come from test-run evidence, not from imagined completeness.

## Roadmap pressures

| Pressure | Source | Impact |
|---|---|---|
| Need repeatable project audits | Original assistant goal | Keep prompts and templates operational, not just explanatory. |
| Avoid process bloat | Muze model itself | Prefer simplification and acceptance checks over adding documents. |
| Audit scope matters | SimplyStore test-run | Existing-repo audits must record branch, worktree, and dependency scope. |
| Dependency scope matters | SimplyStore dependency discussion | Reviews need a conscious decision about related repositories. |
| Need proof from real use | Current self-audit | Commit project-specific Muze docs and evaluate their usefulness. |

## Capability cycles

| Cycle | Capability | Main question | Main risk | Expected evidence | Status |
|---|---|---|---|---|---|
| 0 | Self-audit | Can Spiral Assistant use its own workflow without becoming ceremonial? | The process looks complete but does not improve decisions | `docs/muze/` first-pass docs and acceptance-check evaluation | Completed |
| 1 | Repeatable external audit | Can a second repository audit produce similarly useful outputs? | The workflow worked only because the user guided it closely | Another repo audit with less steering and clear acceptance check | Planned |
| 2 | First example hardening | Can examples show real use without becoming too long? | Generic examples are too abstract for new users | One compact real or anonymized example | Proposed |
| 3 | Prompt simplification | Can prompts be shorter while preserving behavior? | Prompt set becomes repetitive and hard to maintain | Reduced duplication, same output quality on a test audit | Proposed |
| 4 | Tooling decision | Is there enough repetition to justify tooling? | Automation adds ceremony before the manual process is proven | Evidence log showing repeated manual friction | Deferred |

## Near-term cycle

### Capability

Cycle 1: Repeatable external audit.

### Why now?

The SimplyStore audit and this self-audit are useful, but both happened with close human guidance. The next risk is repeatability: can the repository itself guide a first pass on another project without adding more process?

### Explicit non-goals

1. Do not add new standard Muze documents.
2. Do not build an app, CLI, MCP server, or GitHub workflow.
3. Do not expand examples into a large manual.

### Risks to reduce

1. The workflow may be too dependent on the current assistant's judgment.
2. The first-pass document set may be too large for users to maintain.
3. The prompts may overlap enough to cause drift.

### Evidence needed

1. A second external repository audit that records audit scope and dependency scope.
2. A checklist evaluation showing which first-pass criteria were met or missed.
3. A short note identifying which docs were useful and which felt redundant.

### Pause or change conditions

1. If users or assistants produce broad feature plans instead of evidence-driven cycles, simplify prompts before more testing.
2. If eight docs feel too heavy, introduce a staged adoption rule rather than adding more templates.
3. If audit quality depends heavily on one assistant's unstated knowledge, improve examples before tooling.

## Later possibilities

1. A compact "audit packet" example for a real project.
2. A script that checks whether required Muze docs exist.
3. A GitHub PR review prompt that comments only on risks and maturity regressions.

## Out of scope

1. Full project-management tooling.
2. Automatic scoring without human review.
3. Semi-agentic repository changes before the document workflow is validated.

## Roadmap review log

| Date | Change | Reason | Impact |
|---|---|---|---|
| 2026-06-28 | Added self-audit roadmap | Test Spiral Assistant against its own process | Makes next cycle evidence-driven |
