---
kind: primary
routes:
  web: Web
  iphone: iPhone
steps:
- text: The Visitor chooses a single sign-on provider and signs in there
  kind: actor
  actor: visitor
  entities: []
  contexts:
    web:
      place: web::sign-in::sign-in
    iphone:
      place: iphone::sign-in::sign-in
- text: The Product links the provider's identity to the existing account with that email and starts a session
  kind: product
  actor: visitor
  entities:
  - {entity: account, effect: changes, facts: [Last sign-in]}
  contexts:
    web:
      place: web::sign-in::sign-in
    iphone:
      place: iphone::sign-in::sign-in
---

# Sign in with a single sign-on provider

## Trigger

The instance has a single sign-on provider configured.

## Outcome

The person is signed in through the provider.

## Edge cases

- A provider identity with no matching account is refused; providers never create accounts.
