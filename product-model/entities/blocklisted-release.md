---
domain: library
references:
- {kind: code, role: implementation, target: apps/api/src/routes/medias/blocklist/index.ts}
- {kind: code, role: implementation, target: apps/api/src/services/downloadJanitor.ts#rejectRelease}
---

# Blocked release

A release Rawkoon will never grab again.

## Information kept

- **Release title** — the release's name
- **Indexer** — where it came from
- **Reason** — why it was blocked
- **Kind** — how it got there: stalled, blocked file, import rejected, or blocked by an administrator
- **Blocked** — when it was blocked
