---
appliesTo:
- {type: entity, id: movie, effect: changes}
- {type: entity, id: show, effect: changes}
- {type: entity, id: episode, effect: changes}
permits:
- {actors: [administrator]}
- {unattended: true}
references:
- {kind: code, role: implementation, target: apps/api/src/routes/library/libraryMetaRoutes.ts}
- {kind: code, role: implementation, target: apps/api/src/routes/library/libraryGrabRoutes.ts}
---

# Only an administrator changes a movie, show or episode

Profiles, monitoring, details, artwork, searches and grabs are the administrator's; Rawkoon's own schedule moves titles through their states as downloads progress.
