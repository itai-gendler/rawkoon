---
kind: primary
routes:
  web: Web
steps:
- text: The Member enters their current password and a new one of at least eight characters
  kind: actor
  actor: member
  entities: []
  contexts:
    web:
      place: web::household::profile
- text: The Product checks the current password and saves the new one
  kind: product
  actor: member
  entities:
  - {entity: account, effect: changes, facts: [Password]}
  contexts:
    web:
      place: web::household::profile
---

# Change password

## Trigger

A person wants a new password.

## Outcome

The new password works for the next sign-in.
