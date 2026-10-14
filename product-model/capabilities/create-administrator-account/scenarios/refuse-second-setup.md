---
kind: validation
routes:
  web: Web
steps:
- text: The Visitor opens the sign-in page of an instance that already has accounts
  kind: actor
  actor: visitor
  entities:
  - {entity: account, effect: reads, facts: []}
  contexts:
    web:
      place: web::sign-in::sign-in
- text: The Product finds an account already exists and offers only signing in
  kind: condition
  entities:
  - {entity: account, effect: reads, facts: []}
  contexts:
    web:
      place: web::sign-in::sign-in
---

# Refuse setup once an account exists

## Trigger

A person reaches the sign-in page after the instance was set up.

## Outcome

No new account is created; later accounts come only from administrators.

## Edge cases

- A sign-up attempted directly against the instance after setup is refused the same way.
