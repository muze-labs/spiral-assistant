# Spiral Assistant

Spiral Assistant is a document-first AI assistant framework for applying Muze's frontend-first, maturity-gated spiral model to new and existing software projects.

It is intended for use with ChatGPT, GitHub Copilot Chat, Claude, local agents, or any AI assistant that can read repository files.

This repository does not contain an application yet. The first version is deliberately small: a set of model documents, templates, catalogs, and reusable prompts. The goal is to make Muze's development model repeatable before turning it into tooling.

## What the assistant helps with

The assistant helps a team:

- clarify the project's purpose and roadmap;
- identify current and newly discovered risks;
- plan roadmap-driven spiral cycles;
- define maturity levels and quality metrics;
- keep complexity under control;
- review abstractions and boundaries;
- decide when to pause for evidence-based risk assessment;
- account for AI-era risks such as generated-code bloat and loss of human legibility.

The assistant should not act as an unsupervised project manager or architect. It is a coach and reviewer that helps humans make better decisions.

## Core idea

Muze's model combines:

- frontend-first validation;
- risk-driven spiral cycles;
- explicit Analyze–Plan–Act–Evaluate loops;
- maturity levels with quality targets;
- roadmap-driven capability planning;
- complexity control;
- abstraction discovery;
- clear conceptual and technical boundaries;
- small decoupled components combined through a thin application layer;
- AI-era caution around code generation and human understanding.

The guiding question is:

> What risk are we reducing, what complexity are we adding, and what evidence would change our mind?

## Repository structure

```text
spiral-assistant/
  README.md
  AGENTS.md
  docs/
    00-quickstart.md
    01-model-overview.md
    02-practical-complexity-guide.md
    03-ai-era-update-unvalidated.md
    04-assistant-workflow.md
  templates/
    MUZE_PROJECT_BRIEF.md
    MUZE_ROADMAP.md
    MUZE_MATURITY.md
    MUZE_RISK_REGISTER.md
    MUZE_BOUNDARY_MAP.md
    MUZE_ABSTRACTION_REVIEW.md
    MUZE_CYCLE_LOG.md
    MUZE_AI_USAGE.md
  catalogs/
    quality-metrics.md
    common-risks.md
    ai-era-risks.md
    abstraction-warning-signs.md
    boundary-patterns.md
  prompts/
    intake-prompt.md
    current-state-audit-prompt.md
    roadmap-cycle-planning-prompt.md
    cycle-evaluation-prompt.md
    repository-review-prompt.md
  examples/
    new-project/
    existing-project/
```

## How to use this repository in a chat

Start a new chat and point the assistant to this repository, or upload a zip of it. Then add the project you want to analyze.

Ask the assistant to read `AGENTS.md` and `docs/00-quickstart.md` first. The first useful result should be a bounded project pass: drafts of the core Muze documents, a proposed next cycle, and the evidence needed to decide whether the roadmap should continue.

For a new project:

```text
Use the Spiral Assistant repository as background.
Help me apply Muze's spiral model to this new project.
Start with intake and produce drafts for:
- MUZE_PROJECT_BRIEF.md
- MUZE_ROADMAP.md
- MUZE_MATURITY.md
- MUZE_RISK_REGISTER.md
```

For an existing project:

```text
Use the Spiral Assistant repository as background.
Review this repository and help us adopt Muze's spiral model.
Start with a current-state audit, identify complexity and abstraction risks,
then propose the first roadmap-driven spiral cycle.
Record the branch, worktree state, and which related repositories or internal
dependencies are in scope before judging maturity.
```

For an end-of-cycle evaluation:

```text
Use the Spiral Assistant repository as background.
Evaluate this cycle using Analyze–Plan–Act–Evaluate.
Check whether maturity targets were met, whether any quality regressed,
and whether new risks require a roadmap pause.
```

## How to add the model to a project

A project adopting the model should add a `docs/muze/` directory:

```text
docs/muze/
  MUZE_PROJECT_BRIEF.md
  MUZE_ROADMAP.md
  MUZE_MATURITY.md
  MUZE_RISK_REGISTER.md
  MUZE_BOUNDARY_MAP.md
  MUZE_ABSTRACTION_REVIEW.md
  MUZE_CYCLE_LOG.md
  MUZE_AI_USAGE.md
```

Copy the files from `templates/` and fill them in with the assistant.

Start with only:

- `MUZE_PROJECT_BRIEF.md`
- `MUZE_ROADMAP.md`
- `MUZE_MATURITY.md`
- `MUZE_RISK_REGISTER.md`

Add the other documents once the assistant has enough project context to say something useful.

## Status

This is a Level 1 assistant: document-first, manually invoked, and human-led.

Possible later levels:

1. Prompt-based assistant.
2. Document-aware assistant.
3. Repository-aware assistant.
4. Workflow-integrated assistant.
5. Semi-agentic assistant with strict controls.

Do not add workflow automation until the document workflow has proven useful.
