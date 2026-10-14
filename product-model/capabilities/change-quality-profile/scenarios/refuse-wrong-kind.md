---
kind: validation
routes:
  web: Web
steps:
- text: The Administrator picks an ebook-only profile for an audiobook
  kind: actor
  actor: administrator
  entities:
  - {entity: audiobook, effect: reads, facts: []}
  - {entity: ebook, effect: reads, facts: []}
  contexts:
    web:
      place: web::household::book
- text: 'The Product refuses: a profile scoped to one kind is never used for the other'
  kind: condition
  entities:
  - {entity: book-quality-profile, effect: reads, facts: [Kind]}
  contexts:
    web:
      place: web::household::book
---

# Refuse a profile for the other kind

## Trigger

The chosen profile is for ebooks.

## Outcome

The edition keeps its profile.
