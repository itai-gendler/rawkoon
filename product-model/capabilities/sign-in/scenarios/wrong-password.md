---
kind: validation
routes:
  web: Web
steps:
- text: The Visitor enters an email and a wrong password
  kind: actor
  actor: visitor
  entities: []
  contexts:
    web:
      place: web::sign-in::sign-in
- text: The Product refuses the sign-in and starts no session
  kind: product
  entities:
  - {entity: account, effect: reads, facts: [Email]}
  contexts:
    web:
      place: web::sign-in::sign-in
---

# Refuse a wrong password

## Trigger

A person mistypes their password.

## Outcome

The person stays on the sign-in page, not signed in.
