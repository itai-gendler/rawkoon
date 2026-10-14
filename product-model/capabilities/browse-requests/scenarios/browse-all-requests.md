---
kind: primary
routes:
  web: Web
steps:
- text: The Administrator opens Requests
  kind: actor
  actor: administrator
  entities:
  - {entity: request, effect: reads, facts: []}
  contexts:
    web:
      place: web::household::requests
- text: The Product lists every person's requests with who asked
  kind: product
  actor: administrator
  entities:
  - {entity: request, effect: reads, facts: [Kind, Title, Year, Poster, Requested]}
  contexts:
    web:
      place: web::household::requests
---

# See every request

## Trigger

An administrator reviews what the household wants.

## Outcome

The administrator sees all requests and can decide the pending ones.
