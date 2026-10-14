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
- text: The Administrator chooses Auto Search
  kind: actor
  actor: administrator
  capability: start-upgrade-search
  entities: []
  contexts:
    web:
      place: web::household::title
- text: The Product marks the movie upgrading and queues the upgrade search
  kind: product
  actor: administrator
  capability: start-upgrade-search
  entities:
  - {entity: movie, effect: changes, from: Downloaded, to: Upgrading, facts: []}
  contexts:
    web:
      place: web::household::title
---

# Upgrade automatically

## Trigger

An administrator raises a downloaded movie's quality bar.

## Outcome

An upgrade search is under way while the current file stays.
