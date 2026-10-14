---
kind: primary
routes:
  web: Web
steps:
- text: The Member chooses Mark as read and confirms
  kind: actor
  actor: member
  entities: []
  contexts:
    web:
      place: web::household::book
- text: The Product records the read badge for the person and clears their ebook and audiobook positions for the book
  kind: product
  actor: member
  entities:
  - {entity: read-badge, effect: creates, facts: [Read on]}
  - {entity: listening-progress, effect: removes}
  - {entity: reading-progress, effect: removes}
  - {entity: audiobook, effect: reads, facts: []}
  - {entity: ebook, effect: reads, facts: []}
  - {entity: book, effect: reads, facts: []}
  contexts:
    web:
      place: web::household::book
---

# Mark a book read

## Trigger

A person finished a book.

## Outcome

The book carries their Read badge and starts from the beginning next time.
