---
appliesTo:
- {type: capability, id: add-titles-from-followed-authors}
- {type: capability, id: follow-author}
references:
- {kind: code, role: implementation, target: apps/api/src/workers/checkAuthorReleases.ts}
---

# Monitoring an author adds only titles published on or after the day it was switched on

Turning monitoring on never pulls in a backlist; new titles must also be in one of the author's chosen languages, when any are chosen.
