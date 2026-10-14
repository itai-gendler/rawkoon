---
appliesTo:
- {type: entity, id: blocklisted-release, effect: removes}
permits:
- {actors: [administrator]}
references:
- {kind: code, role: implementation, target: apps/api/src/routes/medias/blocklist/index.ts}
---

# Only an administrator unblocks a release

The blocklist is managed in the administration area.
