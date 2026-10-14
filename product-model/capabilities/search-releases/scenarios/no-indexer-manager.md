---
kind: edge
routes:
  web: Web
steps:
- text: The Administrator searches with neither Prowlarr nor Jackett configured
  kind: actor
  actor: administrator
  entities: []
  contexts:
    web:
      place: web::household::title
- text: The Product reports that an indexer manager must be enabled
  kind: condition
  entities:
  - {entity: library-settings, effect: reads, facts: [Active indexer manager]}
  contexts:
    web:
      place: web::household::title
---

# No indexer manager is configured

## Trigger

No indexer manager is set up.

## Outcome

No search runs.
