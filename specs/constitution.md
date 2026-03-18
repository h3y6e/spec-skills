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
The source of truth for requirements is `specs/{feature}/spec.md`. If execution design or implementation discovers requirement-impacting changes, `spec.md` must be updated and reset to `draft` before implementation continues.

### IV. Execution design lives with tasks
Keep execution-facing design, task breakdown, and progress together in `specs/{feature}/tasks.md` so backflow updates do not need a second execution document. Ambiguity resolution is handled inside `spec-specify`.

### V. Verification-first implementation
`spec-implement` follows `implement -> self-validate -> fix` loops. Human escalation is exception-based; routine issues are resolved in the automated validation loop.

### VI. Context efficiency over document volume
Generated and distributed Markdown should stay within 150 lines when possible; split when needed. At the end, run a final review to deduplicate, simplify, and resolve contradictions.

This constitution is used to record stable rules that spec-skills should apply during their workflow. It is not a replacement for the repository's general engineering handbook. Feature scope belongs in `spec.md`; execution design, sequencing, and validation strategy belong in `tasks.md` unless intentionally promoted to a permanent shared rule for spec-skills runs.
