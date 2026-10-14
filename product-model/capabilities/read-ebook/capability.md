---
domain: books
availability:
- {place: 'web::household'}
- {place: 'iphone::household'}
references:
- {kind: code, role: implementation, target: apps/api/src/routes/books/bookPlaybackRoutes.ts}
- {kind: code, role: implementation, target: apps/web/src/features/reader/ReaderPage.tsx}
- {kind: code, role: implementation, target: apps/ios/Rawkoon/Views/EbookReaderView.swift}
---

# Read an ebook

A person reads an EPUB ebook from where they left off on any device.
