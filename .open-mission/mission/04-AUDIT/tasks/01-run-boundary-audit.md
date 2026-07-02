---
resource: open-mission/provision/mission-template/04-audit/tasks/01-run-boundary-audit
title: Run boundary audit
type: template
summary: Run the authoritative audit observation for this Mission and update mission.auditPath. Capture concrete evidence from the owned runtime or execution boundary for the behavior
owner: workflow
fileName: 01-run-boundary-audit.md
subject: Run boundary audit
---

# Run boundary audit

Run the authoritative audit observation for this Mission and update {{mission.auditPath}}.

Capture concrete evidence from the owned runtime or execution boundary for the behavior being audited before drawing conclusions.

Record:

- the observed end-to-end flow or boundary behavior
- the commands, inputs, environments, or surfaces used
- the operator-visible evidence, logs, outputs, or artifacts gathered
- whether the observation supports or contradicts the governing Mission claims

This task is observational only. Do not adjudicate final Mission compliance here; record the runtime or boundary evidence so the debrief task can evaluate it.

Separate Mission regressions from baseline failures. Record risks and the smallest follow-ups.
