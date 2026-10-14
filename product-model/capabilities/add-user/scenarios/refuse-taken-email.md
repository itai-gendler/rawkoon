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
- text: The Product refuses
  kind: condition
  entities:
  - {entity: account, effect: reads, facts: [Email]}
  contexts:
    web:
      place: web::administration::users
---

# Refuse an email already in use

## Trigger

The address is taken.

## Outcome

No account is created.

## Edge cases

- A malformed email or a password shorter than eight characters is refused.
