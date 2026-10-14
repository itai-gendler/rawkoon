---
appliesTo:
- {type: capability, id: change-books-settings}
- {type: entity, id: general-settings, facts: [Books]}
references:
- {kind: doc, role: intent, target: docs/library/books.md, title: Turn it on}
---

# The book library turns on only with a stored Google Books key

A book section whose every search fails on authentication is worse than none, so the switch stays inert until a key is stored.
