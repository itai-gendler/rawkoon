---
kind: primary
routes:
  web: Web
steps:
- text: The Administrator saves the provider key, sets the library folders and turns the library switch on
  kind: actor
  actor: administrator
  entities: []
  contexts:
    web:
      place: web::administration::books-settings
- text: The Product stores the key encrypted, saves the folders and turns books on
  kind: product
  actor: administrator
  entities:
  - {entity: integration-settings, effect: changes, facts: [Google Books]}
  - {entity: library-settings, effect: changes, facts: [Books folder, Audiobooks folder]}
  - {entity: general-settings, effect: changes, facts: [Books]}
  - {entity: book, effect: reads, facts: []}
  contexts:
    web:
      place: web::administration::books-settings
---

# Turn the book library on

## Trigger

The household wants books.

## Outcome

Books appear in the navigation, book searches and feeds start, and book settings apply.
