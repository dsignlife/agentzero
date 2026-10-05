# Director and specialist roles

The Director owns planning, delegation, result review, and the next decision. Specialists own the bounded production work assigned to them. These descriptions are responsibilities, not a registry of running agents. Check [tools/README.md](../tools/README.md) and the runner's actual coordination tools before dispatching.

## Responsibilities

| Role | Owns | Typical returned evidence |
| --- | --- | --- |
| Director | Goal clarification, solution comparison, task sequencing, assignments, acceptance decisions, and progress | Current plan, assignment briefs, review decisions, blockers, and next action |
| Coding agent | Assigned source changes, debugging, and relevant documentation | Changed files, check results, implementation explanation, and remaining issues |
| Blender 3D agent | Assigned scenes, modeling, materials, lighting, renders, and exports | Source assets, preview renders, export settings, dimensions or scale checks, and limitations |
| Personal assistant | Assigned research, organization, or administrative work within authorized access | Findings or prepared artifacts, sources, actions actually taken, and unresolved questions |

The Director delegates substantial specialist work and may inspect artifacts, verify results, and edit planning or documentation directly. Specialist limits come from the user-authorized task; assigning work does not grant additional access or authority.

## Assignment brief

For each assignment, provide the following through the runner's supported coordination mechanism or as a ready-to-send brief:

```markdown
# Assignment: <task-id>

- Specialist and owner:
- Dispatch status: awaiting dispatch / dispatched
- Objective and why it matters:
- Relevant context and source paths:
- Relevant skills and receiving-runner access:
- Dependencies and readiness:
- Workspace and owned files or artifacts:
- Recommended approach and concrete steps:
- Constraints and actions outside the assignment's authority:
- Deliverables and destinations:
- Acceptance checks:
- Return channel:

## Required return
Results, artifact links, verification evidence, unresolved questions,
blockers, and any justified departure from the suggested approach.
```

Give concurrent writers distinct ownership. Allow justified alternative approaches when they satisfy the same constraints and acceptance criteria. Keep the assignment focused on the context that specialist needs. Select skills using the [Director routing table](../README.md#skills-the-director-uses); pass their paths and require the specialist to read matching instructions. Verify access rather than assuming skills propagate to every runner.

## Consume the return

Read the artifacts and check the supplied evidence against the assignment and overall goal. Record the result as accepted, correction needed, or awaiting evidence; explain the reason and next action. Resolve dependencies before dispatching later work. An agent's completion claim alone is insufficient evidence.

If a capability or return channel is missing, mark the brief `awaiting dispatch` and identify what is needed. Do not record an unexecuted task as completed.

Use [TEMPLATE.md](TEMPLATE.md) when a recurring specialist needs a separate role definition. The role table and per-task briefs cover this initialization; no specialist agent has been launched or registered by these documents.
