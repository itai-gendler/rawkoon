---
kind: primary
routes:
  web: Web
steps:
- text: The Administrator deletes a book quality profile and confirms
  kind: actor
  actor: administrator
  entities:
  - {entity: book-quality-profile, effect: reads, facts: []}
  contexts:
    web:
      place: web::administration::books-settings
- text: The Product deletes the profile and leaves the editions that used it without a profile
  kind: product
  actor: administrator
  entities:
  - {entity: book-quality-profile, effect: removes}
  - {entity: ebook, effect: changes, facts: [Quality profile]}
  contexts:
    web:
      place: web::administration::books-settings
---

# Delete a book quality profile

## Trigger

A book profile is no longer needed.

## Outcome

The profile is gone; its editions fall back to the defaults.
