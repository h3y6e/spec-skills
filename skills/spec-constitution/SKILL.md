---
name: spec-constitution
description: Define shared project rules for spec-skills runs
license: MIT
metadata:
  author: h3y6e
  version: "0.2.1"
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
3. Update Core Principles based on user-provided rules.
   - Ask the user if no rules were provided
4. Add variable project rules only when the user specifies them.
   - Naming rules
   - Quality thresholds
   - Security requirements
5. Update frontmatter.
   - Required keys: `language`, `summary`
6. If updating an existing constitution, verify consistency with existing feature documents.
   - Check `specs/{feature}/spec.md`, `plan.md`, `tasks.md`
   - Skip this step when no feature documents exist
7. Perform final review and keep the file within 150 lines.
   - Remove repetition
   - Simplify wording
   - Resolve contradictions
8. In the completion message, suggest the next step.
   - New feature: `spec-specify`
   - Existing feature update: `spec-specify` for the target `spec.md`

## Success Criteria

- Constitution reflects current shared rules.
- Frontmatter values are valid and complete.
- Related feature documents stay consistent.

## Completion Guidance

- Next recommended step: `spec-specify`
- Include the target feature and next file path in the response
