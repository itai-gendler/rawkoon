---
kind: primary
routes:
  web: Web
steps:
- text: The Administrator clears an own value
  kind: actor
  actor: administrator
  entities: []
  contexts:
    web:
      place: web::household::title
- text: The Product drops the own value so the catalog's shows again
  kind: product
  actor: administrator
  entities:
  - {entity: movie, effect: changes, facts: [Title]}
  - {entity: show, effect: reads, facts: []}
  contexts:
    web:
      place: web::household::title
---

# Return to the catalog's details

## Trigger

A correction is no longer needed.

## Outcome

The catalog value is back.
