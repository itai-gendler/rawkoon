---
singleton: true
references:
- {kind: code, role: implementation, target: apps/api/prisma/schema.prisma}
- {kind: code, role: implementation, target: apps/api/src/routes/library/libraryMediaAdmin.ts}
---

# Library settings

The instance's settings for placing files, choosing releases and seeding.

## Information kept

- **Post-processing** — whether finished downloads are placed into the library
- **Movies folder** — where movies are placed
- **Shows folder** — where shows are placed
- **Downloads folder** — where the download client puts finished downloads
- **File operation** — hardlink, which keeps the download seeding, or move
- **Movie naming** — the template movie files are named by
- **Episode naming** — the template episode files are named by
- **Default movie profile** — the quality profile new movies receive
- **Default show profile** — the quality profile new shows receive
- **Active indexer manager** — Prowlarr or Jackett, the one releases are searched through
- **Seed targets** — the ratio and seeding time a torrent must reach before Rawkoon removes it, for public and private trackers
- **Automatic seeding release** — whether Rawkoon removes torrents from the client once they meet their seed target
- **Blocked file types** — file extensions that get a release rejected
- **Minimum free space** — grabs that would leave less free space on the download volume are refused; 0 turns the check off
- **Download checks** — how often downloads are checked, and how long one may go without progress or in total before it fails
- **Books folder** — where ebooks are placed
- **Audiobooks folder** — where audiobooks are placed
- **Book naming** — the template ebook files are named by
- **Audiobook naming** — the template audiobook folders are named by; tracks keep their own names
- **Default book profile** — the book quality profile new editions fall back to
- **Metadata source order** — the book metadata sources in priority order; a source left out is off
