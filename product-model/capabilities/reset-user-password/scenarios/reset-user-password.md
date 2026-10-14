---
kind: primary
routes:
  web: Web
steps:
- text: The Administrator enters a new password of at least eight characters for a user
  kind: actor
  actor: administrator
  entities: []
  contexts:
    web:
      place: web::administration::users
- text: The Product saves the password and ends every session the person has
  kind: product
  actor: administrator
  entities:
  - {entity: account, effect: changes, facts: [Password]}
  contexts:
    web:
      place: web::administration::users
---

# Reset a user's password

## Trigger

Someone forgot their password.

## Outcome

The person signs in again with the new password.
