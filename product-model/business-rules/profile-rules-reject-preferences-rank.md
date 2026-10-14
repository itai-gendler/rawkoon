---
appliesTo:
- {type: capability, id: search-releases}
- {type: capability, id: search-now}
- {type: capability, id: search-wanted-titles}
- {type: entity, id: quality-profile}
references:
- {kind: code, role: implementation, target: apps/api/src/utils/medias/releaseScorer.ts}
- {kind: doc, role: intent, target: docs/library/quality-profiles.md, title: Hard rules and preferences}
---

# A quality profile's rules reject releases; its preferences only rank the rest

Minimum resolution, cutoff, required HDR, preferred audio languages, size, seeders and required or forbidden custom formats reject; sources, codecs, HDR, trackers and custom-format scores rank what is left.
