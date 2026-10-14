---
kind: primary
routes:
  web: Web
steps:
- text: The Administrator edits the title, sort title, year or overview of a movie and saves
  kind: actor
  actor: administrator
  entities:
  - {entity: movie, effect: reads, facts: []}
  contexts:
    web:
      place: web::household::title
- text: The Product keeps the values as the movie's own, apart from the catalog's
  kind: product
  actor: administrator
  entities:
  - {entity: movie, effect: changes, facts: [Title, Sort title, Year, Overview]}
  contexts:
    web:
      place: web::household::title
---

# Correct a movie's details

## Trigger

The catalog has a title wrong.

## Outcome

The library shows the corrected details; files are not renamed or moved.
