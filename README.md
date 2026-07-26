# system-distillation

A [WorkBuddy](https://www.codebuddy.cn/) skill for **learning from external systems**.

## What it does

When you ask WorkBuddy to "learn from", "absorb", or "evolve from" an external system (a workspace, repo, framework, or methodology), this skill activates.

Instead of just summarizing what the system does, it:

1. **Extracts mechanisms** - the underlying disciplines, not surface features
2. **Three-way classifies** each one:
   - **Already have** - WorkBuddy solves this natively, no action needed
   - **Can absorb** - a behavioral discipline worth internalizing
   - **Not applicable** - exists only due to constraints WorkBuddy does not share
3. **Translates** absorbable items into executable actions with trigger conditions
4. **Produces an evolution blueprint** (Phase 0-3)
5. **Immediately internalizes** the disciplines into long-term memory

## Core Principle

> **Do not copy the form. Absorb the spirit.**

Most external systems build elaborate structures (documents, indexes, routing tables) to compensate for limitations that AI assistants like WorkBuddy do not have (session amnesia, no search, no multimodal). The goal is to extract the *behavioral discipline* - not to replicate the scaffolding.

## Origin

This skill was distilled from analyzing a multi-project AI agent workspace (CodexWrokspace) with a sophisticated governance system including layered document loading, experience compounding, mandatory verification, and scenario-based skill routing.

## Structure

```
system-distillation/
+- SKILL.md                          # Core 7-step workflow
+- references/
   +- mechanism-catalog.md          # Common mechanism patterns + WorkBuddy equivalents
   +- translation-patterns.md       # 6 patterns for external -> native translation
```

## The 7-Step Workflow

| Step | Action |
|------|--------|
| 1 | Understand the target system (read entry -> index -> conditional docs) |
| 2 | Extract mechanisms (not features) |
| 3 | Three-way classify: already have / can absorb / not applicable |
| 4 | Translate absorbable items to executable actions (trigger + action) |
| 5 | Produce phased evolution blueprint (Phase 0-3) |
| 6 | **Execute immediately** - write disciplines into long-term memory |
| 7 | Present and verify (show_widget + present_files) |

## License

MIT
