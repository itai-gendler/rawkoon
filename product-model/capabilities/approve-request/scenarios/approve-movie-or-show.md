---
kind: primary
routes:
  web: Web
  iphone: iPhone
steps:
- text: The Administrator picks a quality profile for a pending request and approves it
  kind: actor
  actor: administrator
  entities:
  - {entity: quality-profile, effect: reads, facts: []}
  - {entity: request, effect: reads, facts: []}
  contexts:
    web:
      place: web::household::requests
    iphone:
      place: iphone::household::requests
- text: The Product adds the movie to the library with that profile, marks the request approved and notifies the requester
  kind: product
  actor: administrator
  entities:
  - {entity: movie, effect: creates, to: Wanted, facts: [Title, Year, Overview, Poster, Catalog identity, Monitored, Quality profile, Search title, Digital release date, Added]}
  - {entity: request, effect: changes, from: Pending, to: Approved, facts: [Quality profile, Decided]}
  - {entity: notification, effect: creates, to: Unread, facts: [Title, Body, Kind, Link, Image, Received]}
  contexts:
    web:
      place: web::household::requests
    iphone:
      place: iphone::household::requests
---

# Approve a movie or show

## Trigger

An administrator agrees to get a requested title.

## Outcome

The title is wanted in the library and the requester knows it was approved.

## Edge cases

- Approving a show adds it with its episodes the same way.
