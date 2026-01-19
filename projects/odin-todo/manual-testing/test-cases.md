# Odin Todo — Manual Test Cases

## Scope

Core CRUD + state transitions: add, complete, edit, delete/clear, filter, search, sort.

---

## Add Task

### TC-TODO-001 — Add a task via button

**Preconditions:** App loaded, list visible.

**Steps:**

1. Type "Buy milk" in task input.
2. Click Add / Submit.

**Expected:**

- New task appears in the list.
- Task text is exactly "Buy milk".
- Input clears.

### TC-TODO-002 — Add a task via Enter key

**Steps:**

1. Type "Walk dog".
2. Press Enter.

**Expected:** Task is added as in TC-TODO-001.

### TC-TODO-003 — Reject empty task

**Steps:**

1. Ensure input is empty.
2. Click Add / press Enter.

**Expected:**

- No task is added.

### TC-TODO-004 — Reject whitespace-only task

**Steps:**

1. Type " " (spaces).
2. Submit.

**Expected:**

- No task added.

### TC-TODO-005 — Trim leading/trailing spaces

**Steps:**

1. Type " Pay bills "
2. Submit.

**Expected:**

- Task text saved as "Pay bills".

---

## Complete / Toggle

### TC-TODO-006 — Mark task as completed

**Preconditions:** At least one task exists.

**Steps:**

1. Toggle completion checkbox on a task.

**Expected:**

- Task shows completed styling/state.
- Completed count updates.

### TC-TODO-007 — Un-complete a completed task

**Steps:**

1. Toggle the same task again.

**Expected:**

- Task returns to active state.
- Counts update correctly.

### TC-TODO-008 — Edit task text successfully

**Preconditions:** Task exists.

**Steps:**

1. Trigger edit (edit button / double click / prompt).
2. Change text to "Buy oat milk".
3. Save/confirm.

**Expected:**

- Task text updates.
- Completion state unchanged.

### TC-TODO-009 — Cancel edit leaves text unchanged

**Steps:**

1. Start edit.
2. Cancel (Esc / Cancel button / close prompt).

**Expected:** Original text remains.

### TC-TODO-010 — Reject edit to empty/whitespace

**Steps:**

1. Start edit.
2. Replace text with empty / spaces.
3. Save.

**Expected:**

- Edit rejected and original text remains.

---

## Delete / Clear

### TC-TODO-011 — Delete a single task

**Preconditions:** Task exists.

**Steps:**

1. Click delete/remove on one task.

**Expected:**

- Task disappears.
- Counts update.

### TC-TODO-012 — Clear completed removes only completed tasks

**Preconditions:** One completed, one active.

**Steps:**

1. Click “Clear completed”.

**Expected:**

- Completed tasks removed.
- Active tasks remain.

### TC-TODO-013 — Clear all removes all tasks

**Preconditions:** Multiple tasks exist.

**Steps:**

1. Click “Clear all”.

**Expected:** List is empty.

---

## Filter

### TC-TODO-014 — Filter: Active shows only active tasks

**Preconditions:** One active + one completed.

**Steps:**

1. Set filter to Active.

**Expected:** Only active tasks shown.

### TC-TODO-015 — Filter: Completed shows only completed tasks

**Steps:**

1. Set filter to Completed.

**Expected:** Only completed tasks shown.

### TC-TODO-016 — Filter: All shows all tasks

**Steps:**

1. Set filter to All.

**Expected:** Both active and completed shown.

---

## Search

### TC-TODO-017 — Search is case-insensitive and partial match

**Preconditions:** Tasks: "Buy milk", "Walk dog".

**Steps:**

1. Search "MIL".

**Expected:** "Buy milk" is shown.

### TC-TODO-018 — Empty search shows full list

**Steps:**

1. Clear search input.

**Expected:** Full list returns.

---

## Sort

### TC-TODO-019 — Sort by created date

**Preconditions:** Two tasks created in order.

**Steps:**

1. Set sort to “created asc/desc” (or your equivalent).

**Expected:** Ordering changes correctly and consistently.

## Test Run Summary — Odin Todo (Manual UI)

- **Date:** 2026-01-19

- **Environment:** macOS 15.7.3 (24G419), MacBook Pro (arm64)

- **Browser:** Chrome 144.0.7559.60 (Official Build) (arm64)

- **Scope:** Manual UI test execution for Odin Todo app.

- **Out of Scope:** Backend tests, performance/load testing, accessibility audit, cross-browser testing.

- **Total Test Cases:** 19

- **Passed:** 19

- **Failed:** 0

- **Notes:** No defects found during this test run.
