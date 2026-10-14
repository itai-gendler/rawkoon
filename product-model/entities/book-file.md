---
domain: books
references:
- {kind: code, role: implementation, target: apps/api/prisma/schema.prisma}
---

# Book file

An ebook or audiobook file in the library.

## Information kept

- **Path** — where the file is
- **File name** — the file's name
- **Size** — the file size
- **Format** — epub, mobi, azw3, pdf or cbz for ebooks; m4b, mp3, flac or ogg for audiobooks
- **Retail** — whether the release was marked retail
- **Audio bitrate** — the bitrate of an audio file
- **Duration** — the length of an audio file
- **Languages** — the languages it carries
