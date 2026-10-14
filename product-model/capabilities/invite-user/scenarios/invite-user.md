---
kind: primary
routes:
  web: Web
steps:
- text: The Administrator enters an email, picks a language and whether the person will be an administrator
  kind: actor
  actor: administrator
  entities: []
  contexts:
    web:
      place: web::administration::users
- text: The Product creates the invitation with a link that expires in seven days and displays the link once
  kind: product
  actor: administrator
  entities:
  - {entity: invitation, effect: creates, to: Pending, facts: [Email, Language, Administrator, Link, Expires, Created]}
  contexts:
    web:
      place: web::administration::users
---

# Generate an invitation link

## Trigger

An administrator wants someone in the household to have an account.

## Outcome

The administrator has a link to send; the invitation is listed as pending.

## Edge cases

- Rawkoon sends no email; the administrator shares the link themselves.
