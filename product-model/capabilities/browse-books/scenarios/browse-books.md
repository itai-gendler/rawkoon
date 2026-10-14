---
kind: primary
routes:
  web: Web
steps:
- text: The Member opens Books and searches or sorts
  kind: actor
  actor: member
  entities:
  - {entity: book, effect: reads, facts: []}
  contexts:
    web:
      place: web::household::books
- text: The Product lists the books with the state of each edition
  kind: product
  actor: member
  entities:
  - {entity: book, effect: reads, facts: [Title, Authors, Cover, Published]}
  - {entity: ebook, effect: reads, facts: []}
  - {entity: audiobook, effect: reads, facts: []}
  contexts:
    web:
      place: web::household::books
---

# Browse the book library

## Trigger

A person looks for something to read or listen to.

## Outcome

The person sees the books and which editions are downloaded.
