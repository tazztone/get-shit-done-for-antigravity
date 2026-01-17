# SUMMARY.md Template

> Copy this template when documenting completed plan execution.

```markdown
---
phase: {N}
plan: {M}
completed_at: {YYYY-MM-DD HH:MM}
duration_minutes: {X}
tasks_completed: {Y}
---

# Summary: Plan {N}.{M} — {Plan Name}

## Outcome
**Status:** ✅ Complete

## Completed Tasks

### 1. {Task 1 Name}
- **Files:** `{file1}`, `{file2}`
- **What was done:** {Brief description}
- **Verification:** PASS — {evidence}

### 2. {Task 2 Name}
- **Files:** `{file1}`
- **What was done:** {Brief description}
- **Verification:** PASS — {evidence}

## Files Changed

| File | Change |
|------|--------|
| `{path/to/file1}` | {Created | Modified | Deleted} — {what changed} |
| `{path/to/file2}` | {Created | Modified | Deleted} — {what changed} |

## Commits

| Hash | Message |
|------|---------|
| `{abc123}` | feat(phase-{N}): {task 1} |
| `{def456}` | feat(phase-{N}): {task 2} |

## Deviations from Plan
{Any differences between plan and actual execution}
- None

OR

- {Deviation 1}: {Why and what was done instead}

## Issues Encountered
{Problems hit during execution}
- None

OR

- {Issue 1}: {How it was resolved}

## Notes for Future Reference
{Anything useful to know}
- {Note 1}
- {Note 2}
```

## Frontmatter Purpose

The frontmatter enables automated processing:

```yaml
phase: 1          # Links to correct phase
plan: 2           # Identifies specific plan
completed_at: ... # Timestamp for history
duration_minutes: # Execution time tracking
tasks_completed:  # Success metrics
```

This allows building dependency graphs and tracking progress programmatically.
