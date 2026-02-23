---
language: en
summary: Shared rules used during spec-skills runs
---

# spec-skills Constitution

## Core Principles

### I. Lightweight by default
spec-skills prioritizes lightweight execution. Keep artifacts and process minimal so small changes remain practical.

### II. Agent and tool neutrality
Use instructions that work across agents. Treat Git operations (branch/worktree) as optional and compatible with user workflow choices.

### III. Specs as the source of truth
The source of truth for requirements is `specs/{feature}/spec.md`. If planning discovers requirement-impacting changes, `plan` may update `spec.md` and must reset status to `draft`.

### IV. Design and execution planning are separate
Keep `plan` and `tasks` separate. `plan` handles technical design and annotation updates; `tasks` handles executable breakdown. Ambiguity resolution is handled inside `specify`.

### V. Verification-first implementation
`implement` follows `implement -> self-validate -> fix` loops. Human escalation is exception-based; routine issues are resolved in the automated validation loop.

### VI. Context efficiency over document volume
Generated and distributed Markdown should stay within 150 lines when possible; split when needed. At the end, run a final review to deduplicate, simplify, and resolve contradictions.

This constitution is used to record project-specific shared rules that may change over time.
