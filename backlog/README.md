# Task backlog

Each backlog task is a folder whose `task.md` is the prompt. Every time the Director works the task, it creates the next `iterationN/` folder holding that run's brief, specialist return, review, and `taskstate.json`. Task folders are local and ignored by Git; only this README and [_template/](_template/) are tracked.

## Layout

```text
backlog/
  <task-id>/
    task.md                 prompt: goal, inputs, constraints, acceptance criteria
    inputs/                 optional reference files (images, meshes, data)
    iteration1/
      taskstate.json        machine-readable state for this iteration
      brief.md              exact prompt sent to the specialist
      report.md             specialist's returned report, as received
      artifacts/            returned files: renders, exports, logs, screenshots
      review.md             Director review: evidence checked, verdict, feedback
    iteration2/
      ...
```

Use a short, descriptive `<task-id>` such as `3dobject1` or `invoice-export`. Number iterations from 1 and never reuse a number. Create only the files an iteration actually needs.

## Workflow

1. **Start a task.** Copy `_template/task.md` to `backlog/<task-id>/task.md` and fill it in. Put reference files in `inputs/` and link them by relative path.
2. **Start an iteration.** When asked to run the task, create `iteration<N+1>/`, copy `_template/iteration/taskstate.json`, and record the SHA-256 of the current `task.md`. Read the previous iteration's `review.md` and carry forward its unresolved feedback.
3. **Brief.** Write `brief.md` following [roles/README.md](../roles/README.md). Set status `awaiting_dispatch`, or `dispatched` once real runner execution is confirmed.
4. **Return.** Save the specialist's report and files without editing them. Set status `returned`.
5. **Review.** Check each acceptance criterion against evidence, update `acceptance` in `taskstate.json`, and write `review.md`. Set status `accepted`, `correction_needed`, or `blocked`, and record the next action.
6. **Iterate or close.** A `correction_needed` verdict feeds the next iteration's brief. When accepted, move durable decisions to [memory/longterm/](../memory/longterm/README.md) and reusable lessons to [memory/learnings/](../memory/learnings/README.md).

`task.md` holds the goal; iterations hold attempts. Change `task.md` only when the goal or criteria change; the recorded hash shows which version each iteration used. Feedback for a single attempt belongs in `review.md`.

## taskstate.json

| Field | Meaning |
| --- | --- |
| `task`, `iteration` | Task folder name and iteration number |
| `status` | `planned`, `awaiting_dispatch`, `dispatched`, `returned`, `in_review`, `correction_needed`, `accepted`, `blocked`, or `abandoned` |
| `created`, `updated` | ISO dates |
| `task_sha256` | Hash of the `task.md` this iteration ran against |
| `previous_iteration` | Number whose review fed this brief, or `null` |
| `specialist` | Runner and role, plus a dispatch reference once one exists |
| `acceptance` | One entry per criterion from `task.md`, with status `pass`, `partial`, `fail`, or `unverified` and links to evidence |
| `artifacts` | Returned files, with `local` or `remote` location; remote paths are reported, not verified |
| `blockers` | Open blockers that prevent progress |
| `decision` | Verdict, one-line summary, and next action |

Keep reported claims and verified evidence separate. A criterion passes only when the Director inspected supporting evidence. The current task status is the status of the highest-numbered iteration.

This folder is the live record for backlog tasks. Add a [short-term memory](../memory/shorterm/README.md) note only to link to it for a handoff, never to copy its state.
