---
domain: requests
references:
- {kind: code, role: implementation, target: apps/api/src/services/mediaRequests.ts}
- {kind: code, role: implementation, target: apps/api/prisma/schema.prisma}
---

# Request

A household member's ask for a movie or show that is not in the library yet.

## Information kept

- **Kind** — movie or show
- **Title** — the requested title
- **Year** — the release year
- **Poster** — the artwork shown with it
- **Quality profile** — the profile the approving administrator chose
- **Deny reason** — why it was denied, when a reason was given
- **Requested** — when it was made or last reopened
- **Decided** — when an administrator approved or denied it

## States

### Pending

Waiting for an administrator.

### Approved

Added to the library and on its way.

### Denied

An administrator turned it down.

### Available

The title arrived in the library.
