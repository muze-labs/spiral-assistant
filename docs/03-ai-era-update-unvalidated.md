# AI-Era Update to Muze's Spiral Model

## Status

This document is an explicit update to the earlier Muze spiral model documents.

It is **not yet validated**.

The purpose is to identify assumptions in pre-AI software engineering practice that may now have shaky foundations, and to describe how Muze's model should respond while evidence is still emerging.

## Central update

AI changes the cost of producing software.

It does not automatically change the cost of understanding, trusting, evolving, or owning software.

The key question becomes:

> Can AI help us discover simpler abstractions and reduce complexity, or is it merely allowing us to build complex systems faster than humans can understand them?

## 1. Assumption: writing software is high-effort and expensive

Status: weakened.

AI coding tools reduce the effort of generating code, especially for small, familiar, boilerplate-heavy, or greenfield tasks.

Impact:

- early cycles can include more competing prototypes;
- throwaway implementations become cheaper;
- design alternatives can be tested faster.

Model update:

Use AI for **abstraction tournaments**: generate several small approaches, then judge them by simplicity, boundaries, vocabulary, dependency shape, and ability to change.

## 2. Assumption: because code is expensive, teams naturally avoid unnecessary code

Status: invalidated or dangerous.

When code becomes cheap, restraint becomes less automatic. AI makes it easy to generate features, wrappers, adapters, and "complete" implementations before the team has earned that complexity.

Impact:

- feature creep can accelerate;
- generated code can hide architectural confusion;
- large changes can appear productive while increasing review burden.

Model update:

Add an **AI bloat risk** check:

> Did AI help reduce complexity, or merely produce more code faster?

## 3. Assumption: human implementation is the main bottleneck

Status: weakened.

The bottleneck may shift from writing code to reviewing, understanding, verifying, and owning code.

Impact:

- review capacity becomes more important;
- architectural judgment becomes more important;
- clear boundaries become more important.

Model update:

Add a **maintainer load** metric:

> How much human review, explanation, and cleanup does AI-generated work create?

## 4. Assumption: humans need to understand the software

Status: central to Muze, but under pressure.

It is possible that future AI systems will maintain software that no individual human fully understands. Muze should not ignore that possibility.

For now, the practical stance is:

> Software should remain understandable by humans until there is strong evidence that non-human-maintainable systems are safer, more reliable, and more democratic.

Model update:

Add **human legibility** as an explicit maturity metric.

## 5. Assumption: small, decoupled components are the best defense against complexity

Status: still strong, probably strengthened.

AI agents work better when tasks are bounded. A small component with clear tests, clear API, and clear vocabulary is a safer target for AI assistance than a tangled application with hidden side effects.

Model update:

Frame components as **human-and-AI work boundaries**.

A good component should be understandable by humans and safely modifiable by AI within a constrained scope.

## 6. Assumption: schemas and data models should wait until direction is validated

Status: mostly valid, but changed.

AI makes it cheaper to sketch schemas, generate migrations, compare storage models, and build throwaway data experiments.

But once real user data exists, data modeling mistakes remain expensive.

Model update:

Distinguish:

- exploratory schemas: cheap, disposable, AI-assisted;
- committed schemas: reviewed, documented, migration-aware, security-aware.

## 7. Assumption: prototypes are visibly incomplete and therefore safe to treat as prototypes

Status: weakened.

AI-generated prototypes can look polished very quickly. Stakeholders may mistake a convincing demo for a mature product.

Model update:

Every prototype should carry a visible maturity label:

> This is Level 1: usable concept. Security, data integrity, maintainability, and operational quality have not yet reached production maturity.

## 8. Assumption: tests and quality gates are reliable if present

Status: weakened.

AI can generate tests, but it can also generate shallow tests, tests that encode the implementation instead of the requirement, or tests that miss the real risk.

Model update:

Add **evidence quality** as a metric:

- Does the test check real behavior?
- Does it cover failure cases?
- Was it reviewed by someone who understands the risk?
- Does it protect a boundary or only preserve generated behavior?

## 9. Assumption: dependency minimization means writing more code yourself

Status: changed.

AI makes custom glue code, adapters, wrappers, and small utilities cheaper. That strengthens Muze's ability to avoid unnecessary dependencies, but it also creates a danger of generating piles of bespoke code no one really owns.

Model update:

Use a **replaceability test**:

> Whether code is external or generated internally, can we replace it without rewriting the system?

## 10. Assumption: shared vocabulary matters because humans translate domain ideas into code

Status: still strong, but the reason changes.

AI can turn vague language into plausible code. That makes unclear vocabulary more dangerous because ambiguity can be hidden instead of resolved.

Model update:

Add an **AI vocabulary check**:

- Are prompts, docs, code names, tests, and UI labels using the same terms?
- Did AI invent new names?
- Did it collapse two distinct concepts into one?
- Did it split one concept into multiple inconsistent terms?

## 11. Assumption: architecture should be designed carefully because changing it later is expensive

Status: partly weakened, partly strengthened.

AI lowers the cost of rewriting and experimentation. But once users, data, dependencies, and mental models accumulate, architectural mistakes still become expensive.

Model update:

Use AI for **architecture probes**: small competing implementations evaluated by how much dependent code they simplify.

## 12. Assumption: code is the main artifact

Status: weakened.

In an AI-assisted world, durable artifacts may increasingly be:

- vocabulary;
- tests;
- examples;
- architecture notes;
- risk registers;
- maturity metrics;
- prompts or agent instructions;
- schemas and contracts;
- review decisions.

AI can regenerate code from strong constraints, but it cannot reliably recover missing intent.

Model update:

Expand the view-source philosophy to **view intent**.

Every component should make its intent inspectable:

- what problem it solves;
- what it deliberately does not solve;
- what boundary it protects;
- what changes it expects;
- which assumptions it relies on.

## New AI-era quality metrics

| Metric | Question |
|---|---|
| Human legibility | Can a maintainer explain the system and its boundaries? |
| AI containment | Are AI changes limited to safe, reviewable scopes? |
| Generated-code provenance | Do we know which parts were AI-generated or heavily AI-assisted? |
| Review burden | Did AI reduce work, or move work to human reviewers? |
| Evidence quality | Do tests and prototypes prove the actual risk? |
| Abstraction fitness | Does the chosen abstraction simplify dependent code? |
| Prompt/vocabulary alignment | Do prompts, docs, UI, tests, and code use the same concepts? |
| Bloat resistance | Did the cycle avoid unnecessary generated code and features? |
| Security distrust | Is AI-generated security-sensitive code treated as untrusted until reviewed? |

## AI assumption review

At the start and end of each cycle, ask:

1. Which parts of this cycle became cheaper because of AI?
2. Which risks became larger because AI can generate too much too quickly?
3. Which human assumptions did AI hide instead of resolving?
4. Which generated code is not yet understood by a human?
5. Which abstractions should be tested by generating competing implementations?
6. Which parts of the system are safe for AI to modify independently?
7. Which parts require human architectural review?
8. Did AI reduce complexity, or did it only increase output?

## Provisional principle

> Use AI aggressively for exploration, comparison, scaffolding, review, and simplification. Do not allow AI to become an unsupervised source of architecture.

## References

Use up-to-date sources when revising this document. Suggested areas:

- empirical studies of AI coding productivity;
- DORA reports on AI and software delivery;
- studies on AI-generated code quality and security;
- benchmarks such as SWE-bench;
- human oversight literature for AI-assisted software engineering.
