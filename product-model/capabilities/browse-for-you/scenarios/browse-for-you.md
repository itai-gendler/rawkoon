---
kind: primary
routes:
  web: Web
steps:
- text: The Member opens For You
  kind: actor
  actor: member
  entities: []
  contexts:
    web:
      place: web::household::for-you
- text: The Product deals suggested titles, leaving out those in the library and those the person marked Not interested
  kind: product
  actor: member
  entities:
  - {entity: dismissed-title, effect: reads, facts: [Catalog identity]}
  - {entity: movie, effect: reads, facts: [Catalog identity]}
  - {entity: show, effect: reads, facts: [Catalog identity]}
  contexts:
    web:
      place: web::household::for-you
---

# Go through the For You deck

## Trigger

A person wants something new to watch.

## Outcome

The person sees one suggestion at a time.
