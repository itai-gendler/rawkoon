---
availability:
- {place: 'web::household'}
references:
- {kind: code, role: implementation, target: apps/api/src/workers/syncShowEpisodes.ts}
- {kind: code, role: implementation, target: apps/api/src/services/libraryTmdbRefresh.ts#syncLibraryShowEpisodes}
---

# Add new episodes

Every six hours Rawkoon refreshes each show from TMDB, adding new episodes as wanted and updating the series status.
