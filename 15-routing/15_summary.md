# 15. ROUTING - Complete Deep Dive

## Summary: Routing Deal-Breaker Checklist

| Area | Deal-Breaker | Consequence |
|------|-------------|-------------|
| **Fundamentals** | No route boundaries | One error crashes the app |
| **React Router** | Importing from `react-router-dom` | Package removed in v7 |
| **React Router** | Using Declarative mode for data-heavy apps | No loaders, manual fetching |
| **Nested Routing** | Missing `<Outlet>` | Child routes never render |
| **Nested Routing** | Absolute paths in children | Nesting breaks |
| **Data Routers** | No `<RouterProvider>` | Router not mounted |
| **Loaders** | Fetching in `useEffect` | Waterfall |
| **Loaders** | Not throwing on error | Component crashes later |
| **Actions** | No `redirect` after action | Resubmit on refresh |
| **Actions** | Forgetting `method="post"` | Action never called |
| **Route Boundaries** | No root error boundary | Blank page on error |
| **Route Boundaries** | Missing nested boundaries | One route crashes all |
| **TanStack Router** | No Vite plugin | Route tree not generated |
| **TanStack Router** | `as Type` casts | Defeats type safety |
| **TanStack Router** | No `loaderDeps` | Loader doesn't re-run on search change |
| **TanStack Router** | No `validateSearch` | Runtime errors from search params |
| **Preloading** | No preload | "Broken button" feel |
| **Preloading** | No `preloadDelay` | Excessive network calls |
| **Comparison** | No evaluation before choosing | Costly migration later |
