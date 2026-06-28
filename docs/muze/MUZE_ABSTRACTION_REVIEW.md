# Muze Abstraction Review

## Purpose

This document reviews whether Spiral Assistant's core abstractions simplify the system or create complexity.

Core question:

> Does this abstraction make everything built on top of it simpler?

## Core abstractions

| Abstraction | Purpose | What it simplifies | What depends on it | Current maturity |
|---|---|---|---|---|
| Frontend-first maturity-gated spiral | Core model for project decisions | Explains why different qualities matter at different stages | All docs, prompts, templates | Good enough for current use |
| Roadmap-driven cycle | Keeps cycles tied to direction, not generic maturity | Prevents feature lists from masquerading as progress | Roadmap, cycle log, prompts | Good enough for current use |
| Quality metric | Scores one aspect of project readiness | Turns vague quality concerns into discussable targets | Maturity template, catalogs | Basic but useful |
| Evidence pause | Allows roadmap halt when risks are unclear | Prevents continuing on bad assumptions | Risk register, cycle log | Good enough for current use |
| Boundary map | Makes conceptual and technical separations explicit | Exposes coupling and replaceability risk | Boundary template, workflow | Basic but useful |
| Abstraction review | Tests whether core concepts reduce complexity | Prevents hardening poor abstractions | Abstraction template, AGENTS.md | Basic but useful |
| Audit scope | Records branch, worktree, and dependency scope | Prevents reviewing the wrong project state | Quickstart, prompts, boundary map | Newly added, needs validation |

## Detailed review

### Abstraction: Standard Muze document set

#### Purpose

Provide a repeatable set of project-specific documents for applying the model.

#### What it simplifies

- Gives assistants concrete output targets.
- Separates roadmap, maturity, risk, boundaries, abstractions, cycle history, and AI usage.
- Makes uncertainty visible.

#### Warning signs

- [ ] Many special cases
- [ ] Repeated adapter code
- [ ] Forced naming
- [ ] Complex dependent code
- [ ] Difficult schemas
- [x] Heavy setup for simple cases
- [ ] Hard-to-replace dependencies

#### Good signs

- [x] Examples become shorter
- [x] Vocabulary becomes clearer
- [x] Boundaries stabilize
- [ ] Data structures feel natural
- [ ] Special cases disappear
- [x] Tests become easier

#### Alternatives considered

| Alternative | Why rejected or postponed |
|---|---|
| One single `MUZE.md` | Simpler to start, but may blur roadmap, risk, and maturity decisions. |
| Full tool-generated project packet | Premature before document workflow is validated. |
| Only prompts, no templates | Too easy for outputs to drift by assistant or project. |

#### Decision

- [ ] Keep provisional
- [x] Do not harden yet
- [ ] Test through prototype
- [ ] Rename
- [ ] Split
- [ ] Merge with another concept
- [ ] Harden
- [ ] Replace

#### Notes

The document set is useful but may be too heavy. The staged adoption rule is the key simplification: start with four documents, add the rest when context exists.

### Abstraction: Audit scope

#### Purpose

Prevent the assistant from judging the wrong repository state or silently ignoring related repositories.

#### What it simplifies

- Clarifies whether dirty worktree changes count.
- Makes branch/tag/commit evidence explicit.
- Turns dependency review into a conscious scope decision.

#### Warning signs

- [ ] Many special cases
- [ ] Repeated adapter code
- [ ] Forced naming
- [ ] Complex dependent code
- [ ] Difficult schemas
- [ ] Heavy setup for simple cases
- [ ] Hard-to-replace dependencies

#### Good signs

- [x] Examples become shorter
- [x] Vocabulary becomes clearer
- [x] Boundaries stabilize
- [x] Data structures feel natural
- [x] Special cases disappear
- [ ] Tests become easier

#### Decision

- [ ] Keep provisional
- [ ] Do not harden yet
- [ ] Test through prototype
- [ ] Rename
- [ ] Split
- [ ] Merge with another concept
- [x] Harden
- [ ] Replace

#### Notes

This abstraction came directly from the SimplyStore test-run and should remain part of existing-project audits.

## Abstraction tournament

| Candidate | Example size | Dependent code complexity | Boundary clarity | Vocabulary fit | Decision |
|---|---:|---|---|---|---|
| Eight-document project packet | Medium | Clear but potentially heavy | Strong | Good | Keep with staged adoption |
| Four-document starter packet | Small | Lower setup cost | Medium | Good | Use as first adoption default |
| Single `MUZE.md` | Small | Easy to start, easy to blur | Weak | Medium | Do not use yet |

## Hardening gate

Before building tooling around Spiral Assistant:

- [x] The abstraction has clear vocabulary.
- [x] Common cases are simple.
- [ ] Special cases are understood.
- [ ] Dependent code is simpler than alternatives.
- [x] Boundaries are clear.
- [ ] The team can explain why this is the right center after several external audits.

If any box is unchecked, prefer another test-run or simplification pass before tooling.
