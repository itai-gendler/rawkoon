---
kind: primary
routes:
  web: Web
  iphone: iPhone
steps:
- text: The Member opens Requests
  kind: actor
  actor: member
  entities:
  - {entity: request, effect: reads, facts: []}
  contexts:
    web:
      place: web::household::requests
    iphone:
      place: iphone::household::requests
- text: The Product lists the person's own requests, newest first, with their status
  kind: product
  actor: member
  entities:
  - {entity: request, effect: reads, facts: [Kind, Title, Year, Poster, Deny reason, Requested]}
  contexts:
    web:
      place: web::household::requests
    iphone:
      place: iphone::household::requests
---

# See one's own requests

## Trigger

A person checks on what they asked for.

## Outcome

The person sees each request as pending, approved, denied or available.
