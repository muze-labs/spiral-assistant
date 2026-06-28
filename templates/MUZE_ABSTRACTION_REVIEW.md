# Muze Abstraction Review

## Purpose

This document reviews whether the project's core abstractions simplify the system or create complexity.

Core question:

> Does this abstraction make everything built on top of it simpler?

## Core abstractions

| Abstraction | Purpose | What it simplifies | What depends on it | Current maturity |
|---|---|---|---|---|
| | | | | |

## Detailed review

### Abstraction: <!-- name -->

#### Purpose

<!-- What is this abstraction for? -->

#### What it simplifies

<!-- What becomes easier because this abstraction exists? -->

#### Warning signs

- [ ] Many special cases
- [ ] Repeated adapter code
- [ ] Forced naming
- [ ] Complex dependent code
- [ ] Difficult schemas
- [ ] Heavy setup for simple cases
- [ ] Hard-to-replace dependencies

#### Good signs

- [ ] Examples become shorter
- [ ] Vocabulary becomes clearer
- [ ] Boundaries stabilize
- [ ] Data structures feel natural
- [ ] Special cases disappear
- [ ] Tests become easier

#### Alternatives considered

| Alternative | Why rejected or postponed |
|---|---|
| | |

#### Decision

- [ ] Keep provisional
- [ ] Do not harden yet
- [ ] Test through prototype
- [ ] Rename
- [ ] Split
- [ ] Merge with another concept
- [ ] Harden
- [ ] Replace

#### Notes

<!-- Add reasoning here. -->

## Abstraction tournament

Use this when AI or quick prototyping makes it cheap to compare alternatives.

| Candidate | Example size | Dependent code complexity | Boundary clarity | Vocabulary fit | Decision |
|---|---:|---|---|---|---|
| | | | | | |

## Hardening gate

Before building schemas, storage, APIs, or infrastructure around an abstraction:

- [ ] The abstraction has clear vocabulary.
- [ ] Common cases are simple.
- [ ] Special cases are understood.
- [ ] Dependent code is simpler than alternatives.
- [ ] Boundaries are clear.
- [ ] The team can explain why this is the right center.

If any box is unchecked, document the missing evidence and prefer a smaller prototype, comparison, or simplification pass before hardening.
