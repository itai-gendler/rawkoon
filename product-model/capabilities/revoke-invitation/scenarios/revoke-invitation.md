---
kind: primary
routes:
  web: Web
steps:
- text: The Administrator revokes a pending invitation and confirms
  kind: actor
  actor: administrator
  entities:
  - {entity: invitation, effect: reads, facts: []}
  contexts:
    web:
      place: web::administration::users
- text: The Product marks the invitation revoked
  kind: product
  actor: administrator
  entities:
  - {entity: invitation, effect: changes, from: Pending, to: Revoked, facts: []}
  contexts:
    web:
      place: web::administration::users
---

# Revoke an invitation

## Trigger

An administrator no longer wants the invitee to join.

## Outcome

The link no longer creates an account.
