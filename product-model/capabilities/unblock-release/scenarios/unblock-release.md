---
kind: primary
routes:
  web: Web
steps:
- text: The Administrator chooses Unblock on a blocked release and confirms
  kind: actor
  actor: administrator
  entities:
  - {entity: blocklisted-release, effect: reads, facts: []}
  contexts:
    web:
      place: web::administration::blocklist
- text: The Product removes it from the blocklist
  kind: product
  actor: administrator
  entities:
  - {entity: blocklisted-release, effect: removes}
  contexts:
    web:
      place: web::administration::blocklist
---

# Unblock a release

## Trigger

A release was blocked by mistake or the problem is fixed.

## Outcome

The release can be grabbed again.
