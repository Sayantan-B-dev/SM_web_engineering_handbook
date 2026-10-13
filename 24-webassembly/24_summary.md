# 24. WEBASSEMBLY - Complete Deep Dive

## 24.12 WebAssembly - Summary

### When to Use WASM
✅ **Compute-intensive tasks >100ms** - image processing, cryptography, simulation.
✅ **Porting existing C/C++/Rust code** - avoid rewriting algorithms in JS.
✅ **Performance-critical hot paths** - 2-4× faster than JS for heavy computation.
✅ **Server-side microservices** - SpinKube, wasmCloud, Fermyon at 75M RPS.
✅ **React virtualization** - Warper at 120 FPS with 1M items.

### When NOT to Use WASM
❌ **CRUD apps** - JS is sufficient and simpler.
❌ **Text processing** - string interop overhead dominates.
❌ **Small tasks** - interop overhead makes WASM slower.
❌ **DOM-heavy UI** - WASM has no DOM access.

### The Big Rule
> WebAssembly is a **compilation target for compute-intensive workloads**, not a JavaScript replacement. Use it when you have proven, measured performance bottlenecks that JS cannot solve. Always benchmark before and after. Always run it in a Web Worker. Always use Transferable Objects for large buffers. And always remember: **interop is the bottleneck, not the computation**.
