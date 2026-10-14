---
kind: primary
routes:
  web: Web
steps:
- text: The Administrator picks a book quality profile for an audiobook
  kind: actor
  actor: administrator
  entities:
  - {entity: book-quality-profile, effect: reads, facts: []}
  - {entity: audiobook, effect: reads, facts: []}
  contexts:
    web:
      place: web::household::book
- text: The Product assigns the profile to the edition
  kind: product
  actor: administrator
  entities:
  - {entity: audiobook, effect: changes, facts: [Quality profile]}
  contexts:
    web:
      place: web::household::book
---

# Change an edition's profile

## Trigger

An edition should follow different format rules.

## Outcome

Later searches for that edition use the new profile.
