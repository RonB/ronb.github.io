---
resource: open-mission/provision/documentation/doctrine/anti-patterns/pass-through-wrapper
title: Pass-through wrapper
type: doctrine
summary: Avoid wrappers that forward calls without owning translation, validation, policy, observability, or another clear responsibility.
owner: architecture
id: antipattern:pass-through-wrapper
kind: doctrine-antipattern
status: accepted
related:
  - doctrine:abstractions-must-earn-their-existence
---

## Pass-Through Wrapper

Avoid wrappers that forward calls without owning translation, validation, policy, observability, or another clear responsibility.
