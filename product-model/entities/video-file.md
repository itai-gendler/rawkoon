---
domain: library
references:
- {kind: code, role: implementation, target: apps/api/prisma/schema.prisma}
- {kind: doc, role: intent, target: docs/library/metadata.md, title: File metadata}
---

# Video file

A movie or episode file placed in the library, with what scanning it revealed.

## Information kept

- **Path** — where the file is in the library
- **File name** — the file's name
- **Size** — the file size
- **Duration** — the running time
- **Resolution** — the video resolution
- **Source** — the release source, such as BluRay or WEB-DL
- **Video codec** — the video codec
- **HDR** — the HDR format, when there is one
- **Audio tracks** — each audio track with its language
- **Subtitle tracks** — each subtitle track with its language
- **Languages** — the languages the tracks carry
- **Release group** — the group that made the release; an administrator may correct it
- **Proper** — whether it is a proper or repack release
- **Scanned** — when the file was last scanned
