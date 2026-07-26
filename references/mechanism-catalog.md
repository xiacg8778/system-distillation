# Mechanism Catalog: Common Patterns in External Systems

Reference for Step 2 of the distillation workflow. Use these categories to
classify extracted mechanisms quickly.

## Context Recovery Mechanisms

Systems that lose state between sessions develop ways to reconstruct context:

| Mechanism | How it works | WorkBuddy equivalent |
|---|---|---|
| Layered document loading | Entry → global → conditional docs, read on demand | Cloud profile + conversation_search + local memory |
| Project index / manifest | Single file listing all projects with status | TaskList + workspace memory |
| "Next action" field | Each project records what to do first on resume | TaskCreate metadata |
| Context os / startup summary | MCP server injects summary at session start | Auto-injected cloud profile at session start |

**Absorption signal:** If the external system invests heavily in recovery that
WorkBuddy handles natively, classify as "already have" — but check if the
discipline of *proactive* recovery (reading context before acting) is weaker.

## Experience Compounding Mechanisms

| Mechanism | How it works | WorkBuddy equivalent |
|---|---|---|
| Error → knowledge base | Mistakes written to searchable docs with keywords | MEMORY.md + skill references |
| Summary promotion | High-frequency lessons elevated from detail to summary | Daily log → workspace MEMORY → user MEMORY |
| Periodic self-audit | Scheduled review to merge/archive/distill | Trigger-based (capacity threshold, error repeat) |
| Project-scoped vs cross-project | Keep project lessons in project, general lessons in shared | Three-tier memory: daily log → project MEMORY → user MEMORY |

**Absorption signal:** WorkBuddy has the storage layers but may lack the
*proactive discipline* of writing reusable judgments (not just activity logs).

## Quality Enforcement Mechanisms

| Mechanism | How it works | WorkBuddy equivalent |
|---|---|---|
| Mandatory verification | Must run real checks before claiming done | Bash test/build, present_files, assertions |
| Banned phrases | "should work" / "theoretically" prohibited | Same rule, internalize as habit |
| Verification by product type | Code→test, web→browser, data→assert, config→parse | Same mapping |
| Risk disclosure | If can't verify, state what's checked/uncheckable | Same rule |

**Absorption signal:** This is universally applicable. If WorkBuddy tends to
describe rather than execute verification, this is always absorbable.

## Resource Routing Mechanisms

| Mechanism | How it works | WorkBuddy equivalent |
|---|---|---|
| Skill routing table | Scenario → minimal skill combination | SkillManage + skill selection rules |
| Umbrella skill preference | One large skill covers many small errors | Same principle |
| Loading scale by complexity | Simple: 0-1, Medium: 1-2, Complex: 2-3 | Same guideline |

**Absorption signal:** WorkBuddy already has this. Check if the *discipline*
of minimal loading is followed, not whether the mechanism exists.

## Isolation & Governance Mechanisms

| Mechanism | How it works | WorkBuddy equivalent |
|---|---|---|
| Project numbering | Project001_name, IDs never reused | TaskCreate IDs (but less structured) |
| Root directory constraints | Only governance docs at root, projects in folders | Workspace conventions |
| Template system | Pre-made structures for new projects | Skill assets / templates |
| Archive flow | README update → clean → index → move to _archive | Memory distillation (30-day rule) |

**Absorption signal:** Partially applicable. WorkBuddy's task system is less
formal than a numbered project system, but the principle of traceability matters.
