---
status: draft
summary: Phase-based tasks for [FEATURE_NAME]
---

Place this file at `specs/{feature}/tasks.md`.

## Format

- `- [ ] Txxx (P) [USn] [DESCRIPTION] ([PATH])`
- `(P)` marks a parallelizable task
- `[USn]` links the task to a user story

## Phase 1: Setup

- [ ] T001 [SETUP_TASK]
- [ ] T002 (P) [SETUP_TASK]

### DoD

- [ ] [DOD_CHECK]
- [ ] [DOD_CHECK]

## Phase 2: Foundational

- [ ] T003 [FOUNDATIONAL_TASK]
- [ ] T004 (P) [FOUNDATIONAL_TASK]

### DoD

- [ ] [DOD_CHECK]
- [ ] [DOD_CHECK]

## Phase [N]: User Story [N] (Priority: P[N])

Goal: [STORY_GOAL]
Independent Test: [STORY_INDEPENDENT_TEST]

- [ ] T0xx [USn] [IMPLEMENTATION_TASK]
- [ ] T0xx (P) [USn] [IMPLEMENTATION_TASK]

### DoD

- [ ] [DOD_CHECK]
- [ ] [DOD_CHECK]

[Add as many user story phases as needed]

## Phase N: Polish

- [ ] T0xx [POLISH_TASK]

### DoD

- [ ] [DOD_CHECK]
- [ ] [DOD_CHECK]
