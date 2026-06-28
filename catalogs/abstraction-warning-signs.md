# Abstraction Warning Signs

Use this catalog during abstraction reviews.

## Core question

> Does this abstraction make everything built on top of it simpler?

## Warning signs

### Special-case growth

The abstraction needs more and more rules to handle normal cases.

Ask:

- Are these exceptions truly exceptional?
- Are they symptoms of a wrong center?
- Would a different concept remove them?

### Adapter repetition

Many parts of the system translate between the same concepts.

Ask:

- Are boundaries misplaced?
- Is the adapter hiding a mismatch?
- Should the shared model change?

### Forced naming

The names feel unnatural or keep changing.

Ask:

- Is the concept real?
- Are we using a technical word for a domain idea?
- Are two concepts being merged incorrectly?

### Complex dependent code

Using the abstraction requires more code than solving the case directly.

Ask:

- Is the abstraction too general?
- Does it push complexity upward?
- Are simple cases simple?

### Schema friction

Schemas or data structures need many exceptions.

Ask:

- Is the schema centered on the right concept?
- Are we hardening too early?
- Are we modeling storage instead of meaning?

### Setup burden

A simple use case requires too much configuration or ceremony.

Ask:

- Can defaults carry the common case?
- Is the abstraction too indirect?
- Is this really a framework?

### Hard-to-replace dependency

The abstraction is inseparable from a library, framework, or platform.

Ask:

- Is the dependency leaking into core concepts?
- Can it be hidden behind an adapter?
- Should the boundary move?

## Positive signs

### Examples get shorter

Beginner-facing examples become smaller and clearer.

### Vocabulary improves

The same terms work in conversation, UI, docs, tests, and code.

### Boundaries stabilize

Components can change independently.

### Data structures feel natural

The schema or data model follows from the concept.

### Special cases disappear

Rules become more regular.

### Tests become easier

Tests can describe behavior directly instead of setup details.

## Abstraction review template

For each core abstraction:

| Question | Answer |
|---|---|
| Name | |
| Purpose | |
| What does it simplify? | |
| What depends on it? | |
| What special cases exist? | |
| What vocabulary does it introduce? | |
| What does it hide? | |
| What does it leak? | |
| What alternatives were considered? | |
| Is it ready to harden? | |
