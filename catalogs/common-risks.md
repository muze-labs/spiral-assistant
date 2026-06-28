# Common Risks Catalog

Use this catalog to start a project-specific risk register.

Do not copy all risks blindly. Select the ones that matter for the current roadmap and maturity level.

## Product risks

### Wrong problem

The project solves a problem users do not actually have.

### Wrong audience

The project is designed for users who are not the real users.

### Weak feedback

The team receives feedback on screenshots, descriptions, or assumptions instead of usable behavior.

### Polished prototype confusion

A prototype looks mature but lacks security, data integrity, maintainability, or operational quality.

### Roadmap drift

The project roadmap changes implicitly due to client pressure, but the architecture still serves the old direction.

## Complexity risks

### Complexity creep

Each feature makes the system harder to understand.

### Feature pressure

Completeness is prioritized over clarity.

### Wrong abstraction

The core model technically works but requires special cases, adapters, exceptions, or complex dependent code.

### Boundary confusion

UI, storage, network, domain logic, and product-specific code blur together.

### Hidden coupling

Components appear separate but cannot change independently.

### State complexity

State is spread across too many places or represented implicitly.

### Control-flow complexity

It is hard to follow what happens when a user action or command runs.

## Architecture risks

### Dependency lock-in

A library, framework, service, or platform becomes too central to replace.

### Framework gravity

The framework starts defining the architecture instead of being a replaceable tool.

### Application layer thickening

Product-specific composition spreads into reusable components.

### Leaky adapter

An adapter leaks implementation details into the core.

### Premature abstraction

A generalized solution is built before the real use cases are understood.

### Late abstraction

Too much code is built around duplicated local concepts before a shared abstraction is found.

## Data risks

### Premature schema hardening

Schemas or storage models are hardened before the product direction is validated.

### Data model mismatch

The data model does not fit the queries, workflows, or concepts users need.

### Migration risk

Data is committed before migration paths are understood.

### Integrity risk

Updates, commands, or writes can leave the system inconsistent.

### Query mismatch

The chosen query model is too hard for the intended users or too weak for the required use cases.

## Security risks

### Trust boundary confusion

It is unclear which code, users, or inputs are trusted.

### Public prototype exposure

A prototype is exposed publicly before security targets are raised.

### Unsafe execution

User or AI-generated code is executed without adequate isolation.

### Authorization gap

Authentication exists but permissions are incomplete or unclear.

### Secret handling

Secrets or credentials are stored, logged, or exposed unsafely.

## Process risks

### Missing evidence

A cycle produces work but not evidence.

### Roadmap autopilot

The team continues the next planned cycle even after discovering new risks.

### Debt invisibility

Shortcuts are taken but not recorded.

### Metrics theater

Scores or gates exist but do not affect decisions.

### No owner

A risk is known but no one owns the investigation or mitigation.

## AI-era risks

See `ai-era-risks.md`.
