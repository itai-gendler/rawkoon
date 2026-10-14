---
kind: primary
routes:
  web: Web
steps:
- text: The Administrator chooses Use default
  kind: actor
  actor: administrator
  entities: []
  contexts:
    web:
      place: web::household::title
- text: The Product returns to the catalog's backdrop
  kind: product
  actor: administrator
  entities:
  - {entity: show, effect: changes, facts: [Backdrop]}
  contexts:
    web:
      place: web::household::title
---

# Use the default artwork

## Trigger

A picked artwork should go.

## Outcome

The catalog's artwork is displayed again.
