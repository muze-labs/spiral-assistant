# AI-Era Risks Catalog

AI changes the cost structure of software development. This creates new opportunities and new risks.

## AI bloat

AI generates more code, features, tests, wrappers, or abstractions than the project can understand or maintain.

Signal:

- large changes arrive quickly;
- generated code is not reviewed deeply;
- simple tasks produce complex implementations;
- the codebase grows but the model does not get clearer.

Mitigation:

- require small bounded changes;
- ask whether AI reduced complexity;
- prefer competing prototypes over broad implementation;
- record generated complexity as debt.

## Loss of human legibility

The system works, but no human can explain why.

Signal:

- reviewers approve based on tests only;
- generated code uses unfamiliar patterns;
- code names do not match project vocabulary;
- architecture emerges from AI output rather than human intent.

Mitigation:

- require explanation of boundaries and intent;
- maintain architecture notes;
- use smaller components;
- reject code that cannot be explained.

## False maturity

AI-generated prototypes look production-ready before deeper qualities are mature.

Signal:

- polished UI hides missing data integrity or security;
- stakeholders assume "demo" means "done";
- maturity labels are missing.

Mitigation:

- label prototypes explicitly;
- keep maturity matrix visible;
- separate frontend validation from production readiness.

## Shallow evidence

AI generates tests or docs that appear convincing but do not validate the real risk.

Signal:

- tests mirror implementation details;
- edge cases are missing;
- security claims rely on generated assertions;
- coverage increases but confidence does not.

Mitigation:

- define evidence before generating tests;
- review oracle quality;
- include failure cases;
- connect tests to risk register entries.

## Vocabulary drift

AI invents or changes terms, creating hidden conceptual confusion.

Signal:

- prompts, docs, UI, tests, and code use different names;
- same term means multiple things;
- different terms mean the same thing.

Mitigation:

- maintain a glossary;
- review generated names;
- use project vocabulary in prompts and examples.

## Architecture laundering

AI turns vague or weak architectural assumptions into plausible code, hiding uncertainty.

Signal:

- generated implementation assumes a data model, dependency, or boundary without discussion;
- architecture becomes difficult to reverse;
- decisions are not recorded.

Mitigation:

- require architecture decision notes;
- generate multiple options;
- evaluate by simplicity and replaceability;
- avoid hardening generated assumptions.

## Review overload

AI shifts effort from writing to reviewing.

Signal:

- PRs become larger;
- maintainers approve without deep understanding;
- cleanup and refactoring work grows;
- core maintainers become bottlenecks.

Mitigation:

- limit AI-generated change size;
- require focused review goals;
- use component boundaries as work boundaries;
- track review burden as a metric.

## Security overtrust

AI-generated security-sensitive code is trusted too early.

Signal:

- auth, crypto, sandboxing, permissions, or data validation are AI-generated;
- reviewers lack security expertise;
- public deployment occurs without explicit security gate.

Mitigation:

- treat generated security code as untrusted;
- require human review;
- use established libraries and standards where appropriate;
- add security maturity gates.

## Dependency confusion

AI adds dependencies because they are common, not because they fit Muze's boundaries.

Signal:

- dependency count increases quickly;
- project adopts a framework for a small task;
- dependency APIs leak into core concepts.

Mitigation:

- require dependency justification;
- test replaceability;
- prefer small adapters;
- review whether existing Muze libraries already solve the problem.
