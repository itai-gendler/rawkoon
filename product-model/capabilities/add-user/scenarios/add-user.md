---
kind: primary
routes:
  web: Web
steps:
- text: The Administrator enters the person's name, email, a password, a language and whether they are an administrator
  kind: actor
  actor: administrator
  entities: []
  contexts:
    web:
      place: web::administration::users
- text: The Product creates the account
  kind: product
  actor: administrator
  entities:
  - {entity: account, effect: creates, facts: [Email, First name, Last name, Password, Language, Administrator access, Created]}
  contexts:
    web:
      place: web::administration::users
---

# Add a user directly

## Trigger

An administrator sets up an account for someone.

## Outcome

The person can sign in with the password they were given.
