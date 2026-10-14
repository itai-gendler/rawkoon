---
kind: edge
routes:
  web: Web
steps:
- text: The Administrator adds a title on an instance without a TMDB key
  kind: actor
  actor: administrator
  entities: []
  contexts:
    web:
      place: web::household::browse
- text: The Product refuses because TMDB is not configured
  kind: condition
  entities:
  - {entity: integration-settings, effect: reads, facts: [TMDB]}
  contexts:
    web:
      place: web::household::browse
---

# Refuse when TMDB is not configured

## Trigger

TMDB has not been connected.

## Outcome

Nothing is added.
