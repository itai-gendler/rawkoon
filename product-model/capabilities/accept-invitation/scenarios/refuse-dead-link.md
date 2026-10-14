---
kind: validation
routes:
  web: Web
steps:
- text: The Visitor opens an invitation link
  kind: actor
  actor: visitor
  entities:
  - {entity: invitation, effect: reads, facts: []}
  contexts:
    web:
      place: web::sign-in::accept-invitation
- text: The Product finds the link revoked, used or past its expiry and refuses it
  kind: condition
  entities:
  - {entity: invitation, effect: reads, facts: [Expires]}
  contexts:
    web:
      place: web::sign-in::accept-invitation
---

# Refuse an expired or withdrawn link

## Trigger

A person follows a link that no longer works.

## Outcome

No account is created; the person is told the invitation is invalid or expired.
