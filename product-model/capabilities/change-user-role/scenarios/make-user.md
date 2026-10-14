---
kind: primary
routes:
  web: Web
steps:
- text: The Administrator switches an administrator to user and confirms
  kind: actor
  actor: administrator
  entities: []
  contexts:
    web:
      place: web::administration::users
- text: The Product removes administrator access from the account
  kind: product
  actor: administrator
  entities:
  - {entity: account, effect: changes, facts: [Administrator access]}
  contexts:
    web:
      place: web::administration::users
---

# Make an administrator a regular user

## Trigger

Someone no longer needs to administer the instance.

## Outcome

The person keeps their account as a household member.
