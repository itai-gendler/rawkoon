---
appliesTo:
- {type: capability, id: search-now}
- {type: capability, id: retry-search}
references:
- {kind: code, role: implementation, target: apps/api/src/routes/library/libraryGrabRoutes.ts}
---

# A manual search resets the search attempts

Searching by hand always makes a skipped item eligible again.
