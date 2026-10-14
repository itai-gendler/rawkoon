---
kind: edge
routes:
  web: Web
steps:
- text: The Administrator refreshes while one source does not answer
  kind: actor
  actor: administrator
  entities: []
  contexts:
    web:
      place: web::household::book
- text: The Product updates the fields the other sources supply and names the unavailable source, without treating it as having no data
  kind: product
  actor: administrator
  entities:
  - {entity: book, effect: changes, facts: [Overview, Metadata sources]}
  contexts:
    web:
      place: web::household::book
---

# A source is unavailable

## Trigger

A provider is down.

## Outcome

The next refresh asks that source again.
