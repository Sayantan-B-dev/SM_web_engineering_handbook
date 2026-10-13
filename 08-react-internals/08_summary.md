# 8. REACT INTERNALS - Complete Deep Dive

## Summary: React Internals Deal-Breaker Checklist

| Area | Deal-Breaker | Consequence |
|------|-------------|-------------|
| **Virtual DOM** | Believing it's "free" | Wasted CPU on giant trees |
| **Fiber** | Side effects in render | Duplicated work on discarded renders |
| **Reconciliation** | Missing/wrong keys | Wrong DOM updates, lost state |
| **Reconciliation** | Conditional type flip | Full remount, state reset |
| **Scheduling** | Long sync tasks | Scheduler can't help - UI freezes |
| **Concurrent** | Impure components | Broken discarded renders |
| **Concurrent** | Legacy `ReactDOM.render` | No concurrent features |
| **Lanes** | Assuming 1 update = 1 lane | Wrong mental model |
| **Suspense** | No error boundary | Uncaught errors crash UI |
| **Suspense** | Data without Suspense-aware source | Fallback never shows |
| **Transitions** | Input value in transition | Laggy typing |
| **Streaming** | No Suspense boundary | Nothing streams |
| **Hydration** | Date/Math.random in render | Mismatch warnings |
| **Hydration** | `window` in render | SSR crash |
| **Selective hydration** | No boundaries | Whole tree waits |
| **React scheduling** | `flushSync` in hot paths | Jank |
