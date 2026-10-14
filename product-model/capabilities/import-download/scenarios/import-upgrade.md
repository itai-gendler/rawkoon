---
kind: primary
routes:
  web: Web
steps:
- text: The Product picks up a completed upgrade grab
  kind: condition
  unattended: true
  entities:
  - {entity: grab, effect: reads, facts: [Upgrade]}
  contexts:
    web:
      place: web::household::title
- text: The Product places the new file and removes the file it supersedes
  kind: product
  entities:
  - {entity: video-file, as: new-file, effect: creates, facts: [Path, File name, Size, Duration, Resolution, Source, Video codec, HDR, Audio tracks, Subtitle tracks, Languages, Release group, Proper, Scanned]}
  - {entity: video-file, as: superseded-file, effect: removes}
  - {entity: grab, effect: changes, from: Completed, to: Imported, facts: [Library path]}
  contexts:
    web:
      place: web::household::title
---

# Import an upgrade

## Trigger

A better release finished.

## Outcome

The library holds only the better file.
