---
kind: primary
routes:
  web: Web
steps:
- text: The Member opens the Discover tab and filters by kind, genre or streaming service
  kind: actor
  actor: member
  entities: []
  contexts:
    web:
      place: web::household::browse
- text: The Product lists popular titles from TMDB that match
  kind: product
  actor: member
  entities: []
  contexts:
    web:
      place: web::household::browse
---

# Browse Discover lists

## Trigger

A person wants ideas for something to watch.

## Outcome

The person sees titles to open, watchlist or ask for.
