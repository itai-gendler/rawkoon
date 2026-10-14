---
kind: primary
routes:
  web: Web
steps:
- text: The Administrator chooses Retry search on a skipped movie
  kind: actor
  actor: administrator
  entities:
  - {entity: movie, effect: reads, facts: []}
  contexts:
    web:
      place: web::household::title
- text: The Product makes the movie wanted again with no search attempts
  kind: product
  actor: administrator
  entities:
  - {entity: movie, effect: changes, from: Skipped, to: Wanted, facts: [Search attempts]}
  contexts:
    web:
      place: web::household::title
---

# Retry a skipped movie

## Trigger

Releases may exist now that automatic searching gave up.

## Outcome

The next scheduled search looks for the movie again.
