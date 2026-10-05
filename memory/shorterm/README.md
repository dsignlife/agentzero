# Short-term memory

Use this folder for active task context that another session or agent needs to continue the work. Follow the shared [memory guidance](../README.md).

Create a task note for work spanning sessions or requiring a handoff. Read it before resuming that task. Update it after a meaningful decision, change in status, or handoff; keep the current state instead of a running conversation log.

Use a filename such as `<task-id>.md` and include:

```markdown
# Task title

- Goal:
- Constraints:
- Owner:
- Status: active / blocked / complete
- Last updated: YYYY-MM-DD

## Current state
Verified findings, decisions, and remaining uncertainties.

## Artifacts
Links to relevant files, outputs, and supporting sources.

## Next action
The concrete next step and any unresolved blocker.
```

When work finishes, move useful project decisions to [longterm/](../longterm/README.md) and verified reusable lessons to [learnings/](../learnings/README.md). Remove resolved scratch details. Retain only the completion context needed for a handoff; remove obsolete task notes when no longer useful.
