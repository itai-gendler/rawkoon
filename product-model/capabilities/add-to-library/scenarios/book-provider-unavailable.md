---
kind: edge
routes:
  web: Web
steps:
- text: The Administrator adds a book while Google Books does not answer
  kind: actor
  actor: administrator
  entities:
  - {entity: book, effect: reads, facts: []}
  contexts:
    web:
      place: web::household::books
- text: The Product refuses and asks to try again later
  kind: condition
  entities:
  - {entity: integration-settings, effect: reads, facts: [Google Books]}
  contexts:
    web:
      place: web::household::books
---

# Refuse while Google Books is unavailable

## Trigger

The book provider is down.

## Outcome

Nothing is added.
