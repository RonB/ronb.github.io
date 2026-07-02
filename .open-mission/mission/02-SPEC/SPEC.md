---
resource: open-mission/provision/mission-template/02-spec/spec
title: Spec
type: template
summary: Branch: mission.branchRef
owner: workflow
---

Branch: {{mission.branchRef}}

## Architecture

- TODO: Describe the simplest design that satisfies PRD.md.
- TODO: State the authoritative owner for every changed concept.
- TODO: State allowed owners for behavior, validation, storage, integration, and presentation.
- TODO: State required failure behavior.

## Source Review And Decisions

- TODO: Record current architecture evidence used for the design.
- TODO: Link governing decisions and mission-local ADRs.
- TODO: Record unresolved blockers that make task generation unsafe.

## Signatures

- TODO: List the core types, signatures, and responsibilities.
- TODO: Define boundary request, response, command, query, or event semantics.

## File Matrix

- TODO: List the exact files that must change and why.
- TODO: List allowed support files and out-of-scope files.

## Implementation Slices

- TODO: Define small implementation slices, each with one verification slice.
- TODO: For each slice, list objective, owner, non-goals, done criteria, files, checks, and unrelated failures to ignore.

## Compatibility And Cleanup

- TODO: State whether compatibility, fallback, migration, adapters, or deferred cleanup are allowed or forbidden.

## Validation

- TODO: List focused validation commands or static checks for each slice.
- TODO: List known baseline failures to ignore.

## Task Authoring Rules

- Implementation tasks must state scope, allowed files, forbidden files, expected change, and validation gate.
- Verification tasks must state focused checks, failure signals, ignored baseline failures, and evidence location.
- State explicitly whether compatibility, fallback, adapters, or deferred cleanup are allowed or forbidden.
- Record verification evidence under a task-specific heading.
