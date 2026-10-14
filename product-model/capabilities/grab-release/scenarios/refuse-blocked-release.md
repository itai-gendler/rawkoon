---
kind: validation
routes:
  web: Web
steps:
- text: The Administrator grabs a release that is on the blocklist
  kind: actor
  actor: administrator
  entities:
  - {entity: grab, effect: reads, facts: []}
  contexts:
    web:
      place: web::household::title
- text: The Product refuses, giving the reason the release was blocked
  kind: condition
  entities:
  - {entity: blocklisted-release, effect: reads, facts: [Release title, Reason]}
  contexts:
    web:
      place: web::household::title
---

# Refuse a blocked release

## Trigger

The release was blocked earlier.

## Outcome

Nothing is grabbed.
