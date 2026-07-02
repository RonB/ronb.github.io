---
resource: open-mission/provision/mission-template/01-prd/tasks/01-prd-from-brief
title: PRD From Brief
type: template
summary: Read mission.briefPath as intake. Update only mission.prdPath. Do not create code, SPEC content, implementation tasks, verification evidence, decision records outside the Mission
owner: workflow
fileName: 01-prd-from-brief.md
subject: PRD From Brief
---

Read {{mission.briefPath}} as intake. Update only {{mission.prdPath}}. Do not create code, SPEC content, implementation tasks, verification evidence, decision records outside the Mission folder, or other artifacts.

Before writing the PRD, run a doctrine-and-context interrogation pass:

1. Read the mission-local context and decision material that governs the brief, if present, under {{mission.missionPath}}. Also read repository governance, glossary, code comments, schemas, contracts, tests, or decision records only when they are discoverable and relevant to the brief.
2. Inspect existing code, docs, schemas, contracts, or tests when they can answer a question more reliably than the brief.
3. Challenge vocabulary against the discovered glossary or domain language. If the brief uses a conflicting, vague, overloaded, or new term, either map it to the canonical term or record the conflict.
4. Challenge ownership against mission-local decisions, discovered decision records, and existing architecture. Identify the authoritative owner for each required behavior, state, storage location, integration, and presentation concern.
5. Stress-test the brief with concrete edge scenarios that expose missing roles, lifecycle states, permissions, failure behavior, compatibility expectations, migration expectations, and verification signals.

Resolve questions from mission-local records, discovered repository sources, or code whenever possible. When a decision is still unclear, record it in {{mission.prdPath}} as an open question with your recommended answer and whether it blocks SPEC work. If a hard-to-reverse decision appears to need an ADR, record a mission-local ADR candidate in {{mission.prdPath}}; do not create decision records outside the Mission folder. If interactive input is available, ask only genuinely blocking questions one at a time; otherwise do not invent certainty.

Write a requirements-level PRD that states the product outcome, affected surface, authoritative inputs, problem, success criteria, constraints, non-goals, module or ownership roles, compatibility or cleanup policy, smallest verification expectations, source review findings, resolved decisions, mission-local ADR candidates, and open questions.
