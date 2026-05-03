# lean-code-edits

English | [简体中文](README.zh-CN.md)

`lean-code-edits` is a lightweight Codex skill for reducing common LLM coding mistakes in day-to-day development work.

It is built around a simple stance: most bad coding-agent outcomes come from behavioral drift, not lack of raw capability. In practice, that usually means overcomplication, speculative flexibility, broad refactors, or verification that is far heavier than the task requires.

This skill is inspired by [andrej-karpathy-skills](https://github.com/forrestchang/andrej-karpathy-skills) and then lightly tailored for this workspace.

This skill keeps the agent focused on four things:

1. Surface only material uncertainty.
2. Write the minimum code that solves the request.
3. Make surgical, requirement-traceable changes.
4. Use the smallest verification that matches the task.

## What It Includes

- `AGENTS.md`: the canonical behavioral policy.
- `SKILL.md`: the skill trigger and usage instructions for Codex.
- `README.md`: the human-facing overview.

## What Problems It Solves

- Agents adding features that were never requested.
- Agents introducing abstractions for one-off code.
- Agents "cleaning up" surrounding code that should have been left alone.
- Agents turning simple edits into heavyweight testing or validation workflows.
- Agents asking unnecessary clarification questions when a safe, reasonable assumption would do.

## Best Fit

`lean-code-edits` works best for small to medium coding tasks where discipline matters more than breadth:

- bug fixes
- focused feature edits
- narrow refactors
- code review follow-up changes
- routine repository maintenance

It is especially useful when you want smaller diffs, less speculative code, and less ceremony around simple tasks.

## Design Philosophy

This skill is intentionally opinionated:

- It favors caution over speed, but not overthinking over progress.
- It treats simplicity and scope control as first-class quality signals.
- It keeps verification proportional to task risk.
- It assumes project-specific instructions override it when conflicts exist.

## How To Use

Use this folder as a Codex skill, or merge the contents of `AGENTS.md` into a repository's own agent instructions.

If you use it as a skill, the intended flow is:

1. Trigger the skill for coding, review, refactor, or maintenance tasks.
2. Read `AGENTS.md` as the source of truth.
3. Apply the four principles without adding extra process unless the task clearly requires it.

## Non-Goals

This skill is not optimized for:

- greenfield architecture work that genuinely needs wider design exploration
- research-heavy tasks where broad comparison matters more than edit discipline
- high-risk changes that need stronger validation than this default profile

In those cases, treat `lean-code-edits` as a baseline guardrail set, not a complete operating model.
