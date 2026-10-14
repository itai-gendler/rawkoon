---
singleton: true
references:
- {kind: code, role: implementation, target: apps/api/src/routes/integrations/index.ts}
- {kind: doc, role: intent, target: docs/integrations.md}
---

# Integrations

The services the instance connects to.

## Information kept

- **Download client** — qBittorrent, Transmission or Deluge, with its address, credentials, label and save path
- **Prowlarr** — the Prowlarr address and key, and its indexers polled for RSS
- **Jackett** — the Jackett address and key, and its indexers polled for RSS
- **TMDB** — the TMDB key the catalog comes from
- **Jellyfin** — the media server refreshed after imports
- **AI provider** — an OpenAI-compatible endpoint, model, key, prices, daily budget and the places it is asked
- **Google Books** — the key the book catalog comes from; stored encrypted and never shown again
- **Audnexus** — the audiobook metadata service and its region
