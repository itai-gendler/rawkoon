---
kind: edge
routes:
  web: Web
steps:
- text: The Product finds nothing suitable for a wanted movie
  kind: condition
  unattended: true
  entities:
  - {entity: movie, effect: reads, facts: [Search attempts]}
  contexts:
    web:
      place: web::household::title
- text: The Product counts the miss; at the twenty-fourth it marks the movie skipped and notifies everyone who administers the instance
  kind: product
  entities:
  - {entity: movie, effect: changes, from: Wanted, to: Skipped, facts: [Search attempts]}
  - {entity: notification, effect: creates, to: Unread, facts: [Title, Body, Kind, Link, Image, Received]}
  contexts:
    web:
      place: web::household::title
---

# Give up after repeated misses

## Trigger

No allowed release exists for days.

## Outcome

The movie is skipped until an administrator searches or retries.
