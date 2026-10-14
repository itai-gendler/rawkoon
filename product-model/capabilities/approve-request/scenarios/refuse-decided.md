---
kind: validation
routes:
  web: Web
steps:
- text: The Administrator approves a request another administrator already decided
  kind: actor
  actor: administrator
  entities:
  - {entity: request, effect: reads, facts: []}
  contexts:
    web:
      place: web::household::requests
- text: 'The Product refuses: the request is not pending'
  kind: condition
  actor: administrator
  entities:
  - {entity: request, effect: reads, facts: []}
  contexts:
    web:
      place: web::household::requests
---

# Refuse a request that is no longer pending

## Trigger

Two administrators act on the same request.

## Outcome

The first decision stands.

## Edge cases

- A quality profile that no longer exists is refused before anything is added.
