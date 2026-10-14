---
kind: primary
routes:
  web: Web
steps:
- text: The Administrator chooses Remove on a book and confirms
  kind: actor
  actor: administrator
  entities:
  - {entity: book, effect: reads, facts: []}
  contexts:
    web:
      place: web::household::book
- text: The Product removes the book and its editions, leaving their files on disk and their finished grabs seeding
  kind: product
  actor: administrator
  entities:
  - {entity: book, effect: removes}
  - {entity: ebook, effect: removes, from: Downloaded, with: book}
  - {entity: audiobook, effect: removes, from: Wanted, with: book}
  - {entity: grab, effect: reads, facts: []}
  contexts:
    web:
      place: web::household::book
---

# Remove a book

## Trigger

An administrator no longer wants a book.

## Outcome

The book is gone; adding it again and rescanning adopts the files left on disk.
