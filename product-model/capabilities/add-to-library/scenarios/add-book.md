---
kind: primary
routes:
  web: Web
steps:
- text: The Administrator searches by title, author or ISBN in Add a book and picks the editions to add it as
  kind: actor
  actor: administrator
  entities:
  - {entity: author, effect: reads, facts: []}
  - {entity: book, effect: reads, facts: []}
  contexts:
    web:
      place: web::household::books
- text: The Product adds the book with each chosen edition, wanted and monitored, giving each edition the book quality profile for its kind
  kind: product
  actor: administrator
  entities:
  - {entity: book, effect: creates, facts: [Title, Subtitle, Authors, Overview, Cover, Language, Published, ISBN, Catalog identity, Added]}
  - {entity: ebook, effect: creates, to: Wanted, facts: [Monitored, Quality profile], with: book}
  - {entity: audiobook, effect: creates, to: Wanted, facts: [Monitored, Quality profile], with: book}
  - {entity: book-quality-profile, effect: reads, facts: []}
  contexts:
    web:
      place: web::household::books
---

# Add a book

## Trigger

An administrator wants a book in the library.

## Outcome

The book is in the library with its wanted editions; with no edition chosen it arrives as an ebook.

## Edge cases

- A volume already in the library is shown as In library and is not added twice.
