---
appliesTo:
- {type: entity, id: quality-profile, effect: creates}
- {type: entity, id: custom-format, effect: creates}
- {type: entity, id: book-quality-profile, effect: creates}
permits:
- {actors: [administrator]}
references:
- {kind: code, role: implementation, target: apps/api/src/routes/quality-profiles/index.ts}
- {kind: code, role: implementation, target: apps/api/src/routes/custom-formats/index.ts}
- {kind: code, role: implementation, target: apps/api/src/routes/books/bookQualityProfileRoutes.ts}
---

# Only an administrator creates a quality profile, custom format or book quality profile

Release rules are the administrator's.
