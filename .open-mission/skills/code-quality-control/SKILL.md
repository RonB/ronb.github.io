---
resource: open-mission/provision/skill/code-quality-control
title: Code Quality Control
type: skill
summary: Use this skill before audit when reviewing recently changed implementation code. 1. Identify the Mission requirement rows and implementation slice under review. 2. Inspect the
owner: workflow
---

# Code Quality Control

Use this skill before audit when reviewing recently changed implementation code.

## Procedure

1. Identify the Mission requirement rows and implementation slice under review.
2. Inspect the changed files for unnecessary abstractions, hidden compatibility paths, authority conflicts, and missing verification.
3. Confirm repository-owned guidance was retrieved through bounded Mission context rather than broad, unaudited search.
4. Record findings with concrete file references, severity, and the requirement row they affect.
5. Mark each finding as blocking, follow-up, or accepted with rationale.

## Output

Return a concise QC report that lists blocking issues first, then verification gaps, then non-blocking cleanup notes.