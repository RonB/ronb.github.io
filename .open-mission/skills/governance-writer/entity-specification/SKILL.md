---
resource: open-mission/provision/skill/governance-writer/entity-specification
title: entity-specification
type: skill
summary: Cross-cutting governance discipline for Entity pages, Entity schemas, contracts, events, properties, relations, and implementation/doc alignment. Use with architecture or
owner: workflow
name: entity-specification
description: Cross-cutting governance discipline for Entity pages, Entity schemas, contracts, events, properties, relations, and implementation/doc alignment. Use with architecture or contracts when the target work is an Entity.
disable-model-invocation: true
---

---------------------------

# Entity Specification

## Owns

Use this skill when documenting, creating, modifying, or auditing an Entity.

This skill governs Entity specification as a governance discipline, not a governance domain.

Write Entity pages under:

* `.open-mission/documentation/architecture/entities/`

Update contract docs only when the Entity exposes reusable methods, events, APIs, or exchange schemas across a boundary.

## Discovery

Inspect before writing:

1. existing Entity governance
2. product terminology and constitution docs
3. related decisions
4. Entity class
5. Entity schema
6. Entity contract
7. storage metadata or migrations
8. routes, APIs, registries, adapters, sockets, streams, and UI consumers
9. tests and examples

Treat:

* schema as source of truth for properties, arguments, results, and payload shapes
* contract as source of truth for public methods and events
* class as source of truth for behavior and invariants
* callers and consumers as evidence of actual use

If class, schema, contract, docs, or decisions disagree, state the mismatch explicitly.

## Entity Page Shape

An Entity page should document:

* purpose
* owner
* responsibilities
* non-responsibilities
* lifecycle or status model
* important properties
* relations
* public methods
* public events
* persistence behavior
* runtime collaborators
* boundary surfaces
* main flows
* related contracts
* related decisions
* unresolved mismatches

Use diagrams only when they clarify relations, lifecycle, or runtime flow.

## Tables

Keep tables narrow.

Prefer:

* `Field | Meaning`
* `Method | Role | Notes`
* `Event | Meaning | Publisher`
* `Relation | Direction | Authority`

Do not use wide matrix tables. Move long explanations below the table.

## Methods

For every public Entity method, preserve the exact name and document:

* kind: query, mutation, or command
* input schema
* result schema
* behavior
* known callers
* side effects

If behavior or callers are unclear, mark it as a finding.

## Events

For every public Entity event, preserve the exact name and document:

* payload schema
* domain meaning
* publisher
* consumers or subscribers
* persistence or transport path
* ordering, replay, or idempotency only when source defines it

Do not invent event guarantees.

## Properties

For important Entity properties, preserve exact names and document:

* type or schema
* domain role
* whether it is canonical, derived, persisted, transported, or UI-facing

Group properties by role instead of alphabetically.

## Schemas

Entity schemas should have useful descriptions when they are documentation sources.

Report missing schema descriptions as findings. Do not expand the task unless the user asked for a schema documentation pass.

## Naming

Use canonical repository vocabulary.

Do not invent aliases. Flag vague names such as:

* `Data`
* `Info`
* `State`
* `Record`
* `View`
* `Payload`
* `Response`
* `Snapshot`

Only allow them when their role is explicitly documented.

## Decisions

Create or update a decision only when Entity work changes ownership, naming, lifecycle, public contract, persistence, or boundary behavior.

## Output

Report:

* Entity pages changed or created
* class, schema, and contract inspected
* methods documented
* events documented
* diagrams changed
* contract pages updated
* decisions linked or created
* mismatches or unresolved questions
