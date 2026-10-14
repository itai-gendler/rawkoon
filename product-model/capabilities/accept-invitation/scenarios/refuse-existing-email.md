---
kind: validation
routes:
  web: Web
steps:
- text: The Visitor submits the invitation form
  kind: actor
  actor: visitor
  entities:
  - {entity: invitation, effect: reads, facts: []}
  contexts:
    web:
      place: web::sign-in::accept-invitation
- text: The Product finds an account with the invitation's email and refuses
  kind: condition
  entities:
  - {entity: account, effect: reads, facts: [Email]}
  - {entity: invitation, effect: reads, facts: [Email]}
  contexts:
    web:
      place: web::sign-in::accept-invitation
---

# Refuse when the email already has an account

## Trigger

The invited address got an account in the meantime.

## Outcome

No second account is created.
