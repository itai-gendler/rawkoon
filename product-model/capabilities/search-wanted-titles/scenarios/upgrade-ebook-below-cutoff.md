---
kind: primary
routes:
  web: Web
steps:
- text: With books on, the Product finds a downloaded ebook whose best file is below its profile's cutoff format
  kind: condition
  unattended: true
  entities:
  - {entity: general-settings, effect: reads, facts: [Books]}
  - {entity: book-quality-profile, effect: reads, facts: [Cutoff format, Allowed formats]}
  - {entity: ebook, effect: reads, facts: []}
  - {entity: book, effect: reads, facts: []}
  contexts:
    web:
      place: web::household::book
- text: The Product grabs a better-format release as an upgrade and marks the ebook upgrading
  kind: product
  entities:
  - {entity: grab, effect: creates, to: Downloading, facts: [Release title, Indexer, Grabbed, Upgrade]}
  - {entity: ebook, effect: changes, from: Downloaded, to: Upgrading, facts: []}
  contexts:
    web:
      place: web::household::book
---

# Upgrade an ebook below its cutoff format

## Trigger

Only a lesser format, such as a pdf, was found before.

## Outcome

The better format is downloading; once imported it replaces the old files.
