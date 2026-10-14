---
kind: primary
routes:
  web: Web
steps:
- text: The Administrator edits a book's title, series, narrators, publisher or other details and saves
  kind: actor
  actor: administrator
  entities:
  - {entity: book, effect: reads, facts: []}
  contexts:
    web:
      place: web::household::book
- text: The Product keeps the values as the book's own, winning over every metadata source
  kind: product
  actor: administrator
  entities:
  - {entity: book, effect: changes, facts: [Title, Subtitle, Series, Narrators, Genres, Publisher, Page count, Published, Language, Overview, Cover, ISBN]}
  contexts:
    web:
      place: web::household::book
---

# Correct a book's details

## Trigger

The merged book metadata is wrong.

## Outcome

The book shows the corrected details; authors are managed from the author pages.
