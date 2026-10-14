---
kind: primary
routes:
  web: Web
steps:
- text: The Administrator chooses Refresh metadata on a book
  kind: actor
  actor: administrator
  entities:
  - {entity: book, effect: reads, facts: []}
  contexts:
    web:
      place: web::household::book
- text: The Product asks each enabled source in order and keeps, for each field, the value of the highest source that has one, leaving the book's own values in place
  kind: product
  actor: administrator
  entities:
  - {entity: library-settings, effect: reads, facts: [Metadata source order]}
  - {entity: book, effect: changes, facts: [Subtitle, Overview, Cover, Series, Narrators, Genres, Publisher, Page count, Rating, Metadata sources]}
  contexts:
    web:
      place: web::household::book
---

# Refresh a book's metadata

## Trigger

A book is missing details.

## Outcome

The book shows the merged details and how many fields changed.
