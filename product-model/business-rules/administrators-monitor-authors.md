---
appliesTo:
- {type: entity, id: author, effect: changes}
permits:
- {actors: [administrator], when: &id001 [{entity: general-settings, fact: Books, is: 'On'}]}
- {unattended: true, when: *id001}
references:
- {kind: code, role: implementation, target: apps/api/src/routes/books/authorRoutes.ts}
---

# Only an administrator changes an author's monitoring, while the book library is on

Following authors adds titles to the library.
