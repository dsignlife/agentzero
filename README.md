# Director agent project

The Director is a task planner and coordinator for Codex or OpenClaude. It understands your goals, thinks through solutions, gives specialists clear instructions, consumes their results, and decides what happens next. It coordinates coding agents, Blender 3D agents, and personal assistants.

## Responsibilities and workflow

1. Clarify the outcome, constraints, and completion criteria. Ask focused questions when missing information changes the plan.
2. Compare approaches and recommend a practical solution.
3. Break the solution into bounded tasks, identify dependencies, and sequence the work.
4. Give each specialist an [assignment brief](roles/README.md) with the objective, relevant context, ownership, recommended steps, limits, deliverables, and acceptance checks.
5. Dispatch through actual runner tools when available. Track assignments and dependencies in [short-term memory](memory/shorterm/README.md).
6. Inspect returned artifacts and verification evidence. Accept the result, request corrections, gather more information, or assign the next task.
7. Update the plan and report accepted results, blockers, and the next action. Finish when the requested outcome and relevant checks are satisfied.

The Director delegates substantial coding, modeling, and specialist production. It may inspect artifacts, perform suitable verification, and edit planning, coordination, and documentation itself. It works autonomously within your authorized scope and asks when an action exceeds that scope. A specialist assignment does not grant additional access or permission.

If delegation is unavailable, the Director prepares a ready-to-send brief marked `awaiting dispatch`. A returned completion claim remains subject to review; required checks that cannot be performed stay explicitly unverified.

## Setup and available capabilities

Open the repository root in your chosen runner and ask it to read [AGENTS.md](AGENTS.md). OpenClaude's [CLAUDE.md](CLAUDE.md) adapter references those shared instructions. Confirm tool access, specialist workspaces, and return channels before dispatching tasks.

The [tool inventory](tools/README.md) records the initialization observations and remaining checks. Codex and Git were found on PATH; OpenClaude and Blender were not found on PATH. Coordination tools were exposed in the initialization session, but no persistent specialist registrations or Blender connection were established. These observations must be rechecked in future sessions.

The MCP example is empty, six Codex skills are present in `.codex/skills/`, and the local OpenClaude skills folder remains an empty scaffold. No executable repository utilities or automated evaluator are installed. This repository does not provision specialist applications or personal-assistant accounts. Configure missing capabilities only under a separate request; documentation alone does not make them available.

## Skills the Director uses

Select skills by their declared task triggers. Use the runner's skill catalog first; if a repo skill is absent from discovery, locate its file explicitly. Read the selected `SKILL.md` before acting, announce its use, and follow its instructions. Read supporting references or run helpers only when the selected workflow requires them. This follows [official OpenAI guidance on skill selection](https://learn.chatgpt.com/docs/build-skills).

| Skill | Use when |
| --- | --- |
| [writing-plans](.codex/skills/writing-plans/SKILL.md) | A specification or requirements need a multi-step implementation plan before coding begins. The Director can prepare the plan for a coding specialist. |
| [planning-with-files](.codex/skills/planning-with-files/SKILL.md) | Research or substantial work needs persistent planning, including work requiring five or more tool calls. Follow its selected task-directory and recovery workflow. |
| [multi-agent-patterns](.codex/skills/multi-agent-patterns/SKILL.md) | Designing coordination, context isolation, explicit handoffs, or parallel execution, or deciding whether multiple agents are justified. |
| [verification-before-completion](.codex/skills/verification-before-completion/SKILL.md) | Before claiming work is complete, fixed, or passing, or preparing a commit or PR. Run suitable checks and inspect fresh evidence. |
| [advanced-evaluation](.codex/skills/advanced-evaluation/SKILL.md) | Designing LLM-as-judge evaluation, scoring, comparisons, rubric calibration, bias mitigation, or automated quality assessment. |
| [memory-systems](.codex/skills/memory-systems/SKILL.md) | Designing persistent semantic memory, entity tracking, temporal validity, graph or vector retrieval, consolidation, or memory benchmarks. Ordinary task notes follow the memory README. |

Include relevant skill paths in specialist briefs and confirm the receiving runner can access them. The six repo skills are exposed in the current Codex session; recheck discovery when changing runners or sessions. A local skill does not establish external tool access, and hook support depends on the runner.

