# 26. OFFLINE-FIRST / LOCAL-FIRST - Complete Deep Dive

## 26.10 Offline-First / Local-First - Summary Deal-Breaker Checklist

| Area | Deal-Breaker | Consequence |
|------|-------------|-------------|
| **Fundamentals** | Calling offline-first "local-first" | Server is still authoritative; no CRDT benefits |
| **Offline-First** | Relying only on `navigator.onLine` | Returns `true` on captive portals |
| **Offline-First** | No mutation queue | Offline mutations lost |
| **Offline-First** | No cache versioning | Old assets served forever |
| **Local-First** | No CRDT | Concurrent edits overwrite each other |
| **Local-First** | Server as source of truth | Not local-first |
| **Local-First** | No E2EE | Sync server can read all data |
| **IndexedDB** | Using `localStorage` for offline data | 5MB limit, synchronous, blocks main thread |
| **IndexedDB** | No quota monitoring | Storage evicted under pressure |
| **IndexedDB** | Storing large blobs | Slow; use OPFS instead |
| **Local Storage** | `localStorage` for auth tokens | XSS can read them |
| **Service Workers** | No cache versioning | Old assets served forever |
| **Service Workers** | `skipWaiting()` without consent | Breaks running app |
| **Service Workers** | No offline fallback | Browser error page when offline |
| **Optimistic Updates** | No rollback on failure | UI shows data never persisted |
| **Optimistic Updates** | No idempotency keys | Retried mutations create duplicates |
| **Optimistic Updates** | No temp ID reconciliation | Optimistic items never replaced |
| **Synchronization** | Full sync every time | Slow, wasteful |
| **Synchronization** | No sequence numbers | Can't detect gaps or request replay |
| **Synchronization** | No snapshot mechanism | Replaying 100K changes is slow |
| **Conflict Resolution** | LWW for collaborative text | Data loss |
| **Conflict Resolution** | No conflict resolution | Concurrent edits overwrite |
| **Offline Caching** | No cache versioning | Old assets served forever |
| **Offline Caching** | Cache-first for API data | Stale data served indefinitely |
| **Offline Caching** | No cache eviction | Storage fills up |

---

**The Big Rule:** Offline-first means the app works without a network. Local-first means the device is the source of truth. Use Service Workers for assets, IndexedDB for data, and a mutation queue for offline writes. Use CRDTs for collaborative editing. Always version caches, always queue mutations, always provide an offline fallback, and always reconcile optimistic updates with the server.

*Educational use only - AI-assisted content. See [DISCLAIMER.md](../DISCLAIMER.md) and [LICENSE.md](../LICENSE.md).*
