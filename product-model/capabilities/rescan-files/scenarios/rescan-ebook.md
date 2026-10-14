---
kind: primary
routes:
  web: Web
steps:
- text: The Administrator chooses Rescan files on an ebook
  kind: actor
  actor: administrator
  entities:
  - {entity: ebook, effect: reads, facts: []}
  contexts:
    web:
      place: web::household::book
- text: The Product registers the files in the folder the naming template points at and drops records whose file is gone
  kind: product
  actor: administrator
  entities:
  - {entity: book-file, effect: creates, facts: [Path, File name, Size, Format, Retail, Audio bitrate, Duration, Languages]}
  - {entity: library-settings, effect: reads, facts: [Book naming]}
  contexts:
    web:
      place: web::household::book
---

# Rescan an edition

## Trigger

A book was removed and added again while its files stayed on disk.

## Outcome

The edition has its files back; nothing outside its own folder is picked up.
