---
kind: primary
routes:
  web: Web
steps:
- text: The Product finds a movie whose automatic grabbing gave up
  kind: condition
  unattended: true
  entities:
  - {entity: movie, effect: reads, facts: [Search attempts]}
  contexts:
    web:
      place: web::household::home
- text: The Product opens one alert for it and notifies everyone who administers the instance
  kind: product
  entities:
  - {entity: attention-alert, effect: creates, to: Open, facts: [Kind, Detail, Opened]}
  - {entity: notification, effect: creates, to: Unread, facts: [Title, Body, Kind, Link, Image, Received]}
  contexts:
    web:
      place: web::household::home
---

# Raise an alert

## Trigger

Automatic grabbing is not getting a title.

## Outcome

The administrators see it in Library attention.
