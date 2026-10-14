---
appliesTo:
- {type: entity, id: blocklisted-release, effect: creates}
permits:
- {actors: [administrator]}
- {unattended: true}
references:
- {kind: code, role: implementation, target: apps/api/src/routes/medias/blocklist/index.ts}
---

# Only an administrator blocks a release

Rawkoon also blocks releases itself when they stall, carry a blocked file or fail import.
