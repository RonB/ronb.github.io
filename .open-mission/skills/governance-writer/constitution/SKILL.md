---
resource: open-mission/provision/skill/governance-writer/constitution
title: constitution
type: skill
summary: Governance-domain skill for ownership, boundaries, and governing principles. Use with governance-writer when the target work belongs to the constitution domain.
owner: workflow
name: constitution
description: Governance-domain skill for ownership, boundaries, and governing principles. Use with governance-writer when the target work belongs to the constitution domain.
disable-model-invocation: true
---

# Constitution

## Governance Domain Focus

Use this governance-domain skill when the requested governance update belongs to the constitution domain.

## What This Governance Domain Owns

- ownership and boundary law
- repository-wide governing principles
- non-negotiable rules that shape every governance domain

## What This Governance Domain Does Not Own

- other governance-domain responsibilities
- duplicate source of truth
- implementation code unless it is needed as evidence for the docs

## Entity Rule

When the topic is an Entity, use `entity-specification` to inspect the Entity class, schema, contract, documentation, and consumers before writing. Keep Entity pages under `.open-mission/documentation/architecture/entities/` and cross-reference contracts or decisions only when the Entity changes boundary behavior or governance.

## Primary Resources

- `.open-mission/documentation/constitution/index.md`
- `.open-mission/documentation/constitution/engineering-principles.md`
- `.open-mission/documentation/index.md`
- `.agents/constitution.md`
- `.open-mission/documentation/product/context.md`

## Discovery Rules

1. constitution pages
2. repository-wide context and glossary
3. accepted ADRs that define governance
4. code only as evidence of enforcement

## Writing Rules

- stay inside the constitution domain structure and its linked source of truth
- prefer the repository's current vocabulary
- update the docs file directly; do not only describe changes
- keep headings below frontmatter at `##` or deeper
- keep tables narrow and prose compact
- if the topic crosses domain boundaries, call out the cross-reference instead of duplicating content
- if a fact is unresolved, state that explicitly

## Decision Rules

Create a decision page when a governing rule is hard to reverse, surprising without context, and materially changes other governance domains.

## Output

Return the governance update you made plus any unresolved questions.
