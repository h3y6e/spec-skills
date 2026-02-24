---
name: spec-implement
description: Execute tasks and maintain quality through a self-validation loop
license: MIT
metadata:
  author: h3y6e
  version: "0.2.0"
---

# Implement Skill

## Purpose

Implement using `specs/{feature}/tasks.md` as the single progress source.

## Input

- `specs/constitution.md`
- `specs/{feature}/spec.md`
- `specs/{feature}/plan.md`
- `specs/{feature}/tasks.md`

## Output

- Implemented code
- Progress updates in `specs/{feature}/tasks.md`
- `specs/{feature}/research/{topic}.md` when validation notes are needed

## Steps

1. Read `specs/constitution.md`, resolve `language`, and apply shared rules. Conduct all subsequent interaction in this language.
2. Confirm plan/tasks approval state.
3. Process open tasks from top to bottom.
4. Run an implementation loop for each task.
   - Implement
   - Self-validate (tests, type checks, static checks, security checks)
   - Fix
5. Update `tasks.md` after each successful task.
   - Mark the task as complete
   - Update `status` to `in-progress` or `done` when appropriate
   - Record progress in this format
     - Task: [TASK_ID]
     - Change: [CHANGE_SUMMARY]
     - Validation: [PASS_FAIL_AND_EVIDENCE]
     - Next: [NEXT_TASK]
6. Escalate only exception cases.
   - Conflicting requirements
   - High-risk changes
   - Validation failures that cannot be resolved in-loop
7. Run backflow when implementation findings affect requirements.
   - Update `spec.md`
   - Reset `spec.md` status to `draft`
8. Confirm DoD completion and place outputs in the repository structure.
9. If documents are updated, perform final review and keep them within 150 lines.
   - Remove repetition
   - Simplify wording
   - Resolve contradictions
10. In the completion message, suggest the next step.
   - If open tasks remain: continue `spec-implement`
   - If all tasks are complete: final completion report

## Success Criteria

- `tasks.md` progress matches actual implementation state.
- Phase DoD items are satisfied.
- Non-exception issues are resolved inside the self-validation loop.

## Completion Guidance

- Next recommended step: continue `spec-implement` or close implementation
- Include completed tasks, remaining tasks, and the next task in the response
