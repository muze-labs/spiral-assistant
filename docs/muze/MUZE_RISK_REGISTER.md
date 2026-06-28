# Muze Risk Register

## Purpose

This register tracks known risks, newly discovered risks, mitigation options, and evidence needed for Spiral Assistant.

## Risk levels

| Level | Meaning |
|---|---|
| Low | Worth watching, unlikely to block progress. |
| Medium | Needs active mitigation or evidence soon. |
| High | Could invalidate the roadmap or maturity target. |
| Critical | Should pause the normal roadmap until assessed. |

## Current risks

| ID | Risk | Type | Level | Why it matters | Evidence needed | Mitigation | Owner | Status |
|---|---|---|---|---|---|---|---|---|
| R001 | Process bloat | Complexity | High | The assistant could grow prompts, templates, and docs faster than users can understand or maintain them. | Another audit showing which docs are actually used. | Prefer simplification over expansion; add no new templates without evidence. | Muze | Open |
| R002 | First-pass docs too heavy | Adoption | Medium | Eight standard docs may discourage adoption, especially for small projects. | Observe whether users maintain the docs after first generation. | Keep staged adoption rule: start with four docs, add the rest only when useful. | Muze | Open |
| R003 | Assistant behavior depends on one model | AI-era | Medium | The workflow may work with this assistant but fail with another assistant surface. | Run same audit prompt in another assistant or with less steering. | Strengthen examples and acceptance checks before tooling. | Muze | Open |
| R004 | Generic examples are too abstract | Evidence | Medium | New users may not see what good output looks like. | User feedback from first external adoption. | Add one compact real/anonymized example only if needed. | Muze | Open |
| R005 | Metrics theater | Process | Medium | Maturity scores could become decorative if they do not affect cycle decisions. | Check whether next-cycle choices cite scores and evidence. | Require evidence and uncertainty with every score. | Muze | Open |
| R006 | Dependency scope ambiguity | Boundary | Low | Audits may ignore internal dependencies or expand too far. | More repo audits with internal dependencies. | Current quickstart and prompts require dependency scope. | Muze | Watching |

## Newly discovered risks

| Date | Risk | Discovered during | Impact on roadmap | Action |
|---|---|---|---|---|
| 2026-06-28 | Existing-repo audits need branch/worktree scope | SimplyStore test-run | Added audit-scope requirement | Done |
| 2026-06-28 | Internal dependencies need explicit review scope | SimplyStore discussion | Added dependency-scope guidance | Done |
| 2026-06-28 | Self-audit could become documentation theater | Self-audit | Keep docs concise and evaluate against checklist | In progress |

## Evidence pauses

| Risk | Trigger | Evidence activity | Output | Decision |
|---|---|---|---|---|
| Process bloat | A test-run suggests adding several new templates or prompts | Simplification review | List of duplicate or unused docs/prompts | Simplify before expanding |
| Assistant dependency | Another assistant produces broad or unbounded output | Cross-assistant audit comparison | Difference report | Improve examples or instructions |

## Accepted debt

| Debt | Reason | Risk | Repayment trigger | Mitigation |
|---|---|---|---|---|
| No automated validation | Tooling would be premature. | Broken links or stale prompts may go unnoticed. | Repeated manual audits show clear mechanical checks. | Use `rg` and review checklists for now. |
| Generic examples | Real examples need more validation. | New users may not know what good output looks like. | First user outside core team struggles to apply the repo. | Add one compact example, not a large case study. |
| AI-era update marked unvalidated | Evidence is still emerging. | Users may over-trust provisional claims. | Revising model docs for public use. | Keep status label explicit. |

## Retired risks

| Risk | Why retired | Evidence |
|---|---|---|
| Missing audit scope guidance | Added to quickstart, workflow, prompts, and boundary map. | Current docs include branch/worktree and dependency scope. |
