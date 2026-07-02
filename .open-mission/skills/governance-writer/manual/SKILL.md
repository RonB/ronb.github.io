---
resource: open-mission/provision/skill/governance-writer/manual
title: manual
type: skill
summary: Governance-domain skill for operator-facing concepts, guides, and reference material. Use with governance-writer when the target work belongs to the manual domain.
owner: workflow
name: manual
description: Governance-domain skill for operator-facing concepts, guides, and reference material. Use with governance-writer when the target work belongs to the manual domain.
disable-model-invocation: true
---

# Manual

## Governance Domain Focus

Use this governance-domain skill when the requested governance update belongs to the manual domain.

## What This Governance Domain Owns

Use this governance domain for operator-facing documentation:

- concepts needed to use the system
- how-to guides
- task walkthroughs
- UI and workflow guidance
- reference material for operators
- expected user-facing behavior
- troubleshooting only when it helps normal use

Do not use this governance domain for architecture authority, contracts, doctrine, product promises, operational runbooks, or implementation walkthroughs.

## Primary Resources

- `.open-mission/documentation/manual/index.md`
- `.open-mission/documentation/manual/concepts/`
- `.open-mission/documentation/manual/guides/`
- `.open-mission/documentation/manual/reference/`

## Discovery

Inspect before writing:

1. existing manual pages
2. user-facing flows
3. UI labels, routes, and screens
4. operator tasks
5. product docs only for intent
6. code only as needed to verify behavior
7. tests, screenshots, or examples if present

Do not expose internal implementation details unless they affect operator behavior.

## Manual Shape

Use:

- concepts for explaining what something means
- guides for completing a task
- reference for lookup material

A guide should state:

- goal
- when to use it
- prerequisites, if any
- steps
- expected result
- common problems, if known
- related concepts or reference pages

## Writing Rules

- write directly in the manual tree
- use user-facing vocabulary
- prefer short task-oriented sections
- keep internal names out unless visible to the operator
- avoid architecture explanations unless needed for use
- cross-reference other governance domains instead of duplicating their authority
- preserve `<!-- open-mission:auto-index -->`
- state unresolved behavior explicitly

## Decisions

Create or update a decision only when operator-facing behavior becomes policy, doctrine, or a durable product rule.

## Output

Report:

- manual pages changed or created
- concepts, guides, or references updated
- user-facing behavior verified
- decisions linked or created
- unresolved questions
