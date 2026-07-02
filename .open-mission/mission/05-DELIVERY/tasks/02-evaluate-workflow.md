---
resource: open-mission/provision/mission-template/05-delivery/tasks/02-evaluate-workflow
title: Evaluating the mission workflow
type: template
summary: Evaluate the workflow used for this mission before final delivery is claimed. Assume this task runs in an isolated session. Do not rely on prior Agent conversations, hidden
owner: workflow
fileName: 02-evaluate-workflow.md
subject: Evaluating the mission workflow
---

# Evaluating the mission workflow

Evaluate the workflow used for this mission before final delivery is claimed.

Assume this task runs in an isolated session. Do not rely on prior Agent conversations, hidden session state, or unstated operator intent. Investigate the durable Mission record instead: the Mission artifacts, stage task files, verification and audit artifacts, delivery artifacts, `.open-mission/mission/mission.json`, `.open-mission/mission/`, the generated task set, and the deterministic validation evidence available in the repository.

Update only {{mission.deliveryPath}} with a `## Workflow Evaluation` section. Record whether the workflow made the PRD, SPEC, implementation, verification, audit, delivery, changeset or release-note, commit, push, and issue-closeout expectations explicit, correct, unambiguous, and complete. Focus on gaps that can be proven from the durable artifacts, such as missing instructions, missing validation hooks, stage transitions that were not legible from the Mission record, or operator interventions that were required outside the declared workflow.

Treat a finding as in scope only when changing the workflow definition itself would plausibly prevent the problem in future missions. A workflow-law finding must be traceable to the declared workflow surface, such as `workflow.json`, a stage template, a task template, gate sequencing, required artifacts, or missing procedural instructions.

When evaluating audit and delivery behavior, check whether the workflow made independent observation, adjudication, and final closeout reconciliation explicit enough to prevent a Mission from passing on proxy evidence alone.

Do not treat mission-domain friction as workflow-law evidence. Exclude findings about product scope, spec quality, architectural choices, naming, schema shape, validation content, or environment drift unless the durable artifacts prove that the workflow omitted or contradicted a reusable procedural requirement for handling that class of work.

If the mission exposed only mission-specific content pressure and no reusable workflow-law defect, write `No workflow-law change proposed.` and briefly justify that conclusion from the durable artifacts.

Use this decision rule:

- If the issue would still recur even after clarifying the workflow definition, it is not a workflow-law finding.
- If the issue would likely disappear after clarifying a reusable workflow artifact or rule, it is a workflow-law finding.

Use this output contract inside `## Workflow Evaluation`:

- `Finding:` either `No workflow-law change proposed.` or one sentence naming the exact procedural defect.
- `Evidence:` cite the durable workflow artifacts that prove the conclusion.
- `Proposed Workflow Change:` include only when a reusable workflow-law refinement is justified.
- `Out Of Scope:` list any mission-content lessons that were intentionally excluded from workflow-law changes.

If required Mission records, workflow files, or validation evidence are missing or contradictory enough that evaluation would require guessing, stop without editing workflow law and report `WORKFLOW_EVALUATION_BLOCKED` with the exact missing or contradictory evidence.

If a workflow setup gap is found, do not change the repository default workflow without explicit operator permission. Instead, document the gap, propose the smallest workflow-law refinement that would close it, and, if needed, record a follow-up issue with clear acceptance criteria.
