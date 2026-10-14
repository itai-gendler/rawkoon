---
kind: primary
routes:
  web: Web
steps:
- text: The Administrator removes a file from an edition
  kind: actor
  actor: administrator
  entities: []
  contexts:
    web:
      place: web::household::book
- text: The Product removes the file's record, leaving the file on disk
  kind: product
  actor: administrator
  entities:
  - {entity: book-file, effect: removes}
  contexts:
    web:
      place: web::household::book
---

# Remove a book file

## Trigger

An edition lists a file it should not.

## Outcome

The edition no longer lists the file.
