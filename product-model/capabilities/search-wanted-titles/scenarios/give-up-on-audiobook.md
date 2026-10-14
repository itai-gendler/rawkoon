---
kind: edge
routes:
  web: Web
steps:
- text: With books on, the Product finds nothing suitable for a wanted audiobook
  kind: condition
  unattended: true
  entities:
  - {entity: general-settings, effect: reads, facts: [Books]}
  - {entity: audiobook, effect: reads, facts: [Search attempts]}
  - {entity: book, effect: reads, facts: []}
  contexts:
    web:
      place: web::household::book
- text: The Product counts the miss; after repeated misses it marks the audiobook skipped and notifies everyone who administers the instance
  kind: product
  entities:
  - {entity: audiobook, effect: changes, from: Wanted, to: Skipped, facts: [Search attempts]}
  - {entity: notification, effect: creates, to: Unread, facts: [Title, Body, Kind, Link, Image, Received]}
  contexts:
    web:
      place: web::household::book
---

# Give up on an audiobook

## Trigger

No allowed release appears for an audiobook.

## Outcome

The audiobook is skipped until an administrator searches for it by hand.
