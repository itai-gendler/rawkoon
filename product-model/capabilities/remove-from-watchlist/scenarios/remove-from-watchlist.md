---
kind: primary
routes:
  web: Web
steps:
- text: The Member removes a title from their Watchlist
  kind: actor
  actor: member
  entities: []
  contexts:
    web:
      place: web::household::watchlist
- text: The Product deletes the watchlist item
  kind: product
  actor: member
  entities:
  - {entity: watchlist-item, effect: removes}
  contexts:
    web:
      place: web::household::watchlist
---

# Remove a title from the watchlist

## Trigger

A person watched it or lost interest.

## Outcome

The title is gone from their watchlist.
