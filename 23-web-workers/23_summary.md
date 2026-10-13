# 23. WEB WORKERS - Complete Deep Dive

## 23.12 Web Workers - Summary Deal-Breaker Checklist

| Area | Deal-Breaker | Consequence |
|------|-------------|-------------|
| **Fundamentals** | DOM access in worker | `document` is `undefined` |
| **Fundamentals** | `localStorage` in worker | Not available; use IndexedDB |
| **Fundamentals** | Spawning per task | 0.5-1ms overhead per spawn |
| **Types** | Service Worker for CPU work | Can be killed at any time |
| **Types** | Shared Worker without `port.start()` | Messages never arrive |
| **Lifecycle** | No `onerror` handler | Worker errors silently swallowed |
| **Lifecycle** | No `terminate()` | Memory leak, CPU waste |
| **Message Passing** | Large objects without transferables | 302ms vs 6.6ms for 32MB |
| **Message Passing** | No backpressure | Worker floods main thread's event loop |
| **Structured Clone** | Cloning functions | `DataCloneError` |
| **Transferables** | Using a transferred buffer in source | `byteLength === 0`, detached |
| **SharedArrayBuffer** | Without COOP/COEP | Throws in Chrome 91+ |
| **SharedArrayBuffer** | No `Atomics` | Data races, undefined behavior |
| **CPU Workloads** | Offloading <100ms tasks | Slower than main thread |
| **CPU Workloads** | No progress reporting | Frozen UI, no feedback |
| **Off-Main-Thread** | OffscreenCanvas not used | Main thread blocked by rendering |
| **Shared Memory** | No memory barriers | CPU reordering, partial writes |
| **Architecture** | Worker holds authoritative state | State drift between threads |
| **Architecture** | No request/response IDs | Race conditions, mismatched responses |
| **WASM** | WASM on main thread | Still blocks UI |
| **Performance** | Pool size = `hardwareConcurrency` | Oversubscription, main thread starves |
| **Performance** | Not profiling workers | Unknown bottleneck |

---

**The Big Rule:** Use Web Workers for tasks **>100ms** that don't need DOM access. Use **Transferable Objects** for large binary data (zero-copy). Keep the **main thread as the authoritative state holder**. Use a **worker pool** to avoid spawn overhead. Use **OffscreenCanvas** for rendering offload. Always **profile** before and after - workers are not always faster.
