---
kind: primary
routes:
  web: Web
steps:
- text: The Administrator switches a user to administrator and confirms
  kind: actor
  actor: administrator
  entities: []
  contexts:
    web:
      place: web::administration::users
- text: The Product gives the account administrator access
  kind: product
  actor: administrator
  entities:
  - {entity: account, effect: changes, facts: [Administrator access]}
  contexts:
    web:
      place: web::administration::users
---

# Make someone an administrator

## Trigger

A household member should help run the instance.

## Outcome

The person reaches the administration area from their next request.
