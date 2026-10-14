---
kind: primary
routes:
  web: Web
steps:
- text: The Administrator chooses Rescan files on a movie
  kind: actor
  actor: administrator
  entities:
  - {entity: movie, effect: reads, facts: []}
  contexts:
    web:
      place: web::household::title
- text: The Product rescans the movie's files, drops records whose file is gone, adopts untracked video files in its folder and renames files that do not match the movie naming template
  kind: product
  actor: administrator
  entities:
  - {entity: video-file, effect: changes, facts: [Path, File name, Size, Resolution, Source, Video codec, Audio tracks, Subtitle tracks, Languages, Scanned]}
  - {entity: library-settings, effect: reads, facts: [Movie naming, File operation]}
  - {entity: movie, effect: reads, facts: []}
  contexts:
    web:
      place: web::household::title
---

# Rescan a movie

## Trigger

Files changed outside Rawkoon or a mount was repaired.

## Outcome

The library matches what is on disk.

## Edge cases

- A finished download whose file never reached the library is queued for import again.
- Renaming is skipped while a download for the movie is still running.
