# 33. IN-BROWSER AI / ML - Complete Deep Dive

## 33.10 In-Browser AI - Summary Deal-Breaker Checklist

| Area | Deal-Breaker | Consequence |
|------|-------------|-------------|
| **Landscape** | Assuming one backend fits all | 10-15× performance difference between WebGPU and WASM |
| **Landscape** | Ignoring cold-start penalty | 1-5s shader compilation on first WebGPU run |
| **WebGPU** | Naive single-operation measurements | 20× overestimate of per-dispatch cost |
| **WebGPU** | Assuming WebGPU is always faster | Small tensors may not benefit |
| **WebGPU** | No fallback strategy | WebGPU → WebGL → WASM hierarchy required |
| **WebNN** | Assuming production-ready | W3C Candidate Recommendation, origin trial only |
| **Client-Side Inference** | Large model loading without caching | 8-12s download on Fast 3G |
| **Client-Side Inference** | Main-thread contention | 150-300MB peak memory; React reconciliation blocked |
| **Model Loading** | Naive bundling of `.onnx` files | Oversized bundle or error |
| **Model Loading** | No quantization | 4× larger and slower models |
| **Model Optimization** | No Web Worker | UI feels frozen during model execution |
| **Model Optimization** | No memory teardown | GC pauses cause visible frame drops |
| **AI Performance** | Dispatch overhead dominates | Kernel fusion is the effective optimization at batch size 1 |
| **AI Performance** | Memory constraints | Largest browser model required 31.5GB WebGPU memory |
| **Privacy-Preserving AI** | Policy-based privacy | Only architectural privacy (no data leaves device) is a guarantee |
| **Tools & Libraries** | TensorFlow.js WebGPU not bundled | WebGPU is a separate, optional package |
| **Tools & Libraries** | No engine fallback | Feature-detect Prompt API → WebLLM → wllama |
| **Prompt API** | Assuming universal availability | Chrome Canary/Dev only |
| **Prompt API** | No fallback | App breaks when Prompt API is unavailable |

---

**The Big Rule:** In-browser AI is production-ready in 2026, but the **backend choice is the single most consequential decision**. WebGPU for large models (>100M params), WASM for small models (<100M params) and single-pass tasks. Always quantize (INT8, Q4F16). Always cache models (Cache API, OPFS). Always offload to a Web Worker. Always feature-detect and provide fallback (WebGPU → WebGL → WASM → Prompt API). And always measure - the difference between the right and wrong backend can be 10-15×.
