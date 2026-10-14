---
kind: primary
routes:
  web: Web
steps:
- text: The Member chooses Mark as unread
  kind: actor
  actor: member
  entities: []
  contexts:
    web:
      place: web::household::book
- text: The Product removes the person's read badge
  kind: product
  actor: member
  entities:
  - {entity: read-badge, effect: removes}
  contexts:
    web:
      place: web::household::book
---

# Mark a book unread

## Trigger

A person marked the wrong book.

## Outcome

The Read badge is cleared.
