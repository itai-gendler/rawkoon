---
appliesTo:
- {type: capability, id: track-downloads}
- {type: capability, id: import-download}
- {type: entity, id: library-settings, facts: [Blocked file types]}
references:
- {kind: code, role: implementation, target: apps/api/src/services/downloadJanitor.ts}
---

# A release carrying a blocked file type is rejected and blocked

Downloads are checked for blocked extensions while downloading and again before import.
