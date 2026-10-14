---
kind: validation
routes:
  web: Web
steps:
- text: The Administrator enters an email that already has an account
  kind: actor
  actor: administrator
  entities:
  - {entity: account, effect: reads, facts: []}
  contexts:
    web:
      place: web::administration::users
- text: The Product refuses the invitation
  kind: condition
  entities:
  - {entity: account, effect: reads, facts: [Email]}
  - {entity: invitation, effect: reads, facts: []}
  contexts:
    web:
      place: web::administration::users
---

# Refuse an address that already has an account

## Trigger

An administrator invites an existing user.

## Outcome

No invitation is created.
