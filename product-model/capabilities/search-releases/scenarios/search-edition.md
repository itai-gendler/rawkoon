---
kind: primary
routes:
  web: Web
steps:
- text: The Administrator chooses Search indexers on an audiobook
  kind: actor
  actor: administrator
  entities:
  - {entity: audiobook, effect: reads, facts: []}
  contexts:
    web:
      place: web::household::book
- text: The Product searches by the book's title and the author's surname and rejects releases missing a title word or the surname, of the other kind, or in a format the profile does not allow
  kind: product
  actor: administrator
  entities:
  - {entity: book, effect: reads, facts: [Title, Authors, Language]}
  - {entity: audiobook, effect: reads, facts: [Quality profile]}
  - {entity: book-quality-profile, effect: reads, facts: [Allowed formats, Minimum audio bitrate, Maximum size, Minimum seeders]}
  - {entity: author, effect: reads, facts: []}
  contexts:
    web:
      place: web::household::book
---

# Search releases for a book edition

## Trigger

An administrator wants a particular release of a book.

## Outcome

The administrator sees the candidates, rejected ones with their reasons.
