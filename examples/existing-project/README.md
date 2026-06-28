# Example: Existing Project Adoption

This example shows how the assistant should approach an existing project that has not yet adopted Muze's spiral model.

It is intentionally generic. Replace it with real Muze examples once the workflow has been tested.

## Starting point

An existing library has a README, source code, some tests, and several planned features, but no explicit maturity model.

## Expected first assistant outputs

- audit scope, including branch/worktree state;
- dependency scope decision for related repositories;
- current-state audit;
- `MUZE_RISK_REGISTER.md`;
- `MUZE_BOUNDARY_MAP.md`;
- `MUZE_ABSTRACTION_REVIEW.md`;
- `MUZE_MATURITY.md`;
- first roadmap-driven cycle.

## Example risks

- roadmap has changed but docs still describe the old direction;
- the reviewed branch contains experimental changes that are mistaken for stable direction;
- important internal dependencies are treated as stable black boxes without a conscious decision;
- package boundaries follow file history rather than concepts;
- examples require too much setup;
- a common abstraction causes special cases;
- AI-generated code added wrappers that are not needed.

## Example first cycle

Cycle: Abstraction validation

Main risk:

> The current abstraction may be creating complexity in dependent code.

Evidence:

- two or three examples rewritten using the current abstraction;
- one alternative abstraction prototype;
- comparison of dependent code length and clarity;
- vocabulary review;
- decision whether to keep, rename, split, or replace the abstraction.

Pause conditions:

- the alternative prototype is simpler in common cases;
- dependent code needs repeated adapters;
- the current abstraction cannot be explained without implementation details.
