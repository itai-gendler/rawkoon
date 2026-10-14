---
kind: primary
routes:
  web: Web
steps:
- text: The Administrator picks another quality profile for a wanted movie
  kind: actor
  actor: administrator
  entities:
  - {entity: quality-profile, effect: reads, facts: []}
  - {entity: movie, effect: reads, facts: []}
  contexts:
    web:
      place: web::household::title
- text: The Product assigns the profile to the movie
  kind: product
  actor: administrator
  entities:
  - {entity: movie, effect: changes, facts: [Quality profile]}
  contexts:
    web:
      place: web::household::title
---

# Change a movie's profile

## Trigger

The title should follow different release rules.

## Outcome

Later searches use the new profile.
