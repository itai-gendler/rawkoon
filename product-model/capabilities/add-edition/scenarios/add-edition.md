---
kind: primary
routes:
  web: Web
steps:
- text: The Administrator chooses Add audiobook on a book that only has an ebook
  kind: actor
  actor: administrator
  entities:
  - {entity: audiobook, effect: reads, facts: []}
  - {entity: ebook, effect: reads, facts: []}
  - {entity: book, effect: reads, facts: []}
  contexts:
    web:
      place: web::household::book
- text: The Product adds the audiobook edition, wanted and monitored, with a book quality profile for audiobooks
  kind: product
  actor: administrator
  entities:
  - {entity: audiobook, effect: creates, to: Wanted, facts: [Monitored, Quality profile]}
  - {entity: book-quality-profile, effect: reads, facts: []}
  contexts:
    web:
      place: web::household::book
---

# Add the audiobook edition

## Trigger

The household wants to listen to a book it has as an ebook.

## Outcome

The audiobook is wanted and will be searched for.
