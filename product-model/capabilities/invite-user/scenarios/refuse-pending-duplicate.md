---
kind: validation
routes:
  web: Web
steps:
- text: The Administrator invites an address that already has a pending invitation
  kind: actor
  actor: administrator
  entities:
  - {entity: invitation, effect: reads, facts: []}
  contexts:
    web:
      place: web::administration::users
- text: The Product refuses because a pending invitation already exists
  kind: condition
  entities:
  - {entity: invitation, effect: reads, facts: [Email, Expires]}
  contexts:
    web:
      place: web::administration::users
---

# Refuse a second pending invitation

## Trigger

An administrator invites the same address twice.

## Outcome

The existing invitation stays the only pending one; regenerating its link is the way to resend.
