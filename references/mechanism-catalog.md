# Mechanism Catalog: Common Patterns in External Systems

Reference for Step 2 of the distillation workflow. Use these categories to
classify extracted mechanisms quickly.

> **How to use this file:** Each category first describes the *abstract pattern*
> (applies to any AI agent or system), then gives WorkBuddy as the *current
> instance*. If running on a different platform, rewrite only the "current
> instance" column — the abstract pattern stays the same.

## Context Recovery Mechanisms

Systems that lose state between sessions develop ways to reconstruct context:

| Mechanism | Abstract pattern | WorkBuddy (current instance) |
|---|---|---|
| Layered document loading | Entry file → global rules → conditional docs, read on demand | Cloud profile + conversation_search + local memory |
| Project index / manifest | Single file listing all projects with status fields | TaskList + workspace memory |
| "Next action" field | Each project records what to do first on resume | TaskCreate metadata |
| Context os / startup summary | Runtime injects summary at session start | Auto-injected cloud profile at session start |

**Absorption signal:** If the external system invests heavily in recovery that
the current platform handles natively, classify as "already have" — but check if
the discipline of *proactive* recovery (reading context before acting) is weaker.

## Experience Compounding Mechanisms

| Mechanism | Abstract pattern | WorkBuddy (current instance) |
|---|---|---|
| Error → knowledge base | Mistakes written to searchable store with keywords | MEMORY.md + skill references |
| Summary promotion | High-frequency lessons elevated from detail to summary | Daily log → workspace MEMORY → user MEMORY |
| Periodic self-audit | Scheduled or triggered review to merge/archive/distill | Trigger-based (capacity threshold, error repeat) |
| Project-scoped vs cross-project | Keep project lessons in project, general lessons in shared | Three-tier memory: daily log → project MEMORY → user MEMORY |

**Absorption signal:** The platform has storage layers but may lack the
*proactive discipline* of writing reusable judgments (not just activity logs).

## Quality Enforcement Mechanisms

| Mechanism | Abstract pattern | WorkBuddy (current instance) |
|---|---|---|
| Mandatory verification | Must run real checks before claiming done | Bash test/build, present_files, assertions |
| Banned phrases | Speculative language prohibited in completion claims | "should work"/"theoretically"/"probably" banned |
| Verification by product type | Code→test, web→render, data→assert, config→parse | Same mapping |
| Risk disclosure | If can't verify, state what's checked/uncheckable | Same rule |

**Absorption signal:** This is universally applicable. If the agent tends to
describe rather than execute verification, this is always absorbable.

## Resource Routing Mechanisms

| Mechanism | Abstract pattern | WorkBuddy (current instance) |
|---|---|---|
| Skill routing table | Scenario → minimal skill combination | SkillManage + skill selection rules |
| Umbrella skill preference | One large skill covers many small errors | Same principle |
| Loading scale by complexity | Simple: 0-1, Medium: 1-2, Complex: 2-3 | Same guideline |

**Absorption signal:** The platform likely already has this. Check if the
*discipline* of minimal loading is followed, not whether the mechanism exists.

## Isolation & Governance Mechanisms

| Mechanism | Abstract pattern | WorkBuddy (current instance) |
|---|---|---|
| Project numbering | Sequential IDs, never reused | TaskCreate IDs (but less structured) |
| Root directory constraints | Only governance docs at root, projects in folders | Workspace conventions |
| Template system | Pre-made structures for new projects | Skill assets / templates |
| Archive flow | README update → clean → index → move to archive | Memory distillation (30-day rule) |

**Absorption signal:** Partially applicable. The traceability principle matters
even if the ID system differs.
