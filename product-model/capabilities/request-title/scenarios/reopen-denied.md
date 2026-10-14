---
kind: primary
routes:
  web: Web
steps:
- text: The Member requests a title whose earlier request was denied
  kind: actor
  actor: member
  entities:
  - {entity: request, effect: reads, facts: []}
  contexts:
    web:
      place: web::household::browse
- text: The Product reopens that request as pending under this person, clears the denial and notifies everyone who administers the instance
  kind: product
  actor: member
  entities:
  - {entity: request, effect: changes, from: Denied, to: Pending, facts: [Deny reason, Decided, Requested]}
  - {entity: notification, effect: creates, to: Unread, facts: [Title, Body, Kind, Link, Image, Received]}
  contexts:
    web:
      place: web::household::browse
---

# Ask again for a denied title

## Trigger

A title was denied before and the person still wants it.

## Outcome

The same request is pending again.
