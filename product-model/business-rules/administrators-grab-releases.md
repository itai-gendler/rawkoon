---
appliesTo:
- {type: entity, id: grab, effect: creates}
permits:
- {actors: [administrator]}
- {unattended: true}
references:
- {kind: code, role: implementation, target: apps/api/src/routes/library/libraryGrabRoutes.ts}
- {kind: code, role: implementation, target: apps/api/src/routes/medias/search/index.ts}
---

# Only an administrator grabs a release

Choosing what is downloaded is the administrator's; Rawkoon's scheduled searches and RSS polling grab on their own.
