---
kind: primary
routes:
  web: Web
steps:
- text: With books on, the Product finds a feed release in the book or audio categories that matches a wanted audiobook
  kind: condition
  unattended: true
  entities:
  - {entity: general-settings, effect: reads, facts: [Books]}
  - {entity: audiobook, effect: reads, facts: [Monitored]}
  - {entity: book, effect: reads, facts: []}
  contexts:
    web:
      place: web::household::book
- text: The Product grabs it
  kind: product
  entities:
  - {entity: grab, effect: creates, to: Downloading, facts: [Release title, Indexer, Grabbed]}
  - {entity: audiobook, effect: changes, from: Wanted, to: Downloading, facts: []}
  contexts:
    web:
      place: web::household::book
---

# Grab a matching book release

## Trigger

A book release appears in a feed.

## Outcome

The edition is downloading.
