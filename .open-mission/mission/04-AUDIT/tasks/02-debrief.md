---
resource: open-mission/provision/mission-template/04-audit/tasks/02-debrief
title: Debrief
type: template
summary: Review mission.verifyPath, the focused Mission diff, and the boundary-audit evidence already recorded in mission.auditPath. Adjudicate the Mission against its governing claims
owner: workflow
fileName: 02-debrief.md
subject: Debrief
---

# Debrief

Review {{mission.verifyPath}}, the focused Mission diff, and the boundary-audit evidence already recorded in {{mission.auditPath}}.

Adjudicate the Mission against its governing claims directly instead of restating implementation claims in weaker language.

Use an explicit decision matrix:

- governing claim or requirement
- observed implementation behavior
- observed runtime or boundary behavior
- pass/fail decision
- evidence reference

Do not mark the Mission as satisfied when the observed behavior only meets a weaker proxy while the governing claim still fails.

Separate Mission regressions from baseline failures. Record risks and the smallest follow-ups.
