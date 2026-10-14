---
kind: primary
routes:
  web: Web
steps:
- text: The Administrator chooses Remove from history on a failed grab
  kind: actor
  actor: administrator
  entities:
  - {entity: grab, effect: reads, facts: []}
  contexts:
    web:
      place: web::household::title
- text: The Product deletes the grab and resolves its open attention alert
  kind: product
  actor: administrator
  entities:
  - {entity: grab, effect: removes, from: Failed}
  - {entity: attention-alert, effect: changes, from: Open, to: Resolved, facts: []}
  contexts:
    web:
      place: web::household::title
---

# Remove a failed entry from history

## Trigger

A failure was dealt with.

## Outcome

The history no longer lists it.

## Edge cases

- Only failed downloads and downloads whose import failed can be removed from history this way.
