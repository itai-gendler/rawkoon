---
kind: primary
routes:
  web: Web
steps:
- text: The Member opens Notifications
  kind: actor
  actor: member
  entities:
  - {entity: notification, effect: reads, facts: []}
  contexts:
    web:
      place: web::household::notifications
- text: The Product lists the person's notifications, newest first, with their unread count
  kind: product
  actor: member
  entities:
  - {entity: notification, effect: reads, facts: [Title, Body, Kind, Image, Received]}
  contexts:
    web:
      place: web::household::notifications
---

# Read notifications

## Trigger

A person sees the unread badge.

## Outcome

The person sees what happened; opening one takes them to its link.
