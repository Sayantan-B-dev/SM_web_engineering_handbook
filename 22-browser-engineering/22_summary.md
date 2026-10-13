# 22. BROWSER ENGINEERING - Complete Deep Dive

## Summary: Browser Engineering Deal-Breaker Checklist

| Area | Deal-Breaker | Consequence |
|------|-------------|-------------|
| **Architecture** | Assuming single-threaded | Rendering, JS, GC all block each other |
| **Architecture** | No site isolation awareness | Cross-origin iframes can't sync-access DOM |
| **Rendering** | Animating `width`/`left` | Layout + paint + composite every frame |
| **Rendering** | Reading `offsetHeight` in loop | Forced synchronous layout |
| **Rendering** | `will-change` overuse | GPU memory exhaustion |
| **JS Engine** | Type instability | Deoptimization, slow bytecode |
| **JS Engine** | `delete` on properties | Hidden class change, slow access |
| **Event Loop** | Infinite microtask chain | Browser freeze |
| **Event Loop** | Long tasks > 50ms | Blocked input and rendering |
| **Networking** | HTTP/1.1 with many requests | Head-of-line blocking |
| **Networking** | No `preconnect` | 200-500ms added latency |
| **Storage** | `localStorage` for large data | Blocks main thread, 5MB limit |
| **Storage** | No `navigator.storage.persist()` | Data evicted under pressure |
| **Workers** | CPU-heavy work on main thread | Jank, dropped frames |
| **Workers** | `SharedArrayBuffer` without COOP/COEP | Throws |
| **Performance** | Only Long Tasks, not LoAF | No attribution |
| **Security** | No CSP | XSS vulnerability |
| **Security** | No COOP/COEP | No `SharedArrayBuffer` |
| **Modern APIs** | WebGPU without WebGL2 fallback | Broken on older Safari |
| **Modern APIs** | View Transitions as hard dependency | Firefox users get nothing |

---

**The Big Rule:** The browser is a multi-process, multi-threaded operating system. The main thread does everything - JS, style, layout, paint, GC - and must never be blocked for more than 50ms. The compositor thread handles `transform` and `opacity` animations independently. Move CPU work to Web Workers. Use HTTP/3 + QUIC. Store structured data in IndexedDB, not `localStorage`. Lock down security with CSP, COOP, and COEP. And always provide fallbacks for frontier APIs.

*Educational use only - AI-assisted content. See [DISCLAIMER.md](../DISCLAIMER.md) and [LICENSE.md](../LICENSE.md).*
