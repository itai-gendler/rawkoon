---
domain: custom-formats
references:
- {kind: code, role: implementation, target: apps/api/src/routes/custom-formats/index.ts}
---

# Custom format

A reusable named condition on a release's title or parsed quality, scored or required by quality profiles.

## Information kept

- **Name** — a unique name
- **Conditions** — the conditions, all of which must match: title pattern, release group, source, codec, indexer, language, HDR, proper or repack, freeleech, resolution, seeders or size, each optionally negated
