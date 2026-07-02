---
resource: open-mission/provision/skill/governance-writer/architecture
title: architecture
type: skill
summary: Governance-domain skill for systems, entities, boundaries, flows, diagrams, and architecture authority. Use with governance-writer when the target work belongs to the architecture
owner: workflow
name: architecture
description: Governance-domain skill for systems, entities, boundaries, flows, diagrams, and architecture authority. Use with governance-writer when the target work belongs to the architecture domain.
disable-model-invocation: true
---

# Architecture

## Governance Domain Focus

Use this governance-domain skill when the requested governance update belongs to the architecture domain.

## What This Governance Domain Owns

- systems and runtime topology
- components and responsibility boundaries
- entities, relations, and lifecycle
- flows across services, agents, sandboxes, APIs, databases, or external systems
- architectural seams: trust, protocol, process, persistence, deployment, security
- diagrams that explain architecture

## What This Governance Domain Does Not Own

- product promises
- runbooks
- coding standards
- long decision rationale
- duplicate source of truth

## Primary Resources

- `.open-mission/documentation/architecture/index.md`
- `.open-mission/documentation/architecture/overview.md`
- `.open-mission/documentation/architecture/entities/index.md`
- `.open-mission/documentation/architecture/boundaries/index.md`
- `.open-mission/documentation/architecture/components/index.md`
- `.open-mission/documentation/architecture/flows/index.md`
- `.open-mission/documentation/architecture/systems/index.md`
- `.open-mission/documentation/architecture/diagrams/index.md`
- `docs/adr/` (legacy migration evidence only)

## Discovery Rules

1. existing architecture governance pages
2. related decisions
3. schemas, entities, registries, contracts
4. routes, APIs, services, managers, adapters
5. manifests, Dockerfiles, Compose, runtime config
6. tests and examples
7. callers only as needed

## Entity Rule

When the target is an Entity, use `entity-specification` as the governance discipline.

Write Entity pages under:

- `.open-mission/documentation/architecture/entities/`

Use `entity-specification` for Entity purpose, ownership, lifecycle, properties, relations, methods, events, persistence, collaborators, diagrams, and class/schema/contract/doc alignment.

If the Entity exposes reusable methods, events, APIs, or exchange schemas across a boundary, inspect the contracts domain and update contract governance only when needed.

## Diagrams

Use Mermaid.

Add or update a diagram only when it clarifies:

- multi-component interaction
- boundary crossing
- entity relations
- lifecycle/state
- ordered runtime behavior
- deployment/runtime topology

Prefer:

- flowchart for systems, components, boundaries, deployment
- sequence diagram for ordered interactions
- ER diagram for entity relations
- state diagram for lifecycles

Keep diagrams small. Label boundaries explicitly. Do not imply behavior not supported by source.

## Writing Rules

- write directly in the architecture tree
- use repository vocabulary exactly
- explain purpose, ownership, boundaries, and interaction
- summarize schemas/contracts; do not duplicate generated detail
- cross-reference other governance domains instead of duplicating
- preserve `<!-- open-mission:auto-index -->`
- state unresolved facts explicitly

## Decision Rules

Create or update a decision only when the architecture choice is hard to reverse, changes ownership or boundaries, or needs durable rationale.

## Output

Return the governance update you made plus any unresolved questions.
