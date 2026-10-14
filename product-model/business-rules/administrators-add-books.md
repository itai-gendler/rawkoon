---
appliesTo:
- {type: entity, id: book, effect: creates}
- {type: entity, id: ebook, effect: creates}
- {type: entity, id: audiobook, effect: creates}
permits:
- {actors: [administrator], when: &id001 [{entity: general-settings, fact: Books, is: 'On'}]}
- {unattended: true, when: *id001}
references:
- {kind: code, role: implementation, target: apps/api/src/routes/books/bookListRoutes.ts}
- {kind: doc, role: intent, target: PRODUCT.md, title: Product Principles}
---

# Only an administrator adds a book or edition, while the book library is on

Adding books and editions is library management, open only while books are turned on; Rawkoon also adds new titles by monitored authors on its own schedule.
