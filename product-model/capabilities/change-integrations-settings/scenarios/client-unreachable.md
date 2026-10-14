---
kind: edge
routes:
  web: Web
steps:
- text: The Administrator tests a download client connection
  kind: actor
  actor: administrator
  entities: []
  contexts:
    web:
      place: web::administration::integrations
- text: The Product reports the client cannot be reached
  kind: condition
  entities:
  - {entity: integration-settings, effect: reads, facts: [Download client]}
  contexts:
    web:
      place: web::administration::integrations
---

# The download client does not answer

## Trigger

The address or credentials are wrong.

## Outcome

The administrator fixes them before relying on the client.
