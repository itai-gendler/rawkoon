---
kind: primary
routes:
  web: Web
steps:
- text: The Visitor chooses to sign in with a passkey and confirms it on their device
  kind: actor
  actor: visitor
  entities: []
  contexts:
    web:
      place: web::sign-in::sign-in
- text: The Product matches the passkey to the account and starts a session
  kind: product
  actor: visitor
  entities:
  - {entity: account, effect: changes, facts: [Last sign-in]}
  contexts:
    web:
      place: web::sign-in::sign-in
---

# Sign in with a passkey

## Trigger

A person who registered a passkey wants to sign in without a password.

## Outcome

The person is signed in.
