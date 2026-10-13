# 10. REACT PERFORMANCE - Complete Deep Dive

## Summary: React Performance Deal-Breaker Checklist

| Area | Deal-Breaker | Consequence |
|------|-------------|-------------|
| **Profiler** | No profiling, guessing | Optimizing wrong things |
| **DevTools** | "Why did this render" off | Blind debugging |
| **Render profiling** | Ignoring commit time | DOM/layout bottleneck missed |
| **Memoization** | Over-memoizing trivial values | Slower than no memo |
| **Memoization** | `React.memo` + inline props | Memo never fires |
| **Component splitting** | State too high | Whole tree re-renders |
| **Lazy loading** | Lazy-loading above-fold | LCP regression |
| **Code splitting** | No preload for interactive chunks | "Broken button" feel |
| **Dynamic imports** | No error handling | White screen on chunk load fail |
| **Bundle analysis** | Never analyzing bundle | 500KB surprise library |
| **Tree shaking** | Barrel files | Entire library bundled |
| **Network** | No compression | 3-4× larger downloads |
| **Image optimization** | Lazy-loading LCP image | Direct LCP damage |
| **Image optimization** | No width/height | CLS |
| **Font optimization** | No `font-display` | Invisible text (FOIT) |
| **CPU bottlenecks** | 10K list items rendered | Seconds of jank |
| **Network bottlenecks** | Fetch on every keystroke | CPU + network exhaustion |
| **Core Web Vitals** | CSR above the fold | LCP > 4s |
