---
appliesTo:
- {type: capability, id: delete-quality-profile}
- {type: capability, id: delete-custom-format}
references:
- {kind: code, role: implementation, target: apps/api/src/routes/quality-profiles/index.ts}
- {kind: code, role: implementation, target: apps/api/src/routes/custom-formats/index.ts}
---

# A quality profile or custom format in use cannot be deleted

A profile assigned to titles, or a custom format a quality profile uses, is kept until nothing uses it; a book quality profile can be deleted and its editions go without one.
