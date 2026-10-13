# 12. NEXT.JS - Complete Deep Dive

## Summary: Next.js Deal-Breaker Checklist

| Area | Deal-Breaker | Consequence |
|------|-------------|-------------|
| **App Router** | No root `layout.tsx` | Build error |
| **Routing** | `useRouter` in Server Component | Error; use `redirect()` |
| **Layouts** | Assuming re-render on navigation | State preserved; use `template.tsx` |
| **Dynamic Routes** | Not awaiting `params` | Next.js 15+ error |
| **Parallel Routes** | No `default.tsx` | Build error |
| **Intercepting** | Wrong dots | Route not intercepted |
| **Server Components** | Hooks in RSC | Build error |
| **Client Components** | `'use client'` on parent | Entire subtree client-bundled |
| **Server Boundaries** | Passing class instances | Runtime error |
| **`use client`** | Directive after imports | Ignored |
| **`use server`** | No validation | Security vulnerability |
| **Server Actions** | Assuming private | Public endpoint |
| **Streaming** | No `<Suspense>` | Entire page blocks |
| **Middleware/Proxy** | Heavy logic | Every request slowed |
| **Rendering** | `revalidate = 0` | No caching |
| **Caching** | Assuming fetch cached | Actually cached by default |
| **Revalidation** | No revalidation after mutation | Stale UI |
| **Data Fetching** | Sequential awaits | Slow; use `Promise.all` |
| **Deployment** | No `standalone` output | Huge Docker image |
