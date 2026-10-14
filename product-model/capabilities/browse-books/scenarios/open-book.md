---
kind: primary
routes:
  web: Web
steps:
- text: The Member opens a book
  kind: actor
  actor: member
  entities:
  - {entity: book, effect: reads, facts: []}
  contexts:
    web:
      place: web::household::books
- text: The Product presents the book's details, its editions with their state, narrators, duration and files, and the person's read badge
  kind: product
  actor: member
  entities:
  - {entity: book, effect: reads, facts: [Title, Subtitle, Authors, Overview, Cover, Series, Publisher, Page count, Rating, Metadata sources]}
  - {entity: audiobook, effect: reads, facts: [Narrators, Duration, Size on disk]}
  - {entity: book-file, effect: reads, facts: [Format, Size]}
  - {entity: read-badge, effect: reads, facts: [Read on]}
  contexts:
    web:
      place: web::household::book
---

# Open a book

## Trigger

A person wants a book's details.

## Outcome

The person sees what can be listened to or read.
