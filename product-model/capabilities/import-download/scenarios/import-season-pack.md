---
kind: primary
routes:
  web: Web
steps:
- text: The Product picks up a completed season pack
  kind: condition
  unattended: true
  entities:
  - {entity: grab, effect: reads, facts: [Season]}
  contexts:
    web:
      place: web::household::title
- text: The Product matches each file to its episode by the episode numbers in its name, places it by the episode naming template and records it
  kind: product
  entities:
  - {entity: library-settings, effect: reads, facts: [Episode naming, Shows folder]}
  - {entity: video-file, effect: creates, facts: [Path, File name, Size, Duration, Resolution, Source, Video codec, HDR, Audio tracks, Subtitle tracks, Languages, Release group, Proper, Scanned]}
  - {entity: grab, effect: changes, from: Completed, to: Imported, facts: [Library path]}
  - {entity: episode, effect: reads, facts: []}
  contexts:
    web:
      place: web::household::title
---

# Import a season pack

## Trigger

A season pack finished.

## Outcome

Each episode has its file.
