---
name: spec-plan
description: Create a technical plan and manage annotation-driven updates
license: MIT
metadata:
  author: h3y6e
  version: "0.2.1"
---

# Plan Skill

## Purpose

Create or update `specs/{feature}/plan.md` and define technical design plus execution readiness.

## Input

- `specs/constitution.md`
- `specs/{feature}/spec.md`
- `specs/{feature}/research/*.md` when present
- Plan annotations when present

## Output

- `specs/{feature}/plan.md`
- `specs/{feature}/research/{topic}.md` for additional research
- `specs/{feature}/spec.md` when spec-impacting discoveries occur

## Steps

1. Read `specs/constitution.md`, resolve `language`, and apply shared rules. Conduct all subsequent interaction in this language.
2. Read `spec.md` and extract requirements and acceptance criteria.
3. Create or update `research/{topic}.md` when additional research is required.
4. Create the plan from `references/plan-template.md`.
5. Run the annotation cycle.
   - Draft the initial plan
   - Apply annotation feedback
   - Repeat until approval
6. Run backflow when design discoveries affect requirements.
   - Update `spec.md`
   - Reset `spec.md` status to `draft`
7. Update frontmatter.
   - Required keys: `status`, `summary`
8. Perform final review and keep the file within 150 lines.
   - Remove repetition
   - Simplify wording
   - Resolve contradictions
9. In the completion message, suggest the next step.
   - After approval: `spec-tasks`
   - If annotation work remains: continue `spec-plan`

## Success Criteria

- Plan decisions align with the spec.
- Backflow conditions and actions are explicit.
- Implementation starts only after plan and tasks approval.

## Completion Guidance

- Next recommended step: `spec-tasks`
- Include the target feature and generated `plan.md` path in the response
