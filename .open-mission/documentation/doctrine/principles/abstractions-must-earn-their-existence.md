---
resource: open-mission/provision/documentation/doctrine/principles/abstractions-must-earn-their-existence
title: Every abstraction must earn its existence
type: doctrine
summary: Prefer direct code unless an abstraction adds concrete value. Preserve an abstraction only when it adds domain meaning, owns a responsibility or invariant, enables meaningful
owner: architecture
id: doctrine:abstractions-must-earn-their-existence
kind: doctrine-principle
status: accepted
related:
  - antipattern:redundant-symbolic-alias
  - antipattern:pass-through-wrapper
  - antipattern:speculative-abstraction
---

## Every Abstraction Must Earn Its Existence

Prefer direct code unless an abstraction adds concrete value.

Preserve an abstraction only when it adds domain meaning, owns a responsibility or invariant, enables meaningful reuse, establishes a stable boundary, improves validation, improves testability, improves observability, or reduces cognitive load.

Do not create aliases, wrappers, helpers, factories, interfaces, registries, or layers merely because they are possible.

A one-use abstraction is not automatically wrong. A reused abstraction is not automatically justified.
