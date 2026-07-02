---
resource: open-mission/provision/skill/governance-writer/operations
title: operations
type: skill
summary: Governance-domain skill for runbooks, deployment, recovery, observability, and operational procedures. Use with governance-writer when the target work belongs to the operations
owner: workflow
name: operations
description: Governance-domain skill for runbooks, deployment, recovery, observability, and operational procedures. Use with governance-writer when the target work belongs to the operations domain.
disable-model-invocation: true
---

# Operations

## Governance Domain Focus

Use this governance-domain skill when the requested governance update belongs to the operations domain.

## What This Governance Domain Owns

Use this governance domain for operating the system:

- runbooks
- deployment procedures
- recovery procedures
- incident handling
- observability and diagnostics
- environment setup needed for operation
- backup, restore, migration, and rollback procedures
- operational checks and verification

Do not use this governance domain for architecture authority, product promises, coding doctrine, contract definitions, or implementation walkthroughs.

## Primary Resources

- `.open-mission/documentation/operations/index.md`
- `.open-mission/documentation/operations/runbooks/`

## Discovery

Inspect before writing:

1. existing operations pages
2. deployment files and scripts
3. environment and configuration files
4. observability, logging, tracing, and metrics setup
5. backup, restore, migration, and recovery paths
6. runtime services and health checks
7. tests or scripts that validate procedures
8. related architecture pages only for context

## Runbook Shape

A runbook should state:

- purpose
- when to use it
- prerequisites
- procedure
- verification
- rollback or recovery
- risks
- related logs, metrics, or alerts
- related architecture or decisions

Keep steps executable and ordered.

## Writing Rules

- write directly in the operations tree
- document procedures, not design theory
- use exact command names, service names, and file paths from source
- distinguish local, preview, production, and future k3s behavior
- do not invent operational guarantees
- cross-reference architecture or contracts instead of duplicating them
- preserve `<!-- open-mission:auto-index -->`
- state unresolved behavior explicitly

## Decisions

Create or update a decision only when an operational rule is durable, hard to reverse, or changes deployment, recovery, observability, security, or ownership.

## Output

Report:

- operations pages changed or created
- procedures updated
- commands or scripts inspected
- verification steps added
- decisions linked or created
- unresolved questions
