# 13. STATE MANAGEMENT - Complete Deep Dive

## Summary: State Management Deal-Breaker Checklist

| Category | Deal-Breaker | Consequence |
|----------|-------------|-------------|
| **Local** | State lifted too high | Whole tree re-renders |
| **Derived** | Stored in state | Sync bugs |
| **Global** | Globalizing local state | Unnecessary complexity |
| **Global** | Globalizing server state | Duplicate caches, stale data |
| **Server** | `useEffect` + `useState` for fetch | No cache, no dedup |
| **URL** | Filters in `useState` | Not shareable, back button breaks |
| **Form** | Global store for form | Overkill |
| **Cache** | Cache as source of truth | Stale data |
| **Context** | Unmemoized value | All consumers re-render |
| **Context** | Global app state in context | "Context hell" |
| **Redux** | Plain Redux | Boilerplate explosion |
| **Redux** | Server state in Redux | Rebuilding React Query poorly |
| **Redux** | `useSelector` new refs | Re-renders every dispatch |
| **RTK** | Ignoring RTK Query | Rebuilding caching yourself |
| **Zustand** | No selectors | All components re-render |
| **Jotai** | Too many small atoms | Hard to track |
| **SWR** | No revalidation policy | Unexpected refetches |

---

**The Big Rule:** Match the tool to the state type.
- **UI state** → local (`useState`) or URL
- **Server state** → React Query / SWR / RTK Query
- **Global client state** → Zustand / Jotai / Redux (in that order of preference)
- **Form state** → React Hook Form
