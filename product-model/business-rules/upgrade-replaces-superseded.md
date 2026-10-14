---
appliesTo:
- {type: capability, id: import-download}
- {type: capability, id: start-upgrade-search}
references:
- {kind: code, role: implementation, target: apps/api/src/services/postProcessorSingle.ts}
- {kind: doc, role: intent, target: docs/library/books.md, title: Automatic acquisition}
---

# An upgrade replaces the file it supersedes

When a better release is imported, the file it upgrades is removed, so the library never keeps both.
