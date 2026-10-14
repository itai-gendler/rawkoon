---
availability:
- {place: 'web::household'}
references:
- {kind: code, role: implementation, target: apps/api/src/workers/pollIndexerRss.ts}
- {kind: code, role: implementation, target: apps/api/src/workers/pollIndexerRssBooks.ts}
---

# Grab from RSS

Every fifteen minutes Rawkoon reads the new releases in the selected indexers' feeds and grabs those that match a monitored wanted movie, episode or, with books on, edition.
