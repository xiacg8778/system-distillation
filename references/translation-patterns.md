# Translation Patterns: External Practice → Native Execution

Reference for Step 4 of the distillation workflow. Concrete examples of how to
translate external practices into the agent's native mechanisms.

> **How to use this file:** Each pattern has a universal structure:
> `[external practice] → [trigger] + [action on current platform]`.
> The *trigger* is portable; the *action* names specific tools. If running on
> a different platform, keep the trigger, swap the tool names.
> WorkBuddy tool reference: `~/.workbuddy/MEMORY.md` (cross-project memory),
> workspace `memory/MEMORY.md` (project memory), `conversation_search` (history),
> `TaskCreate` (task tracking), `SkillManage` (skill CRUD), `present_files`
> (result delivery), `show_widget` (inline visuals), `Bash` (command execution).

## Pattern 1: Periodic Audit → Trigger-Based Maintenance

External: "Every 7 days, generate a knowledge audit report."

WorkBuddy cannot run cron jobs internally, but can define triggers:

```
Trigger: MEMORY.md exceeds 3/4 character limit
Action:  Read full file → identify duplicates → merge entries
         → archive low-frequency items → rewrite concisely
         → preserve within character budget

Trigger: Skill count exceeds 15
Action:  List all skills → identify overlapping responsibilities
         → merge umbrella skills → archive obsolete ones

Trigger: Same error type appears 2+ times
Action:  Promote from memory note to skill or strengthen MEMORY entry

Trigger: Daily log older than 30 days
Action:  Distill topics into workspace MEMORY.md → delete raw file
```

## Pattern 2: Document-Driven Recovery → Memory-Driven Recovery

External: "New session reads 5-6 documents to restore context."

WorkBuddy translation (lighter, faster):

```
1. Read workspace memory/MEMORY.md    → project-level long-term
2. Read recent 1-2 daily logs          → current state
3. If insufficient → conversation_search → historical context
4. If code involved → Glob + Read      → project structure
5. Check TaskList                      → pending tasks
6. Before acting → state "what to do now, where we stopped"
```

Key difference: WorkBuddy's recovery is query-based (search memory) rather than
read-based (read all docs). This is lighter but requires *proactive* memory
maintenance to ensure the right things were written.

## Pattern 3: Mandatory Verification → Behavioral Reflex

External: "Completion requires running actual verification matching product type."

WorkBuddy translation:

```
BEFORE claiming any task complete:
  Code    → Bash: run build + test suite
  Web     → present_files preview + browser screenshot
  Data    → Script: run assertions on output
  Config  → Parse validation (json.loads, toml.load, yaml.safe_load)
  Document → Check references valid, paths exist

BANNED phrases in completion claims:
  "should work" / "theoretically" / "probably" / "I believe"

IF cannot verify:
  State: what was checked, what was NOT verified, what risks remain
  Do NOT claim completion without this disclosure
```

## Pattern 4: Error Compounding → Immediate Sedimentation

External: "Error → write to knowledge base → promote to summary if high-frequency."

WorkBuddy translation:

```
After fixing any non-trivial error, immediately ask:
  Q: Will this trap recur in other projects?
    YES (general) → Write to ~/.workbuddy/MEMORY.md with keywords
    YES (domain)  → Update or create a skill
    NO (project)  → Write to workspace memory/YYYY-MM-DD.md

Memory entry format (not activity log):
  ✗ BAD: "Fixed a path bug"
  ✓ GOOD: "Windows bash paths need /c/ prefix, not C:\\ — check before passing to bash commands"
         + keywords: "windows, bash, path"

The keyword line enables conversation_search to find it later.
```

## Pattern 5: Skill Routing Discipline → Minimal Loading

External: "Simple tasks load 0-1 skills, complex tasks load 2-3 in phases."

WorkBuddy translation:

```
Before loading any skill, assess complexity:
  Trivial (Q&A, single edit, lookup)        → 0 skills
  Simple (one domain, low risk)             → 0-1 skill
  Medium (clear scope, moderate change)     → 1-2 skills
  Complex (cross-file, needs verification)  → 2-3 skills
  Long-term (multi-phase project)           → load per phase, not upfront

If loading a skill, justify briefly why.
If skipping a relevant skill, justify briefly why it's unnecessary.

Anti-pattern: loading 5 skills "just in case" → context pollution.
Anti-pattern: skipping browser verification for web changes → no evidence.
```

## Pattern 6: Honest Three-Way Classification

The most common failure mode is classifying everything as "can absorb" out of
politeness or thoroughness. Use these tests:

```
"Already have" test:
  Does WorkBuddy have ANY mechanism that solves the same problem?
  Even if implemented differently? → "Already have"

"Not applicable" test:
  Does the external practice exist ONLY because of a constraint WorkBuddy
  doesn't share? (e.g., no cloud memory, no search, no multimodal)
  → "Not applicable"

"Can absorb" test:
  Is there a behavioral discipline (not a mechanism) that WorkBuddy
  executes weakly or inconsistently?
  → "Can absorb" (this is the only actionable category)
```