When `planning-with-files` owns a task, use its selected planning files as the current plan. Link that directory from short-term memory when a handoff needs it; avoid maintaining a second authoritative copy of the plan.

## Example requests

- "Compare approaches for adding a feature, then prepare a coding-agent brief with implementation steps and acceptance checks."
- "Plan a Blender asset from this reference. Specify the scene requirements, export formats, and review evidence for the 3D agent."
- "Break my research goal into personal-assistant tasks and identify the sources and access each task needs."
- "Review these specialist results, identify missing evidence, and decide what should happen next."
- "Resume this task from memory and tell me the current blocker and next assignment."

## Initialize or revise the Director project

1. Clone or copy this template into your project repository.
2. Start Codex or OpenClaude with the project root as its working directory.
3. Copy the first prompt below, replace bracketed values with your coordination needs, and send it to the agent. The later examples illustrate specialist briefs; they do not change the Director's primary role.
4. Review the edited documentation. It should describe the assigned role, its responsibilities, its boundaries, and the tools actually available for the project. Resolve any setup blockers the agent reports before starting work that depends on them.

Initialization specializes the Director's documentation. It does not by itself install tools, connect MCP servers, dispatch specialists, or complete a production task.

### First prompt

```text
Initialize or revise this repository as a Director agent project.

Project name: [Name]
Agent role: Director, task planner, and coordinator
Purpose: [Goals and domains this Director helps me coordinate]
Responsibilities: Compare solutions, plan tasks, instruct specialists,
review their results, maintain task state, and decide the next action.
Boundaries: [What is in scope, what is outside its role, and which actions need my approval]
Runner and tools: [Codex or OpenClaude; tools available or still needed]
Specialists: [Coding, Blender 3D, personal assistants, or others needed]
Deliverables: [Expected plans, briefs, review results, and destinations]
Success checks: [How completed work should be checked]

Read AGENTS.md first, then inspect the existing repository and README files.
Use this brief to specialize the documentation, preserving useful shared
guidance and existing project content.

Delegate substantial production work. Use actual runner coordination tools;
if unavailable, mark prepared briefs as awaiting dispatch. Review evidence
before accepting returned work. Stay within my authorized scope.

Use the installed Codex skills when their triggers match. Read the selected
SKILL.md before acting and include relevant skill paths in specialist briefs.
Keep the skill routing table and capability inventory current.

1. Update the root README.md with the project's purpose, the agent's role,
   responsibilities, boundaries, setup requirements, and example requests.
   Keep the initialization instructions and README file list useful for
   future setup changes.
2. Customize every existing README listed in the root README for this role.
   Explain how its folder supports the project. Describe actual tools and
   workflows; clearly identify anything that is not configured yet.
3. Update AGENTS.md, using TEMPLATE.md as its structure, so future sessions
   know the primary role, its scope, expected outputs, relevant checks, and
   when to read supporting files.
   Keep it under 600 words and link to details instead of duplicating them.
   Keep CLAUDE.md as the adapter to the shared instructions.
4. Explain the role's use of short-term task memory, long-term decisions,
   and verified learnings in the memory README files. Preserve the existing
   memory/shorterm/ spelling. Record confirmed setup decisions when useful;
   do not create fictional task histories or lessons.
5. Keep domain references in knowledge, reusable procedures in skills,
   shared utilities in tools, and requested artifacts in outputs. Document
   the primary role in roles/README.md; add specialist role definitions from
   roles/TEMPLATE.md only when the project needs them. Keep every TEMPLATE.md
   file generic so it can be reused for new entries.
6. Check that documentation links and repository paths resolve, that the
   READMEs and AGENTS.md agree, and that AGENTS.md meets its word limit.

This request authorizes edits to the project READMEs and AGENTS.md for
initialization. For this setup task, inspect available capabilities and
document requirements. Installations, external connections, and production
work need a separate request. Do not claim a tool is available merely
because a folder or configuration example exists.

Ask focused questions if essential role or boundary information is missing.
Otherwise proceed with the documentation edits, state your assumptions, and
report the changed files and any remaining setup blockers.
```

### Example specialist brief: coding agent

Adapt these values into the assignment format in roles/README.md, adding task-specific context, ownership, dependencies, steps, and a return channel:

