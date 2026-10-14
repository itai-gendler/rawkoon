---
appliesTo:
- {type: entity, id: grab, effect: changes}
permits:
- {actors: [administrator]}
- {unattended: true}
references:
- {kind: code, role: implementation, target: apps/api/src/services/downloadOutcome.ts}
---

# Only an administrator changes a grab

Rawkoon follows each grab through to the library on its own schedule; an administrator may retry an import or remove a torrent.
