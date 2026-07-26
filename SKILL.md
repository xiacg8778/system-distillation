---
name: system-distillation
description: "Analyze an external system, workspace, framework, or methodology to extract transferable disciplines, mechanisms, and design patterns that WorkBuddy itself can absorb for self-improvement. Triggered when the user asks to learn from, absorb, or evolve from an external system, workspace, repo, article, or methodology. Also triggered by reflection questions like 'can you learn and improve from this' after analyzing something. This skill produces a structured distillation of what to absorb, what already exists, and what to skip, plus an executable evolution blueprint, and immediately writes the absorbed disciplines into long-term memory."
agent_created: true
---

# System Distillation

## Overview

This skill transforms the analysis of any well-designed external system into
actionable self-improvement. Instead of merely summarizing what a system does,
it extracts the disciplines and mechanisms worth absorbing, maps them to
WorkBuddy's own capabilities, identifies gaps, and produces a concrete evolution
blueprint that is immediately executed — not just documented.

## When to Use

- User asks to "learn from" or "absorb the strengths of" an external system
- User asks "can you improve yourself from this" after reviewing a workspace/repo/article
- User provides a well-structured framework, SOP, or governance system to study
- User wants to compare an external methodology against WorkBuddy's own practices
- Reflection prompts after deep analysis work ("what can you take away from this")

## When NOT to Use

- User only wants a factual summary of a system (no self-improvement angle)
- User wants to copy or replicate a system verbatim (not distill lessons)
- User asks to build or modify the external system itself
- Simple lookups or one-line questions about a system

## Core Principle

**Do not copy the form. Absorb the spirit.**

Most external systems solve problems that WorkBuddy already handles differently
(e.g., context recovery via documents vs. via cloud memory). The goal is not to
replicate their documents or structures, but to extract the behavioral disciplines
and decision rules that make them effective — then internalize those into
WorkBuddy's own memory and skill systems.

## Workflow

### Step 1: Understand the Target System

Read the external system's entry-point documents in order, avoiding full loads:

1. Entry/rules file (AGENTS.md, README.md, CONTRIBUTING.md, etc.)
2. Index or manifest (project index, table of contents, directory listing)
3. Condition-specific documents (only those relevant to the user's question)

For code repos: read README + docs/ + key config files.
For methodologies: read the core document + examples.
For workspaces: read governance docs + project index.

### Step 2: Extract Mechanisms (Not Features)

For each notable practice, ask: *what problem does this solve, and what is the
underlying mechanism?*

Common mechanism categories:

| Category | Example |
|---|---|
| Context recovery | Layered document loading, conditional reading |
| Experience compounding | Error → knowledge base → summary promotion |
| Quality enforcement | Mandatory verification before completion |
| Skill/resource routing | Minimal necessary loading by scenario |
| Knowledge maintenance | Periodic self-audit, merge, archive |
| Isolation & numbering | Project separation, ID non-reuse |

### Step 3: Three-Way Classification

Map each extracted mechanism into exactly one of three buckets:

**Already have (green):** WorkBuddy has an equivalent or stronger native mechanism.
Record the mapping but do not act.

**Can absorb (amber/coral):** WorkBuddy lacks this discipline or executes it weakly.
This is the actionable set — proceed to Step 4.

**Not applicable (gray):** The mechanism relies on constraints WorkBuddy doesn't
have (e.g., "session amnesia" that necessitates document-driven recovery).
Skip these, but note why.

### Step 4: Translate to Executable Actions

For each "can absorb" mechanism, produce a translation:

```
External practice → WorkBuddy execution
─────────────────────────────────────────
"7-day knowledge audit"
  → Trigger: MEMORY.md exceeds 3/4 capacity
  → Action: distill duplicates, archive stale, promote high-frequency items

"Completion verification required"
  → Trigger: before claiming any task done
  → Action: run build/test for code, present_files for web, assertions for data
  → Banned phrases: "should work", "theoretically", "probably"
```

Each translation must specify: **trigger condition** and **concrete action**.

### Step 5: Produce Evolution Blueprint

Structure the output as a phased plan:

- **Phase 0 — Existing base:** what WorkBuddy already has (no action)
- **Phase 1 — Quick wins:** behavioral habits, immediately executable
- **Phase 2 — Structural evolution:** mechanism-level changes, medium term
- **Phase 3 — Deep discipline:** long-term self-governance habits

### Step 6: Execute Immediately (Critical)

Do not just write the blueprint. Immediately:

1. Write absorbed disciplines into `~/.workbuddy/MEMORY.md` (cross-project)
2. Write project-specific lessons into workspace `memory/MEMORY.md`
3. Append a "reusable judgment" line to today's work log

The blueprint document is a reference; the memory writes are the actual
internalization. A blueprint that is only written but not internalized into
memory is a failure of this skill.

### Step 7: Present and Verify

- Present the blueprint via `present_files`
- Use `show_widget` for the three-way classification visual
- State explicitly what was written into memory (not just "done")

## Output Format

### Visual (show_widget)

Use an SVG diagram showing the three-way classification:
- Left column: external system's mechanisms
- Right column: WorkBuddy's current state
- Color coding: green (already have), amber/coral (can absorb), gray (N/A)

### Document (present_files)

Markdown file with:
- Core principle statement
- Phase 0-3 breakdown with numbered actions
- Three-way mapping table
- Evolution target comparison table

### Memory Writes

Disciplines written to `~/.workbuddy/MEMORY.md` as behavioral rules with
trigger conditions, not as descriptions.

## Common Mistakes

- **Copying form instead of spirit:** Replicating document structures that
  WorkBuddy doesn't need because it has native memory/retrieval. Always ask:
  "does WorkBuddy already solve this problem a different way?"

- **Writing blueprint without internalizing:** Producing a nice document but
  not writing disciplines into memory. The memory write IS the absorption.

- **Vague actions:** "Be more careful" is not an executable action. Every
  absorbed discipline needs a trigger condition and a concrete action.

- **Treating everything as absorbable:** Many external practices exist because
  of constraints WorkBuddy doesn't share. Classify honestly — "already have"
  and "not applicable" are valid and common outcomes.

- **No immediate execution:** The user asked to evolve, not to plan to evolve.
  Phase 1 actions should start in the same turn.

## Verification

Before claiming this skill is applied:

- [ ] Three-way classification table produced with honest assessments
- [ ] At least one discipline written into long-term memory
- [ ] Blueprint document created and presented
- [ ] Phase 1 actions stated as already-starting, not future-tense
- [ ] No banned verification phrases used ("should", "theoretically")
