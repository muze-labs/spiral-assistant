# Example: Existing Project Adoption

This example shows how the assistant should approach an existing project that has not yet adopted Muze's spiral model.

It is intentionally generic. Replace it with real Muze examples once the workflow has been tested.

## Starting point

An existing library has a README, source code, some tests, and several planned features, but no explicit maturity model.

## Expected first assistant outputs

- current-state audit;
- risk register;
- boundary map;
- abstraction review;
- maturity estimate;
- first roadmap-driven cycle.

## Example risks

- roadmap has changed but docs still describe the old direction;
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
