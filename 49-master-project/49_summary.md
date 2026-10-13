# 49. Master Project

The master project is **Atlas**: an AI-native, real-time, offline-first collaborative workspace. It exists to force every earlier chapter to meet in one codebase, because knowledge that has only ever been studied in isolation is knowledge you cannot yet use.

## What The Project Proves

| Property | Where it is enforced |
|---|---|
| Two people edit the same document without losing work | CRDT (49.22), sync protocol (49.18) |
| The app keeps working with no network and syncs later | IndexedDB (49.20), offline-first (49.21) |
| The AI can act inside the document but cannot exceed the user's rights | Agents (49.16), authorisation (49.13) |
| No tenant can ever read another tenant's data | Authorisation (49.13), Postgres RLS (49.10) |
| A bad deploy is reversible in one command | CI/CD (49.26), cloud deployment (49.31) |

Those five properties are the definition of the project. Features are negotiable; these are not.

## How The Pieces Fit

```text
React + Next.js        render the tree and place the client boundary   (49.1, 49.3-49.5)
TypeScript             specify every boundary in the system            (49.2)
Design system          make generated and human UI indistinguishable   (49.7, 49.8)
TanStack Query         own server state; never the document text       (49.9)
Postgres + Redis       persist truth; cache the derived                (49.10, 49.11)
Auth + authorisation   decide who may do what, in three layers          (49.12, 49.13)
AI stack               chat, retrieval, agents, generative UI           (49.14-49.17)
Realtime + CRDT        make simultaneous editing the default            (49.18, 49.19, 49.22)
Offline layer          treat the device as a replica, not a cache       (49.20, 49.21)
Quality gates          prove convergence and permissions, not coverage  (49.23-49.25)
Delivery               build once, promote a digest, drain on deploy    (49.26, 49.27, 49.31)
Observability          measure the experience, not the server           (49.28, 49.29)
Security + OSS         assume each layer can fail; give back upstream   (49.30, 49.32)
```

## The Two Rules That Hold The Architecture Together

**1. One writer per piece of state.**

```text
Document text          -> CRDT only
Server data            -> query cache only (never copied into useState)
Machine-generated UI   -> registry only (never arbitrary components)
Billing/membership     -> server only (never queued offline)
```

Almost every severe bug in this chapter is two writers on one value - the query cache and the CRDT both writing text, or a client and a server both deciding permissions.

**2. Every boundary is validated and authorised on the server side.**

The UI is a convenience. Server actions, route handlers and the socket upgrade are public endpoints, and each one re-checks identity and permission before it touches data.

## The Big Rule

Build the smallest version that still has all five properties. A polished CRUD app without convergence, offline support and server-side authorisation is not a smaller Atlas - it is a different, easier project that teaches none of the lessons this one does.

Reach for the hard part first: get two clients editing one document offline, then everything else has a place to attach.

*Educational use only - AI-assisted content. See [DISCLAIMER.md](../DISCLAIMER.md) and [LICENSE.md](../LICENSE.md).*
