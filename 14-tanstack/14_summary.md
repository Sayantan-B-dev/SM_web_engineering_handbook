# 14. TANSTACK - Complete Deep Dive

## Summary: TanStack Deal-Breaker Checklist

| Area | Deal-Breaker | Consequence |
|------|-------------|-------------|
| **TanStack Query** | Using for client state | Wrong tool; use Zustand/Jotai |
| **Queries** | Query function not throwing | Errors treated as success |
| **Mutations** | `mutateAsync` without try/catch | Unhandled rejection |
| **Mutations** | Invalidate in `onSuccess` only | Stale cache on error |
| **Query Keys** | Non-array key | Runtime error |
| **Query Keys** | Key without variables | All IDs share cache |
| **Cache** | `gcTime` < `staleTime` | Data GC'd before stale |
| **Stale Time** | Default `staleTime: 0` | Refetch on every mount |
| **Garbage Collection** | `gcTime: 0` | No cache benefit |
| **Optimistic Updates** | No cancel in `onMutate` | Race condition |
| **Optimistic Updates** | No snapshot returned | No rollback |
| **Invalidation** | `invalidateQueries` with no key | Invalidates all |
| **Invalidation** | No invalidation after mutation | Stale UI |
| **Pagination** | No `keepPreviousData` | Flash of empty state |
| **Infinite Queries** | Missing `initialPageParam` | v5 error |
| **Infinite Queries** | No `maxPages` | Memory bloat |
| **Prefetching** | No `staleTime` on prefetch | Prefetch wasted |
| **TanStack Router** | No `validateSearch` | Runtime errors |
| **TanStack Start** | No CSRF middleware | Cross-site request vulnerability |
| **TanStack Start** | No input validation | Security vulnerability |
