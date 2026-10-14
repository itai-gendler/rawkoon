---
domain: library
relations:
- {entity: video-file, verb: has, cardinality: one-to-many}
- {entity: grab, verb: has, cardinality: one-to-many}
- {entity: pending-release, verb: holds, cardinality: one-to-many}
- {entity: attention-alert, verb: has, cardinality: one-to-many}
references:
- {kind: code, role: implementation, target: apps/api/prisma/schema.prisma}
- {kind: code, role: implementation, target: apps/api/src/services/libraryFromTmdb.ts#addOrUpdateLibraryFromTmdb}
- {kind: doc, role: intent, target: docs/library/metadata.md}
---

# Movie

A movie in the library.

## Information kept

- **Title** — the catalog title, or the administrator's own title when one is set; an own value survives catalog refreshes
- **Sort title** — the title the library sorts by, catalog or own
- **Year** — the release year, catalog or own
- **Overview** — the synopsis, catalog or own
- **Poster** — the poster artwork, the catalog default or one an administrator picked
- **Backdrop** — the backdrop artwork, the catalog default or one an administrator picked
- **Catalog identity** — the TMDB title it was added from; the library holds a TMDB title once
- **Monitored** — whether automatic searches look for it
- **Quality profile** — the profile that decides which releases are allowed and preferred
- **Search title** — the title, and its language, used when searching indexers
- **Digital release date** — when the movie is released digitally in the instance's region
- **Search attempts** — automatic searches that found nothing suitable since the last grab or reset
- **Added** — when it joined the library
- **Size on disk** — the size of its files

## States

### Wanted

Missing from the library and eligible for searching while monitored.

### Downloading

A release was grabbed and is in the download client.

### Downloaded

A file is in the library.

### Upgrading

A better release was grabbed while the current file stays in place.

### Skipped

Automatic searching gave up after repeated misses; a manual search or Retry search makes it wanted again.
