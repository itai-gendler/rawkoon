---
kind: primary
routes:
  web: Web
steps:
- text: Hourly, the Product finds a watchlisted movie releasing tomorrow with no reminder sent for that date
  kind: condition
  unattended: true
  entities:
  - {entity: watchlist-item, effect: reads, facts: [Release date, Reminder sent]}
  - {entity: movie, effect: reads, facts: []}
  contexts:
    web:
      place: web::household::notifications
- text: The Product sends the person a release reminder notification and records the date it reminded for
  kind: product
  entities:
  - {entity: notification, effect: creates, to: Unread, facts: [Title, Body, Kind, Link, Image, Received]}
  - {entity: watchlist-item, effect: changes, facts: [Reminder sent]}
  contexts:
    web:
      place: web::household::notifications
---

# Remind the day before release

## Trigger

A watchlisted movie's release is one day away.

## Outcome

The person has a reminder linking to their watchlist.

## Edge cases

- A release date that moves resets the reminder so the new date is reminded too.
- A person who turned release reminders off gets none.
