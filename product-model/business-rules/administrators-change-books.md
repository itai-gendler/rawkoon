---
appliesTo:
- {type: entity, id: book, effect: changes}
- {type: entity, id: ebook, effect: changes}
- {type: entity, id: audiobook, effect: changes}
permits:
- {actors: [administrator], when: &id001 [{entity: general-settings, fact: Books, is: 'On'}]}
- {unattended: true, when: *id001}
references:
- {kind: code, role: implementation, target: apps/api/src/routes/books/bookEditionRoutes.ts}
---

# Only an administrator changes a book or edition, while the book library is on

Details, profiles, monitoring, searches and grabs for books are the administrator's; imports and scheduled searches move editions on Rawkoon's own schedule.
