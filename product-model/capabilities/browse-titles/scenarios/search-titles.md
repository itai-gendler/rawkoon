---
kind: primary
routes:
  web: Web
steps:
- text: The Member types part of a title on the Search tab
  kind: actor
  actor: member
  entities: []
  contexts:
    web:
      place: web::household::browse
- text: The Product lists matching movies and shows from TMDB, marking those already in the library
  kind: product
  actor: member
  entities:
  - {entity: movie, effect: reads, facts: [Catalog identity]}
  - {entity: show, effect: reads, facts: [Catalog identity]}
  contexts:
    web:
      place: web::household::browse
---

# Search for a title

## Trigger

A person looks for a particular title.

## Outcome

The person sees matching titles and which ones the library already holds.
