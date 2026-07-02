---
resource: open-mission/provision/skill/governance-writer/quality
title: quality
type: skill
summary: Governance-domain skill for quality requirements, verification, audits, exemptions, checks, and lessons. Use with governance-writer when the target work belongs to the quality
owner: workflow
name: quality
description: Governance-domain skill for quality requirements, verification, audits, exemptions, checks, and lessons. Use with governance-writer when the target work belongs to the quality domain.
disable-model-invocation: true
---

# Quality

## Governance Domain Focus

Use this governance-domain skill when the requested governance update belongs to the quality domain.

## What This Governance Domain Owns

Use this governance domain for quality authority:

- quality requirements
- verification rules
- required checks
- audit rules
- exemptions
- lessons and feedback loops
- acceptance and review expectations
- evidence required before work is considered done

Do not use this governance domain for architecture design, product promises, contracts, runbooks, or implementation walkthroughs.

## Primary Resources

- `.open-mission/documentation/quality/index.md`
- `.open-mission/documentation/quality/requirements.md`
- `.open-mission/documentation/quality/verification.md`
- `.open-mission/documentation/quality/audits.md`
- `.open-mission/documentation/quality/exemptions/`
- `.open-mission/documentation/quality/lessons/`

## Discovery

Inspect before writing:

1. existing quality pages
2. tests, checks, linters, type checks, and CI config
3. mission or issue acceptance criteria
4. audit reports or review notes
5. exemptions and lessons
6. related doctrine if the rule is reusable guidance
7. code only as evidence of behavior

Do not invent quality gates that are not supported by source, docs, or explicit instruction.

## Entity Quality Rule

When verifying or auditing an Entity, use `entity-specification` to check alignment between Entity class, schema, contract, documentation, tests, and decisions.

Record quality findings under the quality domain only when they define verification expectations, audit findings, exemptions, or lessons. Keep Entity explanation in the architecture Entity page.

## Quality Shape

Quality pages should state:

- rule or requirement
- reason
- scope
- required evidence
- verification method
- pass/fail expectation
- exemption path, if any
- related checks
- related lessons or decisions

Keep requirements testable where possible.

## Writing Rules

- write directly in the quality tree
- document verification expectations, not implementation details
- use exact check, script, and CI names from source
- distinguish required checks from recommended checks
- distinguish current checks from intended checks
- cross-reference doctrine, operations, contracts, or decisions instead of duplicating
- preserve `<!-- open-mission:auto-index -->`
- state unresolved verification gaps explicitly

## Decisions

Create or update a decision only when a quality rule becomes durable governance, changes acceptance criteria, or creates a standing exemption policy.

## Output

Report:

- quality pages changed or created
- requirements or checks updated
- evidence inspected
- exemptions or lessons linked
- decisions linked or created
- unresolved questions
