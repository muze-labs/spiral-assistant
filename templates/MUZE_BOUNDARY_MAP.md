# Muze Boundary Map

## Purpose

This document describes the project's conceptual and technical boundaries.

A boundary is useful when it makes change easier. A boundary is harmful when it adds ceremony without reducing coupling.

Core question:

> What decision does this boundary protect us from changing later?

## Conceptual boundaries

| Concept | Responsibility | Related concepts | Confusions or overlaps |
|---|---|---|---|
| | | | |

## Technical boundaries

| Boundary | Responsibility | Depends on | Must not depend on | Change protected | Current risk |
|---|---|---|---|---|---|
| Application layer | Product-specific composition | Reusable components | Product details inside reusable libraries | Changing product direction | |
| | | | | | |

## Dependency boundaries

| Dependency | Used for | Scope | Wrapped by | Replaceability risk | Notes |
|---|---|---|---|---|---|
| | | In scope / Deferred / Out of scope | | | |

## Related repositories

| Repository | Relationship | Review scope | Reason | Risk if excluded |
|---|---|---|---|---|
| | Internal dependency / sibling project / tool / example | In scope / Deferred / Out of scope | | |

## Thin application layer check

- [ ] Reusable components have one clear concern.
- [ ] Product-specific composition is visible in the application layer.
- [ ] Core code does not import app-specific code.
- [ ] Storage details do not leak into domain concepts.
- [ ] UI details do not leak into core logic.
- [ ] External dependencies are behind clear boundaries where needed.

## Boundary risks

| Risk | Evidence | Mitigation |
|---|---|---|
| | | |

## Boundary changes

| Date | Change | Reason | Impact |
|---|---|---|---|
| | | | |
