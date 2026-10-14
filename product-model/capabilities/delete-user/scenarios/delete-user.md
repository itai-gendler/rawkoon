---
kind: primary
routes:
  web: Web
steps:
- text: The Administrator deletes another person's account and confirms
  kind: actor
  actor: administrator
  entities:
  - {entity: account, effect: reads, facts: []}
  contexts:
    web:
      place: web::administration::users
- text: The Product deletes the account together with its notifications, watchlist and progress
  kind: product
  actor: administrator
  entities:
  - {entity: account, effect: removes}
  - {entity: notification, effect: reads, facts: []}
  contexts:
    web:
      place: web::administration::users
---

# Delete a user

## Trigger

Someone should no longer use the instance.

## Outcome

The person can no longer sign in; their requests go with them.
