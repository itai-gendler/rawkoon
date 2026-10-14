---
domain: library
references:
- {kind: code, role: implementation, target: apps/api/prisma/schema.prisma}
- {kind: code, role: implementation, target: apps/api/src/services/downloadOutcome.ts}
- {kind: doc, role: intent, target: CONTEXT.md, title: Downloads}
- {kind: doc, role: intent, target: docs/library/downloads-and-files.md}
---

# Grab

One release handed to the download client for a movie, a show's season, an episode, an ebook or an audiobook, followed until it is placed in the library or fails. The Download history lists them.

## Information kept

- **Release title** — the release's name as the indexer gave it
- **Indexer** — the indexer the release came from
- **Grabbed** — when the release was handed to the client
- **Completed** — when the download client finished it
- **Season** — the season a season-pack grab is for
- **Upgrade** — whether it replaces a file already in the library
- **AI pick** — whether the language model chose this release over the classic scorer
- **Failure reason** — why the download failed or was rejected
- **Import error** — why placing the finished download into the library failed
- **Library path** — where the import placed the file
- **Released from client** — when Rawkoon removed the torrent from the download client, and why: target met, removed by an administrator, move mode, stalled, blocked file, import rejected, or not added by Rawkoon
- **Freed size** — the space removing the torrent freed

## States

### Downloading

Handed to the download client and transferring.

### Completed

The download client finished it; the import has not placed it yet.

### Imported

The import placed the file in the library.

### Import failed

The import could not place the file; it can be retried.

### Failed

The download failed, stalled, or was rejected before it reached the library.
