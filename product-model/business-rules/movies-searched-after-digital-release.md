---
appliesTo:
- {type: capability, id: search-wanted-titles}
- {type: entity, id: movie, facts: [Digital release date]}
references:
- {kind: code, role: implementation, target: apps/api/src/workers/checkMovieReleases.ts#checkMovieReleases}
---

# A movie is searched for automatically only once its digital release date has passed

Until then scheduled searches skip it and count no attempt; a release date that is missing or due is checked again with TMDB first.
