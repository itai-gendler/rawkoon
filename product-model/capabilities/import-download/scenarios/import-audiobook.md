---
kind: primary
routes:
  web: Web
steps:
- text: The Product picks up a completed audiobook grab
  kind: condition
  unattended: true
  entities:
  - {entity: grab, effect: reads, facts: [Release title]}
  - {entity: audiobook, effect: reads, facts: []}
  contexts:
    web:
      place: web::household::book
- text: The Product places the files in the folder the audiobook naming template renders, keeping track names, reads narrators and duration from the tags and lays the chapters on the whole-book timeline
  kind: product
  entities:
  - {entity: library-settings, effect: reads, facts: [Audiobook naming, Audiobooks folder]}
  - {entity: book-file, effect: creates, facts: [Path, File name, Size, Format, Retail, Audio bitrate, Duration, Languages]}
  - {entity: audiobook, effect: changes, from: Downloading, to: Downloaded, facts: [Narrators, Duration, Chapters, Offline ready]}
  - {entity: grab, effect: changes, from: Completed, to: Imported, facts: [Library path]}
  - {entity: notification, effect: creates, to: Unread, facts: [Title, Body, Kind, Link, Image, Received]}
  - {entity: book, effect: reads, facts: []}
  contexts:
    web:
      place: web::household::book
---

# Import an audiobook

## Trigger

An audiobook download finished.

## Outcome

The audiobook is downloaded and can be played; with chapter files it can be downloaded to an iPhone.

## Edge cases

- An upgrade deletes the edition's previous files from disk.
