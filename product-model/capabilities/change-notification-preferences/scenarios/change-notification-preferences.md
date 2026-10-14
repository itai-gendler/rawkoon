---
kind: primary
routes:
  web: Web
steps:
- text: The Member switches off one of the preference toggles
  kind: actor
  actor: member
  entities: []
  contexts:
    web:
      place: web::household::notification-settings
- text: The Product saves the preference; that kind is no longer sent to them
  kind: product
  actor: member
  entities:
  - {entity: account, effect: changes, facts: [Notification preferences]}
  contexts:
    web:
      place: web::household::notification-settings
---

# Turn a kind of notification off

## Trigger

A person gets notifications they do not want.

## Outcome

Later notifications of that kind are not sent to them.
