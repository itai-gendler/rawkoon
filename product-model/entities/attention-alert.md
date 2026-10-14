---
domain: library
references:
- {kind: code, role: implementation, target: apps/api/src/services/libraryAttentionSync.ts}
- {kind: code, role: implementation, target: apps/api/src/services/libraryAttentionApi.ts}
---

# Attention alert

A movie, episode or season pack the Library attention panel flags because automatic grabbing is struggling or gave up.

## Information kept

- **Kind** — what needs attention, such as auto-grab gave up or auto-grab struggling
- **Detail** — the explanation shown with it
- **Opened** — when it was raised

## States

### Open

Shown in the Library attention panel.

### Dismissed

An administrator dismissed it.

### Resolved

The condition cleared and Rawkoon closed it.
