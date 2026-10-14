---
appliesTo:
- {type: entity, id: book, effect: removes}
permits:
- {actors: [administrator], when: [{entity: general-settings, fact: Books, is: 'On'}]}
references:
- {kind: code, role: implementation, target: apps/api/src/routes/books/bookListRoutes.ts}
---

# Only an administrator removes a book, while the book library is on

Removing a book is library management.
