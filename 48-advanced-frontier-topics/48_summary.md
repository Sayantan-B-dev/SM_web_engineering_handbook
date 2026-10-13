# 48. ADVANCED / FRONTIER TOPICS - Complete Deep Dive

## 48.17 Summary: Advanced / Frontier Topics Deal-Breaker Checklist

| Area | Deal-Breaker | Consequence |
|------|-------------|-------------|
| **React Compiler** | Relying on referential equality for correctness | Compiler may break your app |
| **React Compiler** | Manual memo mismatches compiler output | Entire component bails out |
| **RSC** | Hooks in Server Components | Build error |
| **RSC** | No Suspense boundaries | Entire page blocks |
| **Concurrent React** | Input value in `startTransition` | Laggy typing |
| **Distributed Browser** | No privacy controls | Running untrusted code |
| **WebAssembly** | SharedArrayBuffer without COOP/COEP | Throws |
| **WebAssembly** | WASM on main thread | Blocks UI |
| **Web Workers** | PostMessage chains for multi-window | Coordination complexity |
| **Web Workers** | Service Worker for application state | Wrong abstraction |
| **WebRTC** | No TURN server | 10-20% of connections fail |
| **WebRTC** | Unreliable channel for critical data | Packet loss |
| **Local-First** | No sync engine | Just a local database |
| **Local-First** | Server as source of truth | Not local-first |
| **CRDTs** | Yjs for JSON-heavy apps | Automerge is better |
| **CRDTs** | No GC | Tombstones accumulate |
| **In-Browser ML** | No WebGPU fallback | 15% of users can't use it |
| **In-Browser ML** | Main-thread inference | Blocks React rendering |
| **AI Agents** | No max steps | Agent loops forever |
| **AI Agents** | No tool validation | Hallucinated tool names |
| **Generative UI** | `dangerouslySetInnerHTML` | XSS |
| **Generative UI** | No Zod validation at boundary | Malformed JSON crashes renderer |
| **AI-Native Architecture** | No component registry | AI can't map intents to components |
| **AI-Native Architecture** | No latency budget | >200ms feels broken |
| **AI Safety** | No prompt-injection guard | Malicious input reaches model |
| **AI Safety** | Excessive agency | Agent has too many permissions |
| **Observability** | No PII filter | User data logged |
| **Observability** | No `propagateTraceHeaderCorsUrls` | Browser and backend traces disconnected |
| **Distributed Systems** | Edge for database queries | Cold start + DB latency |
| **Distributed Systems** | No cache identity | Edge functions can't coordinate |

---

**The Big Rule:** The frontier is **convergence, not isolation**. React Compiler eliminates manual memoization. RSC is production-ready. Concurrent React is default. WASM 3.0 ships GC and threads. SharedWorkers are in all browsers. WebRTC data channels work serverlessly via QR signaling. Local-first with SQLite WASM + PowerSync + Supabase is the new default stack. Loro is the fastest CRDT. Transformers.js v4 runs 20B models at 60 tokens/sec in the browser. A2UI v0.9 standardizes agent-to-UI communication. json-render makes generative UI practical. Intent-based architecture replaces responsive design. AI safety is system safety, not model safety. Grafana Faro + OTel is the observability stack. And edge compute belongs on routing, auth, and personalization - not database queries.

*Educational use only - AI-assisted content. See [DISCLAIMER.md](../DISCLAIMER.md) and [LICENSE.md](../LICENSE.md).*
