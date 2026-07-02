---
resource: open-mission/provision/skill/governance-writer/decisions
title: decisions
type: skill
summary: Governance-domain skill for durable decisions, ADR-style records, tradeoffs, and rationale. Use with governance-writer when a change needs lasting explanation.
owner: workflow
name: decisions
description: Governance-domain skill for durable decisions, ADR-style records, tradeoffs, and rationale. Use with governance-writer when a change needs lasting explanation.
disable-model-invocation: true
---

# Decisions

## Governance Domain Focus

Use this governance-domain skill when the requested governance update belongs to the decisions domain.

## What This Governance Domain Owns

- decision records
- trade-offs, rationale, and permanence
- changes that need lasting explanation
- migration of legacy ADR substance into the repository-owned docs tree

## What This Governance Domain Does Not Own

- other governance-domain responsibilities
- duplicate source of truth
- implementation code unless it is needed as evidence for the docs

## Primary Resources

- `.open-mission/documentation/decisions/index.md`
- `.open-mission/documentation/decisions/ADR-template.md`
- `.open-mission/documentation/decisions/` itself
- legacy `docs/adr/` only as migration evidence
- relevant architecture, contract, product, or operations docs

## Discovery Rules

1. existing decision pages
2. architecture and contract docs affected by the decision
3. source files that implement or depend on the decision
4. issues or planning docs if present
5. legacy ADRs only as migration evidence

## Entity Decision Rule

When a decision affects an Entity, use `entity-specification` to inspect the Entity class, schema, contract, documentation, and consumers before writing the decision.

Create or update a decision only when the Entity change alters ownership, naming, lifecycle, public methods, public events, persistence, contract authority, or boundary behavior.

Cross-reference the affected Entity page under `.open-mission/documentation/architecture/entities/`.

## Decision Shape

A decision page must state:

- status
- context
- decision
- consequences
- rejected alternatives, if relevant
- affected docs or source areas

Use concise Markdown. Prefer facts over narrative.

## Status

Use simple statuses:

- proposed
- accepted
- superseded

If superseded, link to the replacing decision.

## Writing Rules

- one decision per page
- one decision per concept
- do not mix implementation tasks with rationale
- do not create parallel vocabulary
- cross-reference architecture, contracts, product, or operations instead of duplicating
- preserve `<!-- open-mission:auto-index -->`
- update affected docs after recording the decision

## Output

Return:

- decisions created or updated
- status used
- docs cross-referenced
- source inspected
- unresolved questions
