---
kind: primary
routes:
  web: Web
steps:
- text: The Administrator chooses Regenerate link on a pending or expired invitation
  kind: actor
  actor: administrator
  entities:
  - {entity: invitation, effect: reads, facts: []}
  contexts:
    web:
      place: web::administration::users
- text: The Product replaces the link, restarts the seven days and displays the new link once
  kind: product
  actor: administrator
  entities:
  - {entity: invitation, effect: changes, facts: [Link, Expires]}
  contexts:
    web:
      place: web::administration::users
---

# Regenerate the link

## Trigger

An invitation link was lost or expired.

## Outcome

Only the new link works.
