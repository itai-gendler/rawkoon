---
kind: primary
routes:
  web: Web
steps:
- text: The Member opens Calendar
  kind: actor
  actor: member
  entities: []
  contexts:
    web:
      place: web::household::calendar
- text: The Product places library movies on their digital release dates and episodes on their air dates, with other upcoming releases from TMDB
  kind: product
  actor: member
  entities:
  - {entity: movie, effect: reads, facts: [Title, Digital release date]}
  - {entity: episode, effect: reads, facts: [Title, Air date]}
  contexts:
    web:
      place: web::household::calendar
---

# See upcoming releases

## Trigger

A person wants to know what is coming.

## Outcome

The person sees the month's releases by day.
