---
appliesTo:
- {type: capability, id: grab-release}
- {type: capability, id: search-wanted-titles}
- {type: entity, id: library-settings, facts: [Minimum free space]}
references:
- {kind: code, role: implementation, target: apps/api/src/services/grabSpaceCheck.ts}
---

# A grab that would leave less than the minimum free space on the download volume is refused

The release size is checked against the free space; a minimum of 0 turns the check off, and an unknown size skips it. A scheduled search refused for space does not count as a miss.
