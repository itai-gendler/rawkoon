---
appliesTo:
- {type: entity, id: movie, effect: removes}
- {type: entity, id: show, effect: removes}
permits:
- {actors: [administrator]}
references:
- {kind: code, role: implementation, target: apps/api/src/routes/library/libraryListRoutes.ts}
---

# Only an administrator removes a movie or show from the library

Removing a title is library management.
