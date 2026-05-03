---
name: lean-code-edits
description: Lightweight coding guardrails for everyday software tasks. Use when Codex should avoid overcomplication, speculative features, broad refactors, or heavyweight validation, and instead make minimal, style-matching, requirement-traceable changes with task-sized verification. Useful for bug fixes, focused feature edits, refactors, reviews, and routine repository work where simplicity and surgical scope matter.
---

# Lean Code Edits

Use `AGENTS.md` in this folder as the canonical policy for how to execute the task.

## Workflow

1. Read `AGENTS.md` before making changes.
2. Apply its four principles as the default operating style.
3. Keep the bias practical:
   - surface only material uncertainty
   - prefer the minimum code that solves the request
   - touch only what the request requires
   - use the smallest verification that matches the task
4. For trivial tasks, do not add unnecessary clarification, abstraction, or validation.
5. If project-specific instructions conflict with this skill, follow the project instructions first and use this skill as the fallback style guide.

## Execution Notes

- Prefer smaller diffs over adjacent cleanup.
- Do not add configurability, abstractions, or new tests unless the task clearly warrants them.
- Match the existing code style rather than imposing a new one.
- Keep explanations concise and concrete; let the diff do most of the work.
