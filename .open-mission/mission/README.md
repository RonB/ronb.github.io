---
resource: open-mission/provision/mission-template/readme
title: Workflow
type: readme
summary: This directory contains repository-owned Mission workflow law and Mission artifact templates. mission.json is the workflow-law source; stage artifact and task templates live
owner: package
---

# Workflow

This directory contains repository-owned Mission workflow law and Mission artifact templates. `mission.json` is the workflow-law source; stage artifact and task templates live directly in the numbered artifact folders.

## OKF discipline

Provisioned Mission template Markdown is standing knowledge and follows the repository OKF profile. Generated Mission artifacts that become standing Markdown resources must preserve minimum OKF frontmatter: `resource`, `title`, `type`, `summary`, and `owner`.

Agents creating Mission Markdown must reuse canonical resource identifiers when referencing repository concepts, link to canonical documents instead of repeating architectural explanations, preserve ADR authority, update relationship metadata when canonical relationships change, and validate frontmatter plus relative links before delivery.
