---
resource: open-mission/provision/skill/governance-writer/product
title: product
type: skill
summary: Governance-domain skill for product purpose, scope, users, roles, capabilities, value, and canonical terminology. Use with governance-writer when the target work belongs to the
owner: workflow
name: product
description: Governance-domain skill for product purpose, scope, users, roles, capabilities, value, and canonical terminology. Use with governance-writer when the target work belongs to the product domain.
disable-model-invocation: true
---

# Product

## Governance Domain Focus

Use this governance-domain skill when the requested governance update belongs to the product domain.

## What This Governance Domain Owns

Use this governance domain for product-level authority:

- product purpose
- product scope
- users and roles
- value propositions
- capabilities
- user-facing concepts
- canonical product terminology
- what the product is and is not

Do not use this governance domain for architecture design, contracts, runbooks, coding doctrine, or implementation walkthroughs.

## Primary Resources

- `.open-mission/documentation/product/index.md`
- `.open-mission/documentation/product/purpose.md`
- `.open-mission/documentation/product/scope.md`
- `.open-mission/documentation/product/users-and-roles.md`
- `.open-mission/documentation/product/capabilities.md`
- `.open-mission/documentation/product/terminology.md`

## Discovery

Inspect before writing:

1. existing product pages
2. terminology page
3. user journeys and surfaced behavior
4. manual pages for operator-facing behavior
5. current README and public-facing docs
6. architecture docs only for capability constraints
7. code only as evidence of implemented behavior

Do not let implementation details define product language unless the product docs are missing or contradicted by reality.

## Product Shape

Product pages should state:

- purpose
- audience
- scope
- non-scope
- capability
- user value
- canonical terms
- related roles
- related product boundaries

Use plain product language. Avoid internal implementation names unless they are user-facing.

## Writing Rules

- write directly in the product tree
- use one canonical term per concept
- pressure aliases instead of adding more
- distinguish current capability from intended capability
- avoid promises not supported by source or product docs
- cross-reference architecture, manual, doctrine, or decisions instead of duplicating
- preserve `<!-- open-mission:auto-index -->`
- state unresolved scope or terminology explicitly

## Decisions

Create or update a decision only when product language creates a durable product boundary, governance rule, scope constraint, or canonical terminology choice.

## Output

Report:

- product pages changed or created
- terms clarified
- capabilities or scope updated
- decisions linked or created
- unresolved questions
