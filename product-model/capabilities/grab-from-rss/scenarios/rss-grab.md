---
kind: primary
routes:
  web: Web
steps:
- text: The Product finds a new feed release that matches a monitored wanted movie and passes its profile and the blocklist
  kind: condition
  unattended: true
  entities:
  - {entity: integration-settings, effect: reads, facts: [Prowlarr, Jackett]}
  - {entity: movie, effect: reads, facts: [Monitored]}
  contexts:
    web:
      place: web::household::title
- text: The Product grabs it
  kind: product
  entities:
  - {entity: grab, effect: creates, to: Downloading, facts: [Release title, Indexer, Grabbed, AI pick]}
  - {entity: movie, effect: changes, from: Wanted, to: Downloading, facts: []}
  contexts:
    web:
      place: web::household::title
---

# Grab a matching feed release

## Trigger

A release appears in an indexer's feed.

## Outcome

The movie is downloading minutes after the release appeared.
