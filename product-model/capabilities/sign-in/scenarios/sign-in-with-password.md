---
kind: primary
routes:
  web: Web
  iphone: iPhone
steps:
- text: The Visitor enters their email and password
  kind: actor
  actor: visitor
  entities: []
  contexts:
    web:
      place: web::sign-in::sign-in
    iphone:
      place: iphone::sign-in::sign-in
- text: The Product checks the password against the account and starts a session for thirty days
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

# Sign in with email and password

## Trigger

A person wants to use the instance.

## Outcome

The person is signed in and lands on Home.

## Edge cases

- In the iPhone app the person first enters the instance's address; the app talks only to that instance.
