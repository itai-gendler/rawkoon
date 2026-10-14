---
kind: edge
routes:
  web: Web
steps:
- text: The Administrator chooses Search now
  kind: actor
  actor: administrator
  entities: []
  contexts:
    web:
      place: web::household::title
- text: The Product finds no release the quality profile allows and reports no suitable release
  kind: condition
  entities:
  - {entity: movie, effect: reads, facts: [Quality profile]}
  - {entity: quality-profile, effect: reads, facts: []}
  contexts:
    web:
      place: web::household::title
---

# Nothing suitable is found

## Trigger

No allowed release exists yet.

## Outcome

The movie stays wanted.
