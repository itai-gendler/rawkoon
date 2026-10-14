---
appliesTo:
- {type: entity, id: grab, effect: removes}
permits:
- {actors: [administrator]}
references:
- {kind: code, role: implementation, target: apps/api/src/routes/library/libraryFilesRoutes.ts}
---

# Only an administrator removes a grab

Removing downloads and clearing history is download management.
