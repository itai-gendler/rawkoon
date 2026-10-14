---
kind: primary
routes:
  web: Web
  iphone: iPhone
steps:
- text: The Member chooses Request on a movie or show that is not in the library
  kind: actor
  actor: member
  entities:
  - {entity: request, effect: reads, facts: []}
  - {entity: movie, effect: reads, facts: []}
  - {entity: show, effect: reads, facts: []}
  contexts:
    web:
      place: web::household::browse
    iphone:
      place: iphone::household::discover
- text: The Product records the request as pending and notifies everyone who administers the instance
  kind: product
  actor: member
  entities:
  - {entity: request, effect: creates, to: Pending, facts: [Kind, Title, Year, Poster, Requested]}
  - {entity: notification, effect: creates, to: Unread, facts: [Title, Body, Kind, Link, Image, Received]}
  contexts:
    web:
      place: web::household::browse
    iphone:
      place: iphone::household::discover
---

# Request a movie or show

## Trigger

A person wants a title the library does not have.

## Outcome

The request is pending and the administrators know about it.
