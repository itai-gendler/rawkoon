---
kind: primary
routes:
  web: Web
steps:
- text: The Member changes their first name, last name or profile picture and saves
  kind: actor
  actor: member
  entities: []
  contexts:
    web:
      place: web::household::profile
- text: The Product saves the profile
  kind: product
  actor: member
  entities:
  - {entity: account, effect: changes, facts: [First name, Last name, Avatar]}
  contexts:
    web:
      place: web::household::profile
---

# Edit profile

## Trigger

A person wants their profile to read differently.

## Outcome

The new name and picture appear wherever the person is shown.

## Edge cases

- A picture larger than 5 MB is refused.
