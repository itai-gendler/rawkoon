---
kind: primary
routes:
  web: Web
steps:
- text: The Product picks up a completed ebook grab
  kind: condition
  unattended: true
  entities:
  - {entity: grab, effect: reads, facts: [Release title]}
  - {entity: ebook, effect: reads, facts: []}
  contexts:
    web:
      place: web::household::book
- text: The Product keeps every format the edition's profile allows as files of the ebook, placed by the book naming template, and drops the rest
  kind: product
  entities:
  - {entity: library-settings, effect: reads, facts: [Book naming, Books folder]}
  - {entity: book-file, effect: creates, facts: [Path, File name, Size, Format, Retail, Audio bitrate, Duration, Languages]}
  - {entity: ebook, effect: changes, from: Downloading, to: Downloaded, facts: []}
  - {entity: grab, effect: changes, from: Completed, to: Imported, facts: [Library path]}
  - {entity: notification, effect: creates, to: Unread, facts: [Title, Body, Kind, Link, Image, Received]}
  - {entity: book, effect: reads, facts: []}
  contexts:
    web:
      place: web::household::book
---

# Import an ebook

## Trigger

An ebook download finished.

## Outcome

The ebook is downloaded; an EPUB among its files can be read in the app.

## Edge cases

- An upgrade deletes the edition's previous files from disk.
