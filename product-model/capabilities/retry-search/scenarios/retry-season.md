---
kind: primary
routes:
  web: Web
steps:
- text: The Administrator retries the skipped episodes of a season
  kind: actor
  actor: administrator
  entities:
  - {entity: episode, effect: reads, facts: []}
  contexts:
    web:
      place: web::household::title
- text: The Product makes each skipped episode of the season wanted again
  kind: product
  actor: administrator
  entities:
  - {entity: episode, effect: changes, from: Skipped, to: Wanted, facts: [Search attempts]}
  contexts:
    web:
      place: web::household::title
---

# Retry a season's skipped episodes

## Trigger

A season's episodes were given up on.

## Outcome

The episodes are searched again.
