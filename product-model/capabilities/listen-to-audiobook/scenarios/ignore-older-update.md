---
kind: edge
routes:
  web: Web
steps:
- text: The Member listens on a device that was offline while they listened elsewhere
  kind: actor
  actor: member
  entities: []
  contexts:
    web:
      place: web::household::listen
- text: The Product receives a position recorded earlier than the one it keeps
  kind: condition
  entities:
  - {entity: listening-progress, effect: reads, facts: [Updated]}
  contexts:
    web:
      place: web::household::listen
- text: The Product keeps the newer position
  kind: product
  actor: member
  entities: []
  contexts:
    web:
      place: web::household::listen
---

# Ignore an older position from another device

## Trigger

A device that was offline reports an old position.

## Outcome

The person is never walked backwards by another device.
