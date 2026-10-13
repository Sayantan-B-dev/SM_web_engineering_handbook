# 7. REACT MENTAL MODELS - Complete Deep Dive

## Summary: React Mental Models Deal-Breaker Checklist

| Model | Deal-Breaker | Consequence |
|-------|-------------|-------------|
| **Rendering** | Side effects in render | Multiple executions, inconsistent UI |
| **Re-rendering** | Deep state at top | Whole app re-renders |
| **Render phase** | Reading refs during render | Non-deterministic output |
| **Commit phase** | `useLayoutEffect` for fetching | Blocks paint |
| **Reconciliation** | Conditional element-type flip | State lost |
| **Identity** | Component defined in render | Remount every render |
| **Referential eq.** | Inline object props | Breaks `React.memo`, effects re-run |
| **Batching** | Expecting sync state read | Stale value |
| **Stale closures** | Empty deps + state read | Old values forever |
| **Effects vs events** | useEffect for user actions | Indirect, fragile |
| **Derived state** | Duplicated computed values | Sync bugs |
| **State ownership** | Global state for local UI | Unnecessary re-renders |
| **Composition** | Deep HOC chains | Wrapper hell |
