---
resource: open-mission/provision/skill/governance-writer
title: governance-writer
type: skill
summary: Maintains the repository governance harness for agent-supported development by inspecting source, reconciling authority, and updating authoritative Markdown across governance
owner: workflow
name: governance-writer
description: Maintains the repository governance harness for agent-supported development by inspecting source, reconciling authority, and updating authoritative Markdown across governance domains.
disable-model-invocation: true
---

# Governance Writer

Use this skill to maintain the repository governance harness.

This skill does not write explanatory documentation as an end in itself. It maintains the repository governance harness that agent-supported development must obey.

## Modes

### Autonomous Mode

Use after the user selects autonomous mode.

In autonomous mode, inspect first, infer from source, and write directly. Do not ask setup questions. Choose the safest wording that does not invent authority, and record unresolved questions in the output.

### Guidance Mode

Use only when the user explicitly requests questions, clarification, or review before writing.

In guidance mode, stay conversational but evidence-bound:

- inspect source first
- prefer accepted governance, code contracts, schemas, tests, and current governance over memory or assumption
- challenge vague or overloaded terms against the repository's domain model and documented decisions
- ask only the minimum questions needed to remove ambiguity
- ask one focused question at a time, and wait for an answer before continuing
- if a question can be answered by exploring the codebase, explore the codebase instead
- discuss concrete scenarios that stress-test boundaries, edge cases, and ownership
- surface contradictions between the user's statement and the code or governance tree
- update repository-owned governance inline as decisions crystallize
- do not invent authority or fill gaps with made-up governance
- offer ADRs sparingly, only when the decision is hard to reverse, surprising without context, and the result of a real trade-off

Ask questions only when the answer cannot be derived from source or existing governance and the ambiguity would affect names, ownership, scope, behavior, or policy.

## Start

0. Ask one focused question: autonomous mode or guidance mode?
1. Inspect whether the repository governance tree exists and whether it is scaffolded:
   - `.open-mission/documentation/`
   - `.open-mission/documentation/index.md`
   - the target governance domain folder and its `index.md`, if one is named
2. Classify the governance status:
   - scaffolded
   - partially scaffolded
   - missing
   - legacy-only
3. Determine the best governance domain path from the repository scaffold.
4. Route to the matching governance domain skill when the domain is clear.
5. Inspect source before writing.
6. Write the governance updates directly, not just a report.

## Governance Disciplines

Some skills are governance disciplines, not governance domains.

Use `entity-specification` when the target work involves an Entity, including Entity creation, modification, documentation, schema changes, contract changes, event documentation, property documentation, relation documentation, or Entity audits.

Route governance updates to the owning domain:
- Entity pages go under `.open-mission/documentation/architecture/entities/`.
- Entity exchange contracts go under `.open-mission/documentation/contracts/` only when the contract is reusable across a boundary.
- Entity decisions go under `.open-mission/documentation/decisions/` only when the change alters ownership, naming, lifecycle, public contract, persistence, or boundary behavior.

## Authority Ladder

Lower authority may explain higher authority, but it must not override it.

1. `.open-mission/documentation/product/context.md`, constitution pages, accepted decisions, and explicit repository governance under `.open-mission/documentation/`
2. current code contracts, schemas, routes, entities, configs, and manifests
3. tests and examples
4. current README files and legacy docs
5. issue descriptions and planning docs
6. external docs and public references
7. model knowledge
8. user inference

## Approach

- inspect source first
- challenge fuzzy terms against the repository glossary, context, and governance tree
- update governance inline as decisions crystallize
- ask questions only when source cannot resolve the ambiguity and writing would otherwise invent authority
- offer ADRs only when the decision is hard to reverse, surprising without context, and genuinely traded off

## Governance Domain Routing

If the work clearly belongs to one governance domain, delegate to the matching domain skill first:

- architecture
- constitution
- contracts
- decisions
- doctrine
- manual
- operations
- product
- quality

If the work spans domains, start with the primary domain and cross-reference the others rather than duplicating content.

## Domain Awareness

For this repository, the canonical repository governance tree is `.open-mission/documentation/`.

- treat `.open-mission/documentation/` as the source tree for repository-owned governance
- use the governance domain tree exactly as scaffolded there
- treat `.open-mission/documentation/decisions/` as the home for decisions, not a separate ADR tree
- treat `.open-mission/documentation/product/context.md` as the canonical vocabulary and relationship map
- use `index.md` as the route file for domain roots
- keep `<!-- open-mission:auto-index -->` where the scaffold expects generated child listings
- if a legacy `docs/adr/` exists in a repo, treat it as migration evidence and map its substance into the repository-owned governance tree instead of copying the folder structure

Create files lazily: only create a governance page or ADR when you have something to write.

## Core Rules

- Investigate the codebase and the existing governance before writing.
- Prefer the repository's current vocabulary; do not invent aliases or duplicate terms.
- Keep terminology concise and canonical. Prefer one word when possible.
- Update governance inline as decisions crystallize; do not batch resolved facts into a late cleanup pass.
- Keep frontmatter correct and minimal.
- Use the exact governance domain structure when a page belongs to a domain tree.
- Do not create parallel names for the same concept.
- Do not mirror external folder conventions when the repository scaffold already defines a different shape.
- External knowledge may clarify external systems, standards, or libraries, but it must not create repository authority.

## Source Order

Read the relevant source of truth first:

- `.open-mission/documentation/product/context.md`
- `.open-mission/documentation/`
- repository ownership and boundary docs
- relevant decisions or doctrine pages
- the code that owns the topic
- the current governance page that already covers the topic
- callers, consumers, and neighboring modules only as far as needed to explain the topic safely

## Writing Discipline

When writing or updating governance:

- preserve existing authority unless the code or governance clearly override it
- explain what the thing is, why it exists, what it owns, and what it does not own
- describe the runtime or operational path in plain language before diagrams
- use narrow tables and short cells
- prefer links over repetition
- keep headings below frontmatter at `##` or deeper
- if a term changes, update the owning context or governance page instead of letting aliases accumulate
- if the page is about an Entity, apply Entity-specification discipline for class, schema, contract, events, properties, relations, and cross-control
- if a fact remains unresolved, state that explicitly instead of smoothing it over

## Entity Pages

When governing an Entity, treat the class, schema, contract, and relevant decisions as the canonical surface. Document only what the source and current governance support. If names or ownership are unresolved, call that out instead of smoothing it over.

## Output

Return a concise governance report with:
- mode used
- governance status
- pages changed or created
- governance updated directly
- decisions captured
- unresolved questions
- checks run or still needed
