---
kind: primary
routes:
  web: Web
steps:
- text: The Product finds no account on the instance and offers the first-run setup
  kind: condition
  entities:
  - {entity: account, effect: reads, facts: []}
  contexts:
    web:
      place: web::sign-in::administrator-setup
- text: The Visitor enters their name, email and a password
  kind: actor
  actor: visitor
  entities: []
  contexts:
    web:
      place: web::sign-in::administrator-setup
- text: The Product creates the account with administration rights and signs the person in
  kind: product
  actor: visitor
  entities:
  - {entity: account, effect: creates, facts: [Email, First name, Last name, Password, Administrator access, Created]}
  contexts:
    web:
      place: web::sign-in::administrator-setup
---

# Create the first administrator

## Trigger

A person opens a freshly installed instance.

## Outcome

The instance has its administrator, who lands on Home signed in.