```text
Project name: My application
Agent role: Coding agent
Purpose: Build and maintain this application's source code.
Responsibilities: Implement requested features, investigate bugs, review code, maintain relevant documentation, and run appropriate checks.
Boundaries: Work within this repository and the requested scope. Ask before deploying, publishing releases, changing production data, or making destructive changes to unrelated work.
Runner and tools: Codex or OpenClaude, Git, and the project's language and test tools. Inspect the repository to identify the stack and missing prerequisites.
Deliverables: Source changes and relevant documentation in their project locations; requested reports or exported artifacts under outputs/.
Success checks: Relevant tests, formatting and lint checks, and a build when applicable. Report checks that cannot be run.
```

### Example specialist brief: Blender 3D agent

```text
Project name: My 3D asset studio
Agent role: Blender 3D agent
Purpose: Create and refine Blender scenes and 3D assets from my briefs.
Responsibilities: Modeling, materials, lighting, cameras, rendering, and exporting requested assets. Document scene organization and export requirements.
Boundaries: Work on the requested scenes and assets. Ask before overwriting original source assets, purchasing assets, uploading or publishing work, or starting paid rendering jobs.
Runner and tools: Codex or OpenClaude and Blender. Inspect whether a Blender connection or MCP tool is available and document any missing setup.
Deliverables: Blender source files, renders, and requested exports under outputs/<task-id>/, with formats and naming agreed in the task brief.
Success checks: Inspect the scene and a preview render; check dimensions, scale, materials, and requested export settings. Report anything that cannot be verified with the available tools.
```

## README files to customize

These README files describe the Director's role and supporting workflows. When revising setup, keep them consistent with the actual responsibilities and available capabilities.

| README file | When to edit | What to document |
| --- | --- | --- |
| [README.md](README.md) | When the Director's scope or setup changes | Maintain the purpose, boundaries, workflow, setup requirements, example requests, and README list. |
| [tools/README.md](tools/README.md) | When capabilities change | Update the verified tool inventory, delegation method, prerequisites, and remaining setup checks. |
| [roles/README.md](roles/README.md) | When responsibilities or handoffs change | Maintain Director and specialist responsibilities, assignment instructions, return evidence, and result review. |
| [memory/README.md](memory/README.md) | When changing how project memory is used | Explain how agents find, read, update, and maintain memory across sessions. |
| [memory/shorterm/README.md](memory/shorterm/README.md) | When changing task handoffs | Describe active task records, required context, and cleanup after completion. |
| [memory/longterm/README.md](memory/longterm/README.md) | When changing durable project memory | Describe which confirmed decisions to retain, supporting evidence, and review triggers. |
| [memory/learnings/README.md](memory/learnings/README.md) | When changing how lessons are recorded | Describe verification, applicability, and how to update or retire lessons. |
| [evals/README.md](evals/README.md) | When adding or changing evaluations | Explain the evaluation cases, how to run them, expected results, pass criteria, and where generated results are stored. |
| [outputs/README.md](outputs/README.md) | When defining project deliverables | Describe expected artifacts, their folder layout and naming, and which outputs should be committed to Git. |

## Templates

Copy a `TEMPLATE.md` when creating a new entry, then replace its bracketed text. Keep the templates generic so every new agent or entry starts from the same structure.

| Template | Creates | Copy to |
| --- | --- | --- |
| [TEMPLATE.md](TEMPLATE.md) | A specialized agent guide | `AGENTS.md`, during initialization |
| [roles/TEMPLATE.md](roles/TEMPLATE.md) | A specialist role definition | `roles/<role-name>.md` |
| [knowledge/TEMPLATE.md](knowledge/TEMPLATE.md) | A domain reference | `knowledge/<topic>.md`, indexed in `knowledge/INDEX.md` |
| [memory/shorterm/TEMPLATE.md](memory/shorterm/TEMPLATE.md) | An active task note | `memory/shorterm/<task-id>.md` |
| [memory/longterm/TEMPLATE.md](memory/longterm/TEMPLATE.md) | A durable decision | `memory/longterm/<topic>.md` |
| [memory/learnings/TEMPLATE.md](memory/learnings/TEMPLATE.md) | A verified lesson | `memory/learnings/<lesson>.md` |
| [outputs/TEMPLATE.md](outputs/TEMPLATE.md) | A requested result report | `outputs/<task-id>/result.md` |
| [backlog/_template/](backlog/_template/) | A backlog task and its iterations | `backlog/<task-id>/`; see [backlog/README.md](backlog/README.md) |
