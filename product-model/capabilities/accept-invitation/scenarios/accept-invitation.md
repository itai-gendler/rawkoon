---
kind: primary
routes:
  web: Web
steps:
- text: The Product opens the invitation from its link and fills in its email
  kind: condition
  entities:
  - {entity: invitation, effect: reads, facts: [Email, Expires]}
  contexts:
    web:
      place: web::sign-in::accept-invitation
- text: The Visitor enters their name and a password
  kind: actor
  actor: visitor
  entities: []
  contexts:
    web:
      place: web::sign-in::accept-invitation
- text: The Product creates the account with the invitation's email, role and language, accepts the invitation and signs the person in
  kind: product
  actor: visitor
  entities:
  - {entity: account, effect: creates, facts: [Email, First name, Last name, Password, Administrator access, Language, Created]}
  - {entity: invitation, effect: changes, from: Pending, to: Accepted, facts: [Accepted]}
  contexts:
    web:
      place: web::sign-in::accept-invitation
---

# Accept an invitation

## Trigger

A person received an invitation link from an administrator.

## Outcome

The person has an account and lands on Home signed in.
