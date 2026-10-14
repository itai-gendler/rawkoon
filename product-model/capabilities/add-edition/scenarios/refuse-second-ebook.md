---
kind: validation
routes:
  web: Web
steps:
- text: The Administrator adds an edition the book already has
  kind: actor
  actor: administrator
  entities:
  - {entity: book, effect: reads, facts: []}
  contexts:
    web:
      place: web::household::book
- text: The Product refuses
  kind: condition
  entities:
  - {entity: ebook, effect: reads, facts: []}
  contexts:
    web:
      place: web::household::book
---

# Refuse an edition the book already has

## Trigger

A book can have one ebook and one audiobook.

## Outcome

Nothing is added.
