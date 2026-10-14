---
kind: primary
routes:
  web: Web
steps:
- text: The Administrator picks a stricter quality profile for a downloaded movie
  kind: actor
  actor: administrator
  entities:
  - {entity: quality-profile, effect: reads, facts: []}
  - {entity: movie, effect: reads, facts: []}
  contexts:
    web:
      place: web::household::title
- text: The Product assigns the profile, finds the movie's file fails it and opens Upgrade Quality
  kind: product
  actor: administrator
  entities:
  - {entity: movie, effect: changes, facts: [Quality profile]}
  - {entity: video-file, effect: reads, facts: [Resolution, Source, Video codec, HDR]}
  contexts:
    web:
      place: web::household::title
---

# Offer an upgrade when files fail the new profile

## Trigger

The household raises its quality bar.

## Outcome

The administrator is asked whether to search automatically, search manually, or keep the current file.

## Edge cases

- For a show, the dialog counts the downloaded episodes whose files fail the new profile.
