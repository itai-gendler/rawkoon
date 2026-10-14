---
kind: validation
routes:
  web: Web
steps:
- text: The Member requests a movie that is already in the library
  kind: actor
  actor: member
  entities:
  - {entity: request, effect: reads, facts: []}
  - {entity: movie, effect: reads, facts: []}
  contexts:
    web:
      place: web::household::browse
- text: The Product refuses because the movie is in the library
  kind: condition
  entities:
  - {entity: movie, effect: reads, facts: [Catalog identity]}
  contexts:
    web:
      place: web::household::browse
---

# Refuse a title already in the library

## Trigger

The title arrived in the meantime.

## Outcome

No request is made.
