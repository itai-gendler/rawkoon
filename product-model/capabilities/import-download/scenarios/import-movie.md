---
kind: primary
routes:
  web: Web
steps:
- text: The Product picks up a completed grab with post-processing on
  kind: condition
  unattended: true
  entities:
  - {entity: grab, effect: reads, facts: [Release title]}
  - {entity: library-settings, effect: reads, facts: [Post-processing]}
  contexts:
    web:
      place: web::household::title
- text: The Product renders the movie naming template, hardlinks or moves the file into the movies folder, scans it and records it
  kind: product
  entities:
  - {entity: library-settings, effect: reads, facts: [Movie naming, Movies folder, File operation]}
  - {entity: video-file, effect: creates, facts: [Path, File name, Size, Duration, Resolution, Source, Video codec, HDR, Audio tracks, Subtitle tracks, Languages, Release group, Proper, Scanned]}
  - {entity: grab, effect: changes, from: Completed, to: Imported, facts: [Library path]}
  - {entity: movie, effect: reads, facts: []}
  contexts:
    web:
      place: web::household::title
- text: The Product asks Jellyfin to refresh its library and notifies everyone who administers the instance that the movie was downloaded
  kind: product
  entities:
  - {entity: integration-settings, effect: reads, facts: [Jellyfin]}
  - {entity: notification, effect: creates, to: Unread, facts: [Title, Body, Kind, Link, Image, Received]}
  - {entity: movie, effect: reads, facts: []}
  contexts:
    web:
      place: web::household::title
---

# Import a movie

## Trigger

A movie download finished.

## Outcome

The movie's file is in the library and the media server sees it.

## Decision points

### File operation

Which file operation is set?

- Hardlink → The download stays in place and keeps seeding
- Move → The file is moved, and the torrent no longer seeds

## Edge cases

- A download another grab already placed is recorded as imported without a second file or notification.
