---
appliesTo:
- {type: capability, id: search-wanted-titles}
- {type: capability, id: retry-search}
- {type: entity, id: movie, facts: [Search attempts]}
references:
- {kind: code, role: implementation, target: apps/api/src/services/grabAttempts.ts#recordMovieMiss}
- {kind: code, role: implementation, target: apps/api/src/constants/libraryGrab.ts}
---

# Twenty-four automatic misses skip a title

Each scheduled search that finds nothing suitable counts an attempt against the movie, episode or season; at the twenty-fourth the item is skipped and the administrators are told. A manual search or Retry search makes it wanted again.
