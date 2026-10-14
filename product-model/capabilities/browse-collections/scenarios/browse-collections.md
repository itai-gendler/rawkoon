---
kind: primary
routes:
  web: Web
steps:
- text: The Member opens Collections
  kind: actor
  actor: member
  entities: []
  contexts:
    web:
      place: web::household::collections
- text: The Product lists each franchise with a movie in the library and the entries it is missing
  kind: product
  actor: member
  entities:
  - {entity: movie, effect: reads, facts: [Catalog identity]}
  contexts:
    web:
      place: web::household::collections
---

# See franchises with missing entries

## Trigger

A person wants to complete a franchise.

## Outcome

The person sees the missing movies, ready to open.
