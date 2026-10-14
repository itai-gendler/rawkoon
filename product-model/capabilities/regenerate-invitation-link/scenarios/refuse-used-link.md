---
kind: validation
routes:
  web: Web
steps:
- text: The Administrator tries to regenerate an accepted or revoked invitation
  kind: actor
  actor: administrator
  entities:
  - {entity: invitation, effect: reads, facts: []}
  contexts:
    web:
      place: web::administration::users
- text: 'The Product refuses: only pending invitations are regenerated'
  kind: condition
  entities:
  - {entity: invitation, effect: reads, facts: []}
  contexts:
    web:
      place: web::administration::users
---

# Refuse an accepted or revoked invitation

## Trigger

The invitation is no longer pending.

## Outcome

Nothing changes.
