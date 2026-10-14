---
kind: validation
routes:
  web: Web
steps:
- text: The Member requests a title someone already requested
  kind: actor
  actor: member
  entities:
  - {entity: request, effect: reads, facts: []}
  contexts:
    web:
      place: web::household::browse
- text: The Product finds a pending or approved request for it and reports it as already requested
  kind: condition
  actor: member
  entities:
  - {entity: request, effect: reads, facts: []}
  contexts:
    web:
      place: web::household::browse
---

# Refuse a title already requested

## Trigger

Two people want the same title.

## Outcome

One request stays; the household shares it.
