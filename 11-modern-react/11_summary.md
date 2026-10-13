# 11. MODERN REACT - Complete Deep Dive

## Summary: Modern React Deal-Breaker Checklist

| Area | Deal-Breaker | Consequence |
|------|-------------|-------------|
| **RSC** | Hooks in Server Components | Build error |
| **RSC** | No Suspense boundaries | Entire page blocks |
| **Server Components** | `process.env.SECRET` in client | Secret leaked |
| **Client Components** | `'use client'` on parent | Entire subtree client-bundled |
| **Client Components** | `async` Client Component | Invalid |
| **Server boundaries** | Passing class instances | Runtime error |
| **Server boundaries** | Functions (non-Server-Action) as props | Error |
| **Client boundaries** | Client importing Server Component | Build error |
| **`use client`** | Directive not first line | Silently ignored |
| **`use client`** | Backticks | Silently ignored |
| **`use server`** | No input validation | Security vulnerability |
| **`use server`** | No rate limiting | Abuse |
| **Serialization** | `new Intl.NumberFormat()` as prop | Runtime error |
| **Serialization** | `Symbol` as prop | Error |
| **Server Actions** | Assuming private | Public endpoint |
| **Server Actions** | No authorization | Unauthorized mutation |
| **Streaming** | No Suspense | Whole page blocks |
| **Streaming** | Fallback ≠ content layout | CLS |
| **Hydration** | Expecting RSC to hydrate | Wrong mental model |
| **Hydration** | `Date`/`Math.random` in Client Component | Mismatch |
