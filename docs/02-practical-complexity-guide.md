# Applying Muze's Spiral Model in Practice

## Purpose

This document explains the practical side of Muze's model.

The central idea:

> Each development cycle should reduce important uncertainty while keeping the system easy to understand, change, and replace.

For Muze, software development is not primarily a process of adding features. It is a process of discovering the right shape of a system without falling into unnecessary complexity.

A project becomes mature not by becoming large, complete, or heavily engineered, but by becoming clearer, more stable, more useful, and easier to change.

## 1. The main practical risk: complexity

Many software projects fail because the team cannot keep the system understandable. Features accumulate. Dependencies become hard to replace. Concepts blur together. A small change starts affecting unrelated parts of the system.

The project may still work, but it becomes difficult to safely move forward.

Muze treats complexity as a recurring project risk, not just a technical inconvenience.

At the end of each cycle, ask:

> Did the system become easier or harder to change?

## 2. Common risks in web development

| Risk | What it looks like | Typical mitigation |
|---|---|---|
| Complexity creep | Every feature makes the system harder to explain or change. | Reduce scope, split concepts, simplify abstractions. |
| Wrong abstraction | The model works only by adding special cases, adapters, and exceptions. | Revisit the core concept before hardening data or APIs. |
| Boundary confusion | UI, storage, network, domain rules, and app-specific code blur together. | Define conceptual and technical boundaries explicitly. |
| Feature pressure | Completeness is prioritized over clarity. | Prefer a smaller coherent system over a larger confused one. |
| Prototype debt | Shortcuts from early experiments silently become permanent architecture. | Record intentional debt and define repayment triggers. |
| Dependency lock-in | A library, framework, platform, or service becomes too central to replace. | Keep dependencies behind small interfaces or adapters. |
| Vocabulary mismatch | Developers, users, documentation, and code use different words for the same ideas. | Maintain a shared vocabulary and rename aggressively. |
| Premature hardening | Security, schema, or infrastructure work is done before the product shape is validated. | Match quality targets to maturity level. |
| Late hardening | The project keeps acting like a prototype after real users or real data appear. | Raise technical quality targets explicitly as maturity increases. |

## 3. Architecture must withstand change

Physical architecture must account for gravity.

Software architecture has a different force acting on it: change.

Requirements change. Dependencies change. Browsers change. Security expectations change. Users misunderstand things. Better abstractions are discovered. A project may move from prototype to product, from local use to hosted service, or from one data backend to another.

For Muze:

> Software architecture should be judged by how well it withstands change.

Muze prefers:

- small, decoupled components;
- clear conceptual boundaries;
- clear technical boundaries;
- a thin application layer that combines components;
- browser-native standards where possible;
- replaceable dependencies;
- simple abstractions that make dependent code simpler.

## 4. Abstraction discovery

One of Muze's most important practices is searching for abstractions that make everything built on top of them simpler.

Some abstractions are common but wrong for the problem. They may appear reasonable at first, but later produce complex schemas, awkward APIs, special cases, fragile adapters, or code that is harder to use than the abstraction itself.

Before investing heavily in schemas, data handling, APIs, and infrastructure, ask:

> Are we building on the right abstraction?

A useful analogy is the historical shift from epicycles to heliocentrism. The old model could explain planetary motion only by adding more and more complexity. A better model changed the center of the system and made many things simpler at once.

Muze looks for the software equivalent of that shift.

### Warning signs of a poor abstraction

| Warning sign | What it suggests |
|---|---|
| Many special cases | The abstraction does not match the real problem shape. |
| Repeated adapter code | Boundaries are misplaced or too leaky. |
| Forced naming | The concept may not be real, or may be split incorrectly. |
| Complex dependent code | The abstraction pushes complexity upward. |
| Difficult schemas | The data model is centered on the wrong thing. |
| Heavy setup for simple cases | The abstraction is too large or too indirect. |
| Hard-to-replace dependencies | Technical boundaries are unclear. |

### Signs of a useful abstraction

| Good abstraction | Effect |
|---|---|
| Clarifies vocabulary | People can explain the system more easily. |
| Reduces dependent code | Common cases become shorter and clearer. |
| Removes special cases | Behavior becomes more regular. |
| Stabilizes boundaries | Components can change independently. |
| Supports natural schemas | Data structures follow from the concept. |
| Simplifies examples | Beginner-facing usage becomes easier. |

Practical rule:

> Do not harden a system around an abstraction that is still producing complexity.

## 5. Boundaries as architecture

A boundary can be conceptual, technical, or both.

