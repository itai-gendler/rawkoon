---
kind: primary
routes:
  web: Web
steps:
- text: The Administrator opens Artwork and picks a poster, optionally filtered by language
  kind: actor
  actor: administrator
  entities: []
  contexts:
    web:
      place: web::household::title
- text: The Product uses the picked poster for the show
  kind: product
  actor: administrator
  entities:
  - {entity: show, effect: changes, facts: [Poster]}
  contexts:
    web:
      place: web::household::title
---

# Pick a poster

## Trigger

The default poster is not the one the household likes.

## Outcome

The library displays the picked poster.
