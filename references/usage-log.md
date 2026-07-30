# Usage Log

Tracks each application of the system-distillation skill for effectiveness
analysis. See SKILL.md "Effectiveness Tracking" for why this matters.

## Format

Each entry: date | target system | items per bucket | disciplines written |
follow-up status

---

## Use 1 — 2026-07-24

**Target system:** C:\CodexWrokspace (AI agent multi-project workspace)

**Three-way classification:**
- Already have: 2 (layered loading, skill routing)
- Can absorb: 3 (proactive review, mandatory verification, periodic audit)
- Not applicable: 1 (document-driven recovery — WorkBuddy has native memory)

**Disciplines written to ~/.workbuddy/MEMORY.md:**
1. Complete-before-verify (banned phrases, product-type verification mapping)
2. Error sedimentation (immediate write with keywords after non-trivial fix)
3. Proactive review (append "reusable judgment" line, not just activity log)
4. Knowledge self-audit triggers (capacity threshold, skill count, error repeat)
5. Analysis entry order for unfamiliar workspaces (AGENTS → index → conditional)

**Follow-up (to be checked at Use 3):**
- [ ] Have any of these 5 disciplines been re-read in a later session?
- [ ] Has the banned-phrase rule actually reduced "should work" outputs?
- [ ] Has the error-sedimentation rule fired on a real error?

**Self-assessment at creation time: 8.0/10** (inflated by enthusiasm —
reassess at Use 3 with reference-rate data)

---

## Use 2 — 2026-07-30

**Target system:** `evaluate-skills` integration into `system-distillation`

**Three-way classification:**
- Already have: 2 (mechanism classification, user checkpoints)
- Can absorb: 3 (package-action routing, pre-mutation evaluation gate, verdict feedback)
- Not applicable: 1 (full Skill scoring for memory-only actions)

**Skill change:**
1. Added Step 4.5 to distinguish mechanism value from package trust.
2. Routed concrete install/update/merge/create actions through `evaluate-skills`.
3. Kept memory-only and blueprint-only actions on the lightweight path.
4. Added isolated drafting for new candidates and explicit handling for all three verdicts.

**Behavior evidence:**
- Baseline: installation and merge scenarios did not invoke `evaluate-skills`.
- After change: memory-only skipped evaluation; installation and merge required evaluation before mutation.
- Static validation: candidate integrity passed, with no broken local links or duplicate names.

**Follow-up (to be checked at Use 3):**
- [ ] Did a real distillation-triggered Skill installation route through `evaluate-skills`?
- [ ] Did any rejected package still yield a useful memory-only or freshly designed action?

---

_Next entry to be added on Use 3._