A conceptual boundary separates ideas.

A technical boundary separates code that should be able to change independently.

Ask:

> What decision does this boundary protect us from changing later?

Examples:

| Boundary | Change it protects against |
|---|---|
| Storage adapter | Changing from files to Solid, IndexedDB, SQL, or HTTP. |
| Rendering layer | Changing DOM update strategy or template format. |
| Domain model | Changing UI without changing core concepts. |
| Transport layer | Changing fetch, authentication, retry, or caching behavior. |
| Application layer | Changing product-specific composition without changing libraries. |

A boundary is useful when it makes change easier. A boundary is harmful when it adds ceremony without reducing coupling.

## 6. Shared vocabulary

Muze uses a lightweight version of the Domain-Driven Design idea of shared vocabulary.

The goal is not to introduce a heavy DDD process. The goal is to make sure the project has words that match the real concepts.

Each cycle should ask:

- Which words became clearer?
- Which words are overloaded?
- Which names in the code do not match the language users use?
- Which concepts should be split?
- Which concepts should be merged?
- Which terms need to appear in documentation, examples, APIs, and code?

A vocabulary problem is often an architecture problem in disguise.

## 7. Small components and a thin application layer

The architecture Muze prefers is:

> Simple decoupled components, combined in a thin application layer.

Reusable components should have one clear concern. Applications may compose several concerns, but the composition should remain visible and understandable.

Muze applies this in a lightweight way:

- the core should not depend on the framework;
- domain concepts should not depend on storage details;
- storage should not depend on UI rendering;
- beginner-friendly APIs may wrap smaller components, but should not erase their boundaries;
- dependencies should be replaceable without rewriting the whole system.

## 8. Completeness is not maturity

A project can have many features and still be immature if it is hard to understand, fragile, insecure, or built on poor abstractions.

A project can have few features and still be mature if its concepts are clear, its boundaries are strong, and it can safely evolve.

Practical rules:

- Prefer a small coherent system over a large confused system.
- Prefer fewer concepts over more features.
- Prefer a missing feature over a feature that distorts the model.
- Prefer a clean boundary over a shortcut that couples unrelated parts.
- Prefer a simple dependency over a powerful dependency that takes over the architecture.

## 9. Debt

Early cycles sometimes require shortcuts. That is acceptable when the shortcut is intentional, visible, and temporary.

A simple debt note should contain:

| Field | Example |
|---|---|
| Shortcut | Authentication is mocked. |
| Reason | Needed to validate the interaction flow first. |
| Risk | Security behavior is not yet representative. |
| Repayment trigger | Before public deployment or maturity level 4. |
| Mitigation | Add real identity and permission checks behind an adapter. |

## 10. Practical cycle checklist

### Analyze

- What is the biggest risk right now?
- Is complexity increasing?
- Which parts are hardest to explain?
- Which changes were harder than expected?
- Are we using the right abstraction?
- Are any names misleading?
- Are any dependencies becoming too central?
- Which quality metrics regressed?

### Plan

- Which maturity level are we targeting?
- Which quality metrics must improve?
- Which qualities only need to be preserved?
- Which feature should be deferred to protect simplicity?
- Which boundary should be clarified?
- What evidence do we need from this cycle?

### Act

- Build the smallest useful increment.
- Keep the result usable, not merely visible.
- Avoid broad infrastructure before validating direction.
- Keep reusable components decoupled.
- Put product-specific choices in the thin application layer.
- Record intentional shortcuts as debt.

### Evaluate

- Did the system become easier or harder to change?
- Did the new work reduce the intended risk?
- Did the abstraction simplify dependent code?
- Did any boundary become blurry?
- Did any new risk appear?
- Should we continue, pause, split, simplify, or research?

## References

- Frederick P. Brooks, "No Silver Bullet": https://www.cs.unc.edu/techreports/86-020.pdf
- Ben Moseley and Peter Marks, "Out of the Tar Pit": https://curtclifton.net/papers/MoseleyMarks06a.pdf
- David L. Parnas, "On the Criteria To Be Used in Decomposing Systems into Modules": https://dl.acm.org/doi/10.1145/361598.361623
- Martin Fowler, Bounded Context: https://martinfowler.com/bliki/BoundedContext.html
- Martin Fowler, Ubiquitous Language: https://martinfowler.com/bliki/UbiquitousLanguage.html
- Alistair Cockburn, Hexagonal Architecture: https://alistair.cockburn.us/hexagonal-architecture
- Martin Fowler, Technical Debt: https://martinfowler.com/bliki/TechnicalDebt.html
