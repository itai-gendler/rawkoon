---
domain: library
references:
- {kind: code, role: implementation, target: apps/api/prisma/schema.prisma}
- {kind: code, role: implementation, target: apps/api/src/services/grabDelay.ts#evaluateDelay}
---

# Held release

A release an automatic search found but holds back for the quality profile's grab delay, so better releases for the same movie, episode or season can be collected first.

## Information kept

- **Release title** — the release's name
- **Indexer** — where it came from
- **Score** — how the quality profile ranked it
- **Grab after** — when the delay ends and the best held release is grabbed
