---
domain: library
relations:
- {entity: video-file, verb: has, cardinality: one-to-many}
- {entity: grab, verb: has, cardinality: one-to-many}
references:
- {kind: code, role: implementation, target: apps/api/prisma/schema.prisma}
---

# Episode

One episode of a show in the library.

## Information kept

- **Season** — the season number
- **Number** — the episode number within the season
- **Title** — the episode title
- **Air date** — when the episode aired or airs
- **Monitored** — whether automatic searches look for it
- **Search attempts** — automatic searches that found nothing suitable since the last grab or reset
- **Downloaded** — when its file arrived

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
