---
domain: books
availability:
- {place: 'web::household'}
- {place: 'iphone::household'}
references:
- {kind: code, role: implementation, target: apps/api/src/routes/books/bookPlaybackRoutes.ts}
- {kind: code, role: implementation, target: apps/web/src/features/player/ListenPage.tsx}
- {kind: code, role: implementation, target: apps/ios/Rawkoon/AudiobookPlayer.swift}
- {kind: doc, role: intent, target: docs/library/books.md, title: Reading and listening}
---

# Listen to an audiobook

A person plays an audiobook chapter by chapter from where they left off on any device; the position is kept on the server.
