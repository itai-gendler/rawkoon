---
kind: primary
routes:
  web: Web
  iphone: iPhone
steps:
- text: The Administrator denies a pending request, optionally giving a reason
  kind: actor
  actor: administrator
  entities:
  - {entity: request, effect: reads, facts: []}
  contexts:
    web:
      place: web::household::requests
    iphone:
      place: iphone::household::requests
- text: The Product marks the request denied and notifies the requester with the reason
  kind: product
  actor: administrator
  entities:
  - {entity: request, effect: changes, from: Pending, to: Denied, facts: [Deny reason, Decided]}
  - {entity: notification, effect: creates, to: Unread, facts: [Title, Body, Kind, Link, Image, Received]}
  contexts:
    web:
      place: web::household::requests
    iphone:
      place: iphone::household::requests
---

# Deny a request

## Trigger

An administrator will not get the title.

## Outcome

The requester knows it was denied and why.
