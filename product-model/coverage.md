---
scope: The API server, the web app, the shared package, and the iPhone app's sign-in, requests, listening, reading and offline audiobook downloads.
method: Static inspection of source, schema, locales and documentation; nothing was run.
covered:
- description: API routes for the library, grabs, files, requests, search, watchlist, discovery, books, quality profiles, custom formats, notifications, users and settings.
  paths:
  - apps/api/src/routes/library/
  - apps/api/src/routes/requests/
  - apps/api/src/routes/medias/
  - apps/api/src/routes/books/
  - apps/api/src/routes/quality-profiles/
  - apps/api/src/routes/custom-formats/
  - apps/api/src/routes/notifications/index.ts
  - apps/api/src/routes/users/
  - apps/api/src/routes/settings/
  - apps/api/src/routes/admin/adminUserRoutes.ts
  - apps/api/src/routes/downloads/
  - apps/api/src/routes/integrations/
  - apps/api/src/routes/dashboard/upcoming/
- description: Sign-in, setup, invitations and authorization guards.
  paths:
  - apps/api/src/auth.ts
  - apps/api/src/lib/auth.ts
  - apps/api/src/middleware/
- description: Grab, download tracking, import, seeding, search and request services and the scheduled workers that drive them.
  paths:
  - apps/api/src/services/
  - apps/api/src/workers/
  - apps/api/src/constants/
- description: Data schema.
  paths:
  - apps/api/prisma/schema.prisma
- description: Web app pages, features and navigation.
  paths:
  - apps/web/src/pages/
  - apps/web/src/features/
  - apps/web/src/components/
  - apps/web/src/lib/routing/
  - apps/web/src/locales/
- description: Shared types and constants.
  paths:
  - apps/shared/src/
- description: iPhone app sign-in, requests, books, player, reader and chapter downloads.
  paths:
  - apps/ios/Rawkoon/Views/LoginView.swift
  - apps/ios/Rawkoon/Views/RequestsView.swift
  - apps/ios/Rawkoon/Views/Discover/
  - apps/ios/Rawkoon/Views/Book/
  - apps/ios/Rawkoon/Views/BookView.swift
  - apps/ios/Rawkoon/Views/PlayerView.swift
  - apps/ios/Rawkoon/Views/EbookReaderView.swift
  - apps/ios/Rawkoon/AppModel+Auth.swift
  - apps/ios/Rawkoon/AppModel+Downloads.swift
  - apps/ios/Rawkoon/ChapterDownloader.swift
  - apps/ios/Rawkoon/AudiobookPlayer.swift
exclusions:
- description: Documentation site, screenshots, design notes and planning documents.
  paths:
  - docs/
  - DESIGN.md
  - .impeccable/
- description: Build, container, deployment and CI configuration.
  paths:
  - Dockerfile
  - docker-compose.yml
  - docker-compose.prod-example.yml
  - Makefile
  - ops/
  - scripts/
  - .github/
  - .husky/
  - apps/api/entrypoint.sh
- description: Tests and end-to-end fixtures.
  paths:
  - apps/api/test/
  - apps/api/e2e/
  - apps/ios/Tests/
  - apps/ios/RawkoonTests/
- description: Push relay service that forwards notifications to Apple.
  paths:
  - apps/relay/
- description: One-off maintenance command-line scripts.
  paths:
  - apps/api/src/scripts/
  - apps/api/scripts/
unmapped:
- description: Re-encode queue, remux and their iPhone Live Activities.
  paths:
  - apps/api/src/routes/transcode/
  - apps/api/src/services/transcode/
  - apps/web/src/features/transcode/
  - apps/ios/Rawkoon/Views/Reencode/
- description: AI provider usage page and the interactive search suggestion.
  paths:
  - apps/api/src/routes/integrations/ai-provider/
  - apps/web/src/pages/medias/_component/useAiPick.ts
- description: Jobs, library health, GitHub releases and the server-sent event test.
  paths:
  - apps/api/src/routes/admin/adminJobRoutes.ts
  - apps/api/src/routes/admin/adminLibraryHealthRoutes.ts
  - apps/api/src/routes/admin/sseTestRoutes.ts
  - apps/api/src/routes/releases/
- description: Sessions, API keys, single sign-on provider setup and web push administration.
  paths:
  - apps/api/src/routes/admin/adminMiscRoutes.ts
  - apps/api/src/routes/admin/apiKeyRoutes.ts
  - apps/api/src/routes/integrations/oidc/
- description: Passkey registration, push subscriptions, devices and notification channels.
  paths:
  - apps/api/src/routes/notifications/channels.ts
  - apps/web/src/pages/settings/_component/PasskeysSection.tsx
- description: Download client completion hook.
  paths:
  - apps/api/src/routes/integrations/downloadClient/hookRoutes.ts
- description: Downloads import of loose files, orphaned torrents, per-indexer seed rules and held-release listing.
  paths:
  - apps/api/src/routes/library/downloads/
  - apps/web/src/features/downloadsImport/
  - apps/web/src/features/seeding/
- description: Library scan, import from other library managers, language reindex, search title choice, episode status and release group edits.
  paths:
  - apps/api/src/routes/library/libraryMediaAdmin.ts
  - apps/api/src/routes/library/libraryJobWorkerRoutes.ts
  - apps/web/src/pages/medias/_component/LibrarySearchTitleSection.tsx
- description: Calendar subscription feed.
  paths:
  - apps/api/src/routes/calendar/
- description: Statistics, library growth, activity feed, listening statistics and Jellyfin now playing.
  paths:
  - apps/api/src/routes/dashboard/activities/
  - apps/api/src/routes/dashboard/jellyfin/
  - apps/api/src/routes/library/libraryJobStatsRoutes.ts
  - apps/api/src/routes/books/bookListeningStatsRoutes.ts
  - apps/web/src/pages/stats/
  - apps/web/src/pages/activity/
  - apps/web/src/features/listening/
- description: Book discovery lists and adding from them.
  paths:
  - apps/api/src/routes/books/bookDiscoveryRoutes.ts
  - apps/web/src/pages/books/explore.tsx
- description: Book requests, which the server accepts but no client offers.
  paths:
  - apps/api/src/services/mediaRequests.ts
- description: Forgot-password and reset-password pages.
  paths:
  - apps/web/src/pages/forgot-password.tsx
  - apps/web/src/pages/reset-password.tsx
- description: Summary endpoint for API-key clients.
  paths:
  - apps/api/src/routes/labby/
- description: 'The rest of the iPhone app: home, library management, release search, settings and administration, widgets, CarPlay and Siri intents.'
  paths:
  - apps/ios/Rawkoon/Views/Settings/
  - apps/ios/Rawkoon/Views/Detail/
  - apps/ios/Rawkoon/Views/ReleaseSearch/
  - apps/ios/Rawkoon/Views/Home/
  - apps/ios/Rawkoon/Views/Library/
  - apps/ios/Rawkoon/Views/Activity/
  - apps/ios/RawkoonWidgets/
  - apps/ios/Rawkoon/CarPlay/
  - apps/ios/Rawkoon/Intents/
limitations: []
---

# Coverage
