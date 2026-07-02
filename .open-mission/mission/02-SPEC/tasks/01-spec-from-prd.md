---
resource: open-mission/provision/mission-template/02-spec/tasks/01-spec-from-prd
title: Draft Spec
type: template
summary: Read mission.prdPath and update only mission.specPath. Do not create implementation code, implementation task files, verification evidence, delivery artifacts, or decision records
owner: workflow
fileName: 01-spec-from-prd.md
subject: Draft Spec
---

Read {{mission.prdPath}} and update only {{mission.specPath}}. Do not create implementation code, implementation task files, verification evidence, delivery artifacts, or decision records outside the Mission folder.

Before writing the SPEC, run a design interrogation pass:

1. Read mission-local context, PRD source-review findings, resolved decisions, open questions, and mission ADR candidates from {{mission.prdPath}} and any supporting files under {{mission.missionPath}}.
2. Inspect existing code, docs, schemas, contracts, tests, or generated artifacts when they can prove the current architecture, names, ownership, or failure behavior.
3. Challenge every proposed design decision against the PRD outcome, mission-local decisions, discovered domain language, and existing architecture.
4. Convert requirements into explicit owners for behavior, validation, storage, integration, transport, presentation, configuration, and migration or cleanup.
5. Stress-test the design with concrete scenarios for lifecycle, permissions, tenant or context boundaries, invalid input, partial failure, concurrency, rollback, compatibility, and operator recovery.

Resolve PRD open questions where the codebase or mission-local records provide enough evidence. If a question remains blocking, record it in {{mission.specPath}} with your recommended answer and mark the SPEC as not ready for task generation.

If a hard-to-reverse, surprising, trade-off-driven decision must be recorded as an ADR, create or update only mission-local ADR files under {{mission.missionPath}}/02-SPEC/adrs. Link those ADRs from {{mission.specPath}}. Do not create or update decision records outside the Mission folder.

Make {{mission.specPath}} ready for task generation only when it contains: design, ownership rules, boundary semantics, allowed and forbidden scope, required files, implementation slices, validation commands, ignored failures, compatibility or cleanup policy, mission-local ADR links, and unresolved blockers.
