---
resource: open-mission/provision/mission-template/02-spec/tasks/02-plan
title: Plan Implementation And Verification
type: template
summary: Read mission.specPath and generate paired task markdown under mission.implementationTasksPath. Each slice gets one implementation task and one \"-verify.md\" task that depends on
owner: workflow
fileName: 02-plan.md
subject: Plan Implementation And Verification
---

Read {{mission.specPath}} and generate paired task markdown under {{mission.implementationTasksPath}}. Each slice gets one implementation task and one "-verify.md" task that depends on it. Set `dependsOn`, `taskKind`, and `pairedTaskId` in frontmatter. Do not create production code, delivery artifacts, verification evidence, mission ADRs, or workflow-engine structured runtime records.

Before generating tasks, verify that {{mission.specPath}} is ready for task generation. A ready SPEC has a source review, governing decisions or mission-local ADR references, explicit implementation slices, per-slice ownership, per-slice non-goals, per-slice done criteria, and per-slice narrow validation. If the SPEC contains unresolved blockers, unclear ownership, missing validation gates, ambiguous file scope, contradictory slice ordering, or unmade mission-local ADR decisions that affect implementation, stop and update no task files. Instead, report exactly what must be clarified in {{mission.specPath}}.

Before writing files, derive a task-generation table from the SPEC. For each row, identify slice id, objective, dependencies, owned files or globs, forbidden files or behaviors, expected change, validation commands or searches, and the paired verification task. If any row cannot be filled concretely from the SPEC, stop instead of guessing.

Every generated implementation task must be self-contained. It must not rely on implicit project doctrine, hidden conversation context, or broad phrases such as "as appropriate", "where needed", "etc.", "all relevant files", or "make robust". It may cite only the SPEC and decision artifacts explicitly named by the SPEC.

Generated task Markdown is standing operational knowledge. Add the repository OKF minimum frontmatter to every generated task: `resource`, `title`, `type`, `summary`, and `owner`. Use stable resource identifiers under `open-mission/mission/<mission-id>/implementation/<task-slug>` for implementation tasks and `open-mission/mission/<mission-id>/verification/<task-slug>` for verification tasks unless the Mission's SPEC provides a narrower canonical resource. Preserve task workflow fields (`dependsOn`, `taskKind`, `pairedTaskId`) alongside OKF fields. Link to canonical documents instead of repeating architectural explanations, preserve ADR authority, and update relationship metadata if the generated task establishes or removes canonical relationships.

Use this frontmatter shape for implementation tasks:

```yaml
---
resource: open-mission/mission/<mission-id>/implementation/<same-slug>
title: <Task title>
type: template
summary: <One-sentence task purpose.>
owner: workflow
dependsOn:
 - spec/02-plan
taskKind: implementation
pairedTaskId: implementation/<same-slug>-verify
---
```

Use the previous slice verification task as the dependency for later implementation tasks. Use this frontmatter shape for verification tasks:

```yaml
---
resource: open-mission/mission/<mission-id>/verification/<same-slug>
title: <Verification task title>
type: template
summary: <One-sentence verification purpose.>
owner: workflow
dependsOn:
 - implementation/<same-slug>
taskKind: verification
pairedTaskId: implementation/<same-slug>
---
```

Each implementation task must be lean enough for a coding agent to execute without inventing scope. Include these sections:

- Slice.
- Objective: one concrete outcome.
- Assumptions And Ambiguity: explicit assumptions; competing interpretations; questions that require stopping instead of guessing.
- Testing Policy: include the policy block below verbatim.
- Simplicity Rule: the smallest acceptable change; no speculative features, single-use abstractions, optional configurability, or impossible-scenario handling.
- Surgical Scope: concrete allowed files or globs, concrete forbidden files or globs, and unrelated cleanup that must only be mentioned, not changed.
- Dependencies And Ordering: prior task outputs this task may rely on, and later-slice behavior it must not implement.
- Expected Change: behavior or structure that must exist after the task.
- Compatibility And Cleanup Policy: what compatibility, fallback, migration, adapters, or deferred cleanup are allowed or forbidden.
- Success Criteria And Plan: brief step-by-step plan where each step names its verification check.
- Validation Gate: exact focused commands, static searches, tests, or review checks; do not require broad unrelated suites unless the slice owns that integration. If a command does not exist yet, name the closest existing command and the exact new focused test file expected from the task.
- Stop Conditions: conditions that require the coding agent to stop and ask for clarification rather than expanding scope.

Use this exact `## Testing Policy` section in every implementation task:

```md
## Testing Policy

Do not create tests merely to increase coverage.

Only write or modify tests when they validate meaningful behavior required by the PRD, SPEC, issue, or existing domain contract.

A test is valid only if it satisfies all of these:

1. It verifies observable behavior, not implementation details.
2. It would fail if the intended business rule were broken.
3. It tests a realistic success path, failure path, edge case, or regression.
4. It has a clear reason to exist that can be explained in one sentence.
5. It does not simply assert that a mocked function was called unless that call is itself the observable contract.
6. It does not test TypeScript, Zod, framework behavior, or trivial getters/setters unless the project adds custom logic around them.
7. It does not duplicate another existing test with different names or superficial data changes.
8. It does not assert the current implementation when the expected behavior is not specified.

Before adding a test, identify the behavior under test and the bug it would catch.
If no meaningful behavior can be identified, do not add the test.
```

Each verification task must be feature-frozen and must include these sections:

- Paired Task.
- Focused Checks: checks tied only to the paired task success criteria.
- Failure Signals: what proves the implementation drifted, overreached, or missed the target.
- Simplicity And Scope Review: confirm no speculative features, unrelated refactors, formatting churn, or pre-existing dead-code cleanup were introduced.
- Ignored Baseline Failures: unrelated failures that must be reported but not fixed.
- Evidence Location: where to append verification evidence.

Verification tasks must not ask the agent to implement missing behavior. If verification fails, the verifier reports the failure evidence and stops.

Keep slices small, dependency ordered, and independently finishable. Prefer one boundary, responsibility, or behavior per implementation task. If a slice would require a broad multi-area change, split it further before generating tasks.

Only create or update task markdown under {{mission.implementationTasksPath}}. The workflow engine owns structured runtime records.
