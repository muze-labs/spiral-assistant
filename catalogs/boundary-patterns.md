# Boundary Patterns

Use this catalog to identify conceptual and technical boundaries.

## Core question

> What decision does this boundary protect us from changing later?

## Common boundaries

### Application layer boundary

Keeps product-specific composition separate from reusable components.

Good sign:

- app code wires components together;
- reusable libraries remain independent.

Bad sign:

- product-specific rules leak into library code.

### Storage boundary

Protects against changing storage backend, persistence format, or hosting model.

Examples:

- file storage;
- IndexedDB;
- Solid pod;
- SQL database;
- HTTP API;
- in-memory store.

Good sign:

- core concepts do not depend on storage details.

### Rendering boundary

Protects against changing DOM update strategy, templating, or UI layer.

Good sign:

- domain logic does not import rendering code.

### Transport boundary

Protects against changes in network, authentication, retry, caching, or request format.

Good sign:

- core logic can be tested without HTTP.

### Domain boundary

Separates the concepts of the problem from UI, storage, and framework details.

Good sign:

- domain vocabulary appears in docs, tests, and examples.

### Query boundary

Separates how data is requested from how it is stored.

Good sign:

- query model can change without rewriting storage.

### Command boundary

Separates user intent or state changes from persistence details.

Good sign:

- commands can be tested and replayed.

### Adapter boundary

Allows external systems to be integrated without taking over the core.

Good sign:

- adapter depends on core, but core does not depend on adapter.

### AI work boundary

Defines where AI may safely make changes.

Good sign:

- AI can modify a small component with clear tests and no hidden side effects.

## Boundary review questions

- What belongs inside this boundary?
- What belongs outside it?
- What changes does this boundary protect against?
- What dependencies cross it?
- Is the boundary conceptual, technical, or both?
- Does it make the system easier to understand?
- Does it make replacement possible?
- Does it add ceremony without reducing coupling?
- Is the boundary visible in docs and examples?
- Would a beginner understand the distinction?

## Boundary map template

| Boundary | Responsibility | Depends on | Must not depend on | Change protected | Current risk |
|---|---|---|---|---|---|
| | | | | | |
