---
availability:
- {place: 'web::household'}
references:
- {kind: code, role: implementation, target: apps/api/src/workers/checkMovieReleases.ts#checkMovieReleases}
- {kind: code, role: implementation, target: apps/api/src/workers/checkEpisodeReleases.ts}
- {kind: code, role: implementation, target: apps/api/src/workers/checkBookReleases.ts}
- {kind: code, role: implementation, target: apps/api/src/services/grabAttempts.ts#recordMovieMiss}
- {kind: code, role: implementation, target: apps/api/src/services/grabDelay.ts}
- {kind: code, role: implementation, target: apps/api/src/workers/processPendingReleases.ts}
- {kind: code, role: implementation, target: apps/api/src/services/aiProvider/client.ts#pickReleaseWithAi}
- {kind: doc, role: intent, target: docs/library/ai-release-picks.md}
---

# Search for wanted titles

Every six hours Rawkoon searches for each monitored wanted movie released digitally, each aired wanted episode and, with books on, each wanted edition, and grabs the best release the quality profile allows.
