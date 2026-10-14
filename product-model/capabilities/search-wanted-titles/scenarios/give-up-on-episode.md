---
kind: edge
routes:
  web: Web
steps:
- text: The Product finds nothing suitable for a wanted episode, or for the season pack it belongs to
  kind: condition
  unattended: true
  entities:
  - {entity: episode, effect: reads, facts: [Search attempts]}
  contexts:
    web:
      place: web::household::title
- text: The Product counts the miss against the episode; at the twenty-fourth it marks the episode skipped and notifies everyone who administers the instance
  kind: product
  entities:
  - {entity: episode, effect: changes, from: Wanted, to: Skipped, facts: [Search attempts]}
  - {entity: notification, effect: creates, to: Unread, facts: [Title, Body, Kind, Link, Image, Received]}
  contexts:
    web:
      place: web::household::title
---

# Give up on an episode

## Trigger

No allowed release appears for an aired episode.

## Outcome

The episode is skipped until an administrator retries the season or grabs it.
