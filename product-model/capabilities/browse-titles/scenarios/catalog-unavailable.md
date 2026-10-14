---
kind: edge
routes:
  web: Web
steps:
- text: The Member opens Browse on an instance without a TMDB key
  kind: actor
  actor: member
  entities: []
  contexts:
    web:
      place: web::household::browse
- text: The Product lists no catalog results
  kind: condition
  entities:
  - {entity: integration-settings, effect: reads, facts: [TMDB]}
  contexts:
    web:
      place: web::household::browse
---

# TMDB is not configured

## Trigger

The administrator has not connected TMDB.

## Outcome

Browse stays empty until TMDB is configured.
