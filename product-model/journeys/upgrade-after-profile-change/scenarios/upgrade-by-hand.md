---
kind: primary
result: achieved
routes:
  web: Web
steps:
- text: The Administrator picks a stricter quality profile for a downloaded movie
  kind: actor
  actor: administrator
  capability: change-quality-profile
  entities:
  - {entity: quality-profile, effect: reads, facts: []}
  - {entity: movie, effect: reads, facts: []}
  contexts:
    web:
      place: web::household::title
- text: The Product assigns the profile, finds the movie's file fails it and opens Upgrade Quality
  kind: product
  actor: administrator
  capability: change-quality-profile
  entities:
  - {entity: movie, effect: changes, facts: [Quality profile]}
  contexts:
    web:
      place: web::household::title
- text: The Administrator chooses Search Manually and lands on the movie's Search tab in upgrade mode
  kind: actor
  actor: administrator
  capability: search-releases
  entities:
  - {entity: movie, effect: reads, facts: []}
  contexts:
    web:
      place: web::household::title
- text: The Product lists the releases scored against the new profile
  kind: product
  actor: administrator
  capability: search-releases
  entities:
  - {entity: movie, effect: reads, facts: [Search title, Quality profile]}
  contexts:
    web:
      place: web::household::title
---

# Choose the upgrade by hand

## Trigger

An administrator wants to pick the upgrade release.

## Outcome

The administrator sees releases for the new profile; a grab there replaces the current file.
