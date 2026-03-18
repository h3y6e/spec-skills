---
name: spec-tasks
description: Create or update specs/{feature}/tasks.md by decomposing spec and plan into phased, executable tasks with IDs (T001...), parallel candidates (P), story linkage, and Definition of Done per phase. Use this skill whenever someone wants to break a plan into concrete implementation tasks, create a structured task checklist for a feature, add DoD to task phases, or create/update tasks.md. This follows spec-plan and precedes spec-implement in the spec-driven workflow. Don't use for general to-do lists or project management outside the spec workflow.
license: MIT
metadata:
  author: h3y6e
  version: "0.2.0"
---

# Tasks Skill

## Purpose

Create or update `specs/{feature}/tasks.md` and define execution order plus completion conditions.

## Input

- Existing `specs/constitution.md` when present
- `specs/{feature}/spec.md`
- `specs/{feature}/plan.md`
- `specs/{feature}/research/*.md` when present

## Output

- `specs/{feature}/tasks.md`
- `specs/{feature}/spec.md` when backflow is required

## Steps

1. Resolve `language` and shared rules from `specs/constitution.md` when present; otherwise infer from the available workflow documents and the user's own message. Ask only if still unclear, then conduct all subsequent interaction in this language.
2. Read spec and plan, extract user stories and constraints, and confirm plan/tasks approval state.
   - Require `spec.md` and `plan.md` to be `approved` before generating implementation tasks
3. Create tasks from `references/tasks-template.md`.
   - Setup
   - Foundational
   - User Story (P1, P2, ...)
   - Polish
4. Standardize the task format.
   - `- [ ] Txxx ...`
   - Use `(P)` for parallel candidates
   - Use `[USn]` for story linkage
5. Add `DoD` under each phase.
   - Include checks for testing, observability, and rollback readiness
   - Write DoD as proof that the phase itself is complete
6. Express dependencies through phase order and task descriptions.
7. Run backflow if requirement gaps or contradictions are discovered.
   - Update `spec.md`
   - Reset `spec.md` status to `draft`
8. Update frontmatter.
   - Required keys: `status`, `summary`
   - Initial `status`: `draft`
   - Set `status: approved` when tasks are ready for implementation
9. Perform final review and keep the file within 150 lines.
   - Remove repetition
   - Simplify wording
   - Resolve contradictions
10. In the completion message, suggest the next step.
    - After approval: `spec-implement`
    - If requirement changes are needed: `spec-plan` or `spec-specify`

## Success Criteria

- Tasks support independent delivery by story.
- Each phase has a clear DoD.
- `(P)` marks valid parallel work.
- Backflow handling is explicit.

## Completion Guidance

- Next recommended step: `spec-implement`
- Include the target feature and generated `tasks.md` path in the response
