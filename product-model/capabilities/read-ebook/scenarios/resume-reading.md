---
kind: primary
routes:
  web: Web
  iphone: iPhone
steps:
- text: The Member chooses Read on an ebook with an EPUB file
  kind: actor
  actor: member
  entities:
  - {entity: ebook, effect: reads, facts: []}
  contexts:
    web:
      place: web::household::book
    iphone:
      place: iphone::household::book
- text: The Product opens the EPUB at the saved chapter, trusting the chapter's path over its index when the chapters were reordered
  kind: product
  actor: member
  entities:
  - {entity: book-file, effect: reads, facts: [Format]}
  - {entity: reading-progress, effect: reads, facts: [Chapter path, Chapter index, Offset]}
  contexts:
    web:
      place: web::household::read
    iphone:
      place: iphone::household::reader
- text: The Member reads
  kind: actor
  actor: member
  entities: []
  contexts:
    web:
      place: web::household::read
    iphone:
      place: iphone::household::reader
- text: The Product records the new position as the person reads
  kind: product
  actor: member
  entities:
  - {entity: reading-progress, effect: changes, facts: [Chapter path, Chapter index, Chapter count, Offset, Finished, Updated]}
  contexts:
    web:
      place: web::household::read
    iphone:
      place: iphone::household::reader
---

# Resume reading

## Trigger

A person wants to continue a book.

## Outcome

The person picks up where they stopped.

## Edge cases

- When the saved chapter no longer exists the reader opens at the top of the nearest chapter.
- An older position from another device never replaces a newer one.
