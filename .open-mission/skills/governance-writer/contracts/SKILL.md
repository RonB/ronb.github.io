---
resource: open-mission/provision/skill/governance-writer/contracts
title: contracts
type: skill
summary: Governance-domain skill for APIs, schemas, events, manifests, MCP tools, configuration, and data exchange contracts. Use with governance-writer when the target work defines how
owner: workflow
name: contracts
description: Governance-domain skill for APIs, schemas, events, manifests, MCP tools, configuration, and data exchange contracts. Use with governance-writer when the target work defines how parts communicate.
disable-model-invocation: true
---

# Contracts

## Governance Domain Focus

Use this governance-domain skill when the requested governance update belongs to the contracts domain.

## What This Governance Domain Owns

Use this governance domain for contracts between parts of the system:

- HTTP/API contracts
- route request/response shapes
- entity schemas when used as exchange contracts
- events and messages
- MCP/tool contracts
- manifests
- configuration and environment contracts
- persistence-facing contracts when externally relied on

Do not use this governance domain for general architecture, product behavior, runbooks, or implementation walkthroughs.

## Primary Resources

- `.open-mission/documentation/contracts/index.md`
- `.open-mission/documentation/contracts/`

Also inspect related architecture pages when the contract defines a boundary or flow.

## Discovery

Inspect before writing:

1. existing contract docs
2. route handlers and API definitions
3. Zod schemas
4. Pydantic models
5. OpenAPI output or generated clients
6. event/message schemas
7. MCP/tool definitions
8. manifests and environment definitions
9. tests and examples

Generated output is evidence, not automatically the canonical explanation.

## Entity Contract Rule

When a contract belongs to an Entity, use `entity-specification` to inspect the Entity class, schema, contract, events, consumers, and boundary surfaces.

Document the Entity itself under `.open-mission/documentation/architecture/entities/`.

Document contract pages under `.open-mission/documentation/contracts/` only when the Entity contract is reused across a boundary or needed independently from the Entity page.

## Contract Shape

A contract page should state:

- purpose
- owner
- consumers
- source of truth
- request/input shape
- response/output shape
- events or side effects
- validation rules
- error behavior, if defined
- versioning or compatibility notes, if defined

Keep field tables narrow. List only fields that matter for the contract.

## Writing Rules

- document the contract, not the implementation
- use exact names from source
- do not invent semantics from field names alone
- distinguish required, optional, derived, and generated fields
- cross-reference architecture flows or boundaries instead of duplicating
- state unresolved or mismatched source explicitly
- preserve `<!-- open-mission:auto-index -->`

## Decisions

Create or update a decision only when the contract choice changes compatibility, ownership, protocol, schema authority, or a boundary.

## Output

Report:

- contracts changed or created
- source of truth inspected
- schemas inspected
- affected flows or boundaries
- decisions linked or created
- unresolved questions
