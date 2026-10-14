---
appliesTo:
- {type: capability, id: track-downloads}
- {type: entity, id: blocklisted-release}
references:
- {kind: code, role: implementation, target: apps/api/src/workers/checkDownloadCompletion.ts}
---

# When every live download stalls at once, no release is blocklisted

Two or more downloads all stalling in the same check is a network outage, not bad releases; they fail without being blocked.
