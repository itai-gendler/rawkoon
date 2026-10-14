---
kind: validation
routes:
  web: Web
steps:
- text: The Member opens an ebook that has no EPUB file
  kind: actor
  actor: member
  entities:
  - {entity: ebook, effect: reads, facts: []}
  contexts:
    web:
      place: web::household::book
- text: The Product offers the file for download and states that only EPUB can be read in the app
  kind: condition
  entities:
  - {entity: book-file, effect: reads, facts: [Format]}
  contexts:
    web:
      place: web::household::book
---

# Only EPUB can be read

## Trigger

The edition is a mobi, azw3 or pdf.

## Outcome

The person can download the file but not read it in the app.
