# Muze's Frontend-First Maturity-Gated Spiral Model

## Executive summary

Muze uses a development model inspired by the Agile Manifesto and Barry Boehm's spiral model.

The model is frontend-first: early work focuses on things people can actually see, touch, and try. Initial cycles emphasize usability, interaction flow, visual clarity, and feedback value. Later cycles raise expectations for deeper technical qualities such as security, schemas, data modeling, maintainability, performance, and operational reliability.

The core principle:

> A project does not mature by improving every quality at once. It matures by improving the qualities that reduce the most important risks at that stage, while avoiding regression in the qualities already achieved.

## Foundations

The Agile Manifesto values working software, collaboration, and responding to change over rigid plans and excessive documentation. Its principles emphasize early and continuous delivery, frequent working software, technical excellence, simplicity, and regular reflection.

Boehm's spiral model adds the idea that software development should be risk-driven. Each cycle identifies objectives, constraints, alternatives, and risks, then validates the result and prepares the next cycle.

Muze extends this by adding maturity levels and quality targets. Each maturity level defines minimum acceptable scores for selected quality metrics. Not every metric must improve in every cycle.

## Core concepts

A risk is anything that could make the project fail or waste effort.

A quality metric is a way to score one aspect of quality.

A maturity level is a step in the project's growth. Each level defines minimum acceptable scores for selected quality metrics.

A cycle is one turn through the spiral:

> Analyze → Plan → Act → Evaluate

## The cycle

### Analyze

Review the current state.

Ask:

- What is already known?
- What feedback has been received?
- Which quality scores are strong enough?
- Which risks are still open?
- What is the most important uncertainty to reduce next?

### Plan

Choose the next roadmap capability and maturity target.

Ask:

- Which quality metrics must improve now?
- Which metrics can stay at their current level?
- Which features should be deferred?
- What evidence would prove that the next step is safe?

### Act

Build something that reduces the chosen risk.

This may be:

- a usable increment;
- a prototype;
- a proof of concept;
- a test suite;
- a schema experiment;
- research;
- a refactoring;
- a benchmark.

The action must produce evidence, not merely activity.

### Evaluate

Check whether the cycle met its maturity goals.

Ask:

- Did we meet the quality targets?
- Did anything regress?
- Did we discover new risks?
- Does the roadmap need to change?
- Should the next cycle proceed or pause for evidence?

## Risk-triggered evidence pauses

Sometimes a cycle reveals a new risk that changes the roadmap.

Examples:

- users misunderstand the main interaction model;
- a data model does not support required queries;
- a security assumption is wrong;
- a dependency is immature;
- a performance bottleneck appears earlier than expected;
- a core abstraction creates special cases.

In such cases, Muze allows the next normal cycle to be paused. The next step becomes an evidence-based risk assessment, such as research, a proof of concept, benchmark, or technical spike.

Only after the risk and mitigation options are understood should the roadmap be adjusted and resumed.

## Frontend-first

Frontend-first means early cycles produce something people can actually try.

A written specification can be misunderstood. A diagram can hide interaction problems. A screenshot can suggest a product that does not actually work.

A usable interface, even with limited functionality, gives better feedback.

Frontend-first does not mean that schemas, security, data modeling, or maintainability are ignored. It means their target levels are lower until the direction has been validated.

## Example quality metrics

A generic web product might use:

| Metric | Meaning |
|---|---|
| Usability | Can people use it without excessive explanation? |
| Visual clarity | Does the interface communicate what matters? |
| Feedback value | Can real users give meaningful feedback from trying it? |
| Data model | Is the data structure clear, stable, and suitable? |
| Maintainability | Can the code be understood and safely changed? |
| Security | Are access, trust, and misuse risks properly handled? |

## Example scoring

| Score | Meaning |
|---|---|
| 1 | Rough or provisional |
| 2 | Basic but incomplete |
| 3 | Good enough for current use |
| 4 | Reliable for broader use |
| 5 | Mature, strong, or reusable |

## Operating rules

1. Each cycle must reduce a meaningful risk.
2. Each maturity level has explicit quality targets.
3. Not every metric must improve in every cycle.
4. Already achieved quality should not silently regress.
5. Newly discovered risks can pause the roadmap until evidence is gathered.

## References

- Agile Manifesto: https://agilemanifesto.org/
- Agile Principles: https://agilemanifesto.org/principles.html
- Barry Boehm, "A Spiral Model of Software Development and Enhancement": https://www.cse.msu.edu/~cse435/Homework/HW3/boehm.pdf
- Goal Question Metric overview: https://www.cs.umd.edu/users/mvz/handouts/gqm.pdf
- CMMI levels: https://cmmiinstitute.com/learning/appraisals/levels
