# Repository Review Prompt

Use this prompt when reviewing a repository from a Muze perspective.

```text
Use the Spiral Assistant repository as background.

Review this repository from the perspective of Muze's frontend-first, maturity-gated spiral model.

Start by recording:

- repository path or URL;
- branch, tag, or commit;
- worktree cleanliness;
- whether dirty or untracked files are included;
- related repositories or internal dependencies;
- which related repositories are in scope, deferred, or out of scope.

Focus on:

- project purpose and roadmap clarity;
- complexity risks;
- abstraction fitness;
- conceptual and technical boundaries;
- package/module structure;
- dependency replaceability;
- dependency review scope;
- thin application layer;
- tests and evidence quality;
- documentation clarity;
- AI-era risks;
- maturity level estimate.

Produce:

1. audit scope;
2. concise overview;
3. key strengths;
4. key risks;
5. boundary map;
6. abstraction warning signs;
7. maturity estimate;
8. recommended first cycle;
9. suggested project-specific Muze docs;
10. facts, assumptions, and missing evidence;
11. optional stakeholder note when the audience includes people outside implementation.

Do not judge only by code quality. Judge whether the project can safely change direction without falling into complexity.

If you include a stakeholder note, keep it plain-language and derive it from the review. It should not add commitments beyond the roadmap and cycle recommendation.

If repository evidence conflicts with README or roadmap claims, treat that as a risk.
```
