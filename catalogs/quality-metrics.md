# Quality Metrics Catalog

This catalog provides reusable quality metrics for project-specific maturity models.

A project should not use every metric. Choose the smallest set that matches the roadmap and current risks.

## Generic maturity scale

| Score | Meaning |
|---|---|
| 1 | Rough, experimental, or provisional. |
| 2 | Basic, partially useful, known gaps. |
| 3 | Good enough for the current maturity level. |
| 4 | Reliable for broader use. |
| 5 | Mature, strong, reusable, or production-ready. |

## Product and frontend metrics

### Usability

Can the intended user complete the main flow without excessive explanation?

### Visual clarity

Does the interface communicate what matters?

### Interaction quality

Do actions, state changes, and feedback feel understandable and predictable?

### Feedback value

Can real users give meaningful feedback from trying the system?

### Learnability

Can a new user understand the model from examples and interaction?

### Accessibility

Can the main interaction work with keyboard navigation, screen readers, and expected web behavior?

## Complexity and architecture metrics

### Conceptual simplicity

Can the system be explained using a small number of clear concepts?

### Abstraction fitness

Does the chosen abstraction simplify dependent code?

### Boundary clarity

Are conceptual and technical responsibilities clearly separated?

### Coupling control

Can one part change without forcing unrelated parts to change?

### Dependency replaceability

Can major dependencies be replaced without rewriting the whole system?

### Thin application layer

Are reusable components kept clean while product-specific composition stays visible?

### Human legibility

Can a maintainer explain the system, its boundaries, and its assumptions?

## Data and backend metrics

### Data model readiness

Is the data structure clear, stable, and suitable for current and near-future use?

### Schema readiness

Do schemas or shapes help without becoming a heavy framework?

### Data integrity

Are commands, updates, migrations, and persistence reliable?

### Query ergonomics

Can users or developers express queries clearly?

### Recovery

Can the system recover from failed writes, crashes, or inconsistent state?

## Engineering metrics

### Maintainability

Can the code be understood and safely changed?

### Test quality

Do tests prove meaningful behavior and failure cases?

### Evidence quality

Does the evidence actually validate the risk being reduced?

### Documentation clarity

Can users and maintainers understand the project from docs and examples?

### Performance envelope

Are the expected data sizes, interaction latencies, and resource limits understood?

## Security and operations metrics

### Security containment

Are trust boundaries, access control, and unsafe operations contained?

### Privacy

Is personal or sensitive data handled with explicit care?

### Operational reliability

Can the system be deployed, monitored, backed up, and recovered?

### Observability

Can failures and important state changes be understood?

## AI-era metrics

### AI containment

Are AI changes limited to safe, reviewable scopes?

### Generated-code provenance

Do we know which parts were AI-generated or AI-assisted?

### Review burden

Did AI reduce work, or move work to human reviewers?

### Prompt/vocabulary alignment

Do prompts, docs, UI labels, tests, and code use the same concepts?

### Bloat resistance

Did the cycle avoid unnecessary generated code and features?

### Security distrust

Is AI-generated security-sensitive code treated as untrusted until reviewed?
