---
kind: primary
routes:
  web: Web
steps:
- text: The Product finds a monitored wanted movie whose digital release date has passed
  kind: condition
  unattended: true
  entities:
  - {entity: movie, effect: reads, facts: [Digital release date, Monitored, Search attempts]}
  contexts:
    web:
      place: web::household::title
- text: The Product searches with the movie's search titles and grabs the best release the profile allows
  kind: product
  entities:
  - {entity: grab, effect: creates, to: Downloading, facts: [Release title, Indexer, Grabbed, AI pick]}
  - {entity: movie, effect: changes, from: Wanted, to: Downloading, facts: [Search attempts]}
  - {entity: notification, effect: creates, to: Unread, facts: [Title, Body, Kind, Link, Image, Received]}
  contexts:
    web:
      place: web::household::title
---

# Grab a released movie

## Trigger

A wanted movie became available.

## Outcome

The movie is downloading without anyone acting.

## Decision points

### Who picks the release

Is an AI provider configured for scheduled searches, and does more than one release pass the profile and the blocklist?

- Yes → The language model picks among the ten best-scored releases with seeders, and the grab is marked as an AI pick
- No → The classic scorer's best release is grabbed

## Edge cases

- A movie whose digital release date is still ahead is not searched and no attempt is counted.
- A refusal for low free space is not counted as a miss.
