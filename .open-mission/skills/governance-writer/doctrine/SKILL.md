---
resource: open-mission/provision/skill/governance-writer/doctrine
title: doctrine
type: skill
summary: Governance-domain skill for rules, reusable patterns, examples, anti-patterns, conventions, and naming discipline. Use with governance-writer when the target work belongs to the
owner: workflow
name: doctrine
description: Governance-domain skill for rules, reusable patterns, examples, anti-patterns, conventions, and naming discipline. Use with governance-writer when the target work belongs to the doctrine domain.
disable-model-invocation: true
---

# Doctrine

## Governance Domain Focus

Use this governance-domain skill when the requested governance update belongs to the doctrine domain.

## What This Governance Domain Owns

Use this governance domain for reusable guidance:

- coding doctrine
- documentation doctrine
- naming discipline and terminology pressure
- conventions
- patterns
- anti-patterns
- examples that teach a reusable rule
- principles that guide repeated work

Do not use this governance domain for architecture ownership, contracts, product promises, runbooks, or one-off decisions.

## Primary Resources

- `.open-mission/documentation/doctrine/index.md`
- `.open-mission/documentation/doctrine/conventions/`
- `.open-mission/documentation/doctrine/patterns/`
- `.open-mission/documentation/doctrine/examples/`
- `.open-mission/documentation/doctrine/anti-patterns/`
- `.open-mission/documentation/doctrine/principles/`

## Discovery

Inspect before writing:

1. existing doctrine pages
2. glossary or vocabulary pages
3. current repository docs that use the term or pattern
4. examples and anti-patterns
5. source code that shows the actual pattern
6. tests and fixtures if they demonstrate expected use
7. related decisions if the doctrine came from a tradeoff

External sources may clarify general practices, but repository doctrine must come from repository usage and decisions.

## Doctrine Shape

A doctrine page should state:

- rule
- reason
- when to use it
- when not to use it
- good example
- bad example or anti-pattern, if useful
- related terms
- related decisions, if any

Keep examples small and focused.

## Writing Rules

- write directly in the doctrine tree
- use repository vocabulary exactly
- prefer one canonical term
- remove or pressure aliases instead of adding more
- document reusable rules, not one-off choices
- cross-reference other governance domains instead of duplicating their authority
- preserve `<!-- open-mission:auto-index -->`
- state unresolved terminology explicitly

## Decisions

Create or update a decision only when the doctrine records a durable tradeoff, resolves competing vocabulary, or changes a rule that many future changes depend on.

## Output

Report:

- doctrine pages changed or created
- terms clarified or pressured
- examples or anti-patterns added
- decisions linked or created
- unresolved questions
