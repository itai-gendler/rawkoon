---
domain: library
relations:
- {entity: episode, verb: has, cardinality: one-to-many}
- {entity: grab, verb: has, cardinality: one-to-many}
- {entity: pending-release, verb: holds, cardinality: one-to-many}
- {entity: attention-alert, verb: has, cardinality: one-to-many}
references:
- {kind: code, role: implementation, target: apps/api/prisma/schema.prisma}
- {kind: code, role: implementation, target: apps/api/src/utils/medias/libraryHelpers.ts#resolveDownloadedStatus}
---

# Show

A TV show in the library, with its seasons and episodes.

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
- **Series status** — the catalog's status for the series: returning, in production, planned or ended
- **Episodes** — how many episodes the show has
- **Downloaded episodes** — how many of its episodes are in the library
- **Seasons** — how many seasons the show has
- **Added** — when it joined the library
- **Size on disk** — the size of its files

## States

### Wanted

Missing from the library and eligible for searching while monitored.

### Downloading

A season pack was grabbed and is in the download client.

### Downloaded

A grab for the show finished and the series has ended.

### Returning

A grab for the show finished and the catalog lists the series as returning, in production or planned; the Library shows that catalog status.

### Upgrading

A better season pack was grabbed while the current files stay in place.
