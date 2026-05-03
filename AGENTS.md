# AGENT.md

Behavioral guidelines to reduce common LLM coding mistakes. Use alongside project-specific instructions as needed.

**Tradeoff:** These guidelines favor caution over speed. For trivial tasks, use judgment.

## 1. Think Before Coding

**Surface only material uncertainty.**

- If ambiguity changes behavior or user-visible outcome, say so briefly and ask.
- If multiple interpretations materially differ, name the tradeoff and choose the safest reasonable one if you must proceed.
- Push back when the request is overcomplicated or conflicts with the codebase.
- Otherwise, proceed with the most reasonable assumption and keep moving.

## 2. Simplicity First

**Minimum code that solves the problem. Nothing speculative.**

- No features beyond what was asked.
- No abstractions for single-use code.
- No "flexibility" or "configurability" that wasn't requested.
- No error handling for impossible scenarios.
- If you write 200 lines and it could be 50, rewrite it.

Sanity check: would a senior engineer call this overcomplicated? If yes, simplify.

## 3. Surgical Changes

**Touch only what you must. Clean up only your own mess.**

When editing existing code:
- Don't "improve" adjacent code, comments, or formatting.
- Don't refactor things that aren't broken.
- Match existing style, even if you'd do it differently.
- If you notice unrelated dead code, mention it - don't delete it.

When your changes create orphans:
- Remove imports/variables/functions that YOUR changes made unused.
- Don't remove pre-existing dead code unless asked.

Sanity check: every changed line should trace directly to the user's request.

## 4. Goal-Driven Execution

**Use the smallest verification that matches the task.**

Turn the task into a practical finish line:
- For simple edits, do a light check: formatting, lint, compile, smoke test, or manual spot-check.
- For bug fixes or riskier changes, verify the specific failure mode.
- Only add new tests when the task or risk clearly warrants them.
- Do not create extra test files or heavyweight validation unless asked.
- If the goal is already satisfied, stop; do not loop for the sake of looping.

For multi-step tasks, keep a brief plan and verify the essential outcome at each step:
```
1. [Step] -> verify: [minimal check]
2. [Step] -> verify: [minimal check]
3. [Step] -> verify: [minimal check]
```
---

**These guidelines are working if:** diffs stay small, overcomplication-driven rewrites are rarer, and clarifying questions happen before implementation rather than after mistakes.
