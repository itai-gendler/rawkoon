---
entities:
- {entity: general-settings, shows: [Books], collects: [Books]}
- {entity: integration-settings, shows: [Google Books, Audnexus], collects: [Google Books, Audnexus]}
- {entity: library-settings, shows: [Books folder, Audiobooks folder, Book naming, Audiobook naming, Default book profile, Metadata source order], collects: [Books folder, Audiobooks folder, Book naming, Audiobook naming, Default book profile, Metadata source order]}
- {entity: book-quality-profile, shows: [Name, Kind, Allowed formats, Cutoff format, Prefer retail, Maximum size, Minimum seeders, Minimum audio bitrate, Preferred languages, Prioritized trackers, Prefer tracker over quality], collects: [Name, Kind, Allowed formats, Cutoff format, Prefer retail, Maximum size, Minimum seeders, Minimum audio bitrate, Preferred languages, Prioritized trackers, Prefer tracker over quality]}
references:
- {kind: code, role: implementation, target: apps/web/src/pages/settings/_component/BooksSettingsTab.tsx}
---

# Books settings

The book library's switch, providers, metadata sources, folders, naming and book quality profiles.
