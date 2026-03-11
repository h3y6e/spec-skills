---
name: spec-constitution
description: Create or update specs/constitution.md — the foundational rules file for spec-driven development, defining project-wide coding standards, naming conventions, quality thresholds, security requirements, and workflow language. Use this skill whenever someone wants to set up project rules, initialize a spec-skills workflow for a new project, update shared conventions, change the workflow language, or asks what to do first in spec-driven development. This is step 1 of 5 — always recommend it before spec-specify, spec-plan, spec-tasks, or spec-implement.
license: MIT
metadata:
  author: h3y6e
  version: "0.2.0"
---

# Constitution Skill

## Purpose

Create or update `specs/constitution.md` and confirm shared rules for spec-skills.

## Input

- User-provided project rules (via prompt or conversation)
- Existing `specs/constitution.md` when present

## Output

- `specs/constitution.md`

## Steps

1. Determine `language`.
   - Use the existing `specs/constitution.md` frontmatter value if present
   - Otherwise infer from the user's prompt language
   - Conduct all subsequent interaction in this language
2. Read `specs/constitution.md`; if missing, initialize from `references/constitution-template.md`.
3. Keep the document structure aligned with `references/constitution-template.md`.
   - Do not invent additional top-level sections unless the user explicitly requests them
4. Update Core Principles based on user-provided rules.
   - Ask the user if no rules were provided
   - Keep only stable, project-wide principles here
5. Add variable project rules only when the user specifies them.
   - Fold them into existing principles when possible
6. Update frontmatter.
   - Required keys: `language`, `summary`
7. If updating an existing constitution, verify consistency with existing feature documents.
   - Check `specs/{feature}/spec.md`, `plan.md`, `tasks.md`
   - Skip this step when no feature documents exist
8. Perform final review and keep the file within 150 lines.
   - Remove repetition
   - Simplify wording
   - Resolve contradictions
9. In the completion message, suggest the next step.
   - New feature: `spec-specify`
   - Existing feature update: `spec-specify` for the target `spec.md`

## Success Criteria

- Constitution reflects current shared rules.
- Frontmatter values are valid and complete.
- Related feature documents stay consistent.

## Completion Guidance

- Next recommended step: `spec-specify`
- Include the target feature and next file path in the response
