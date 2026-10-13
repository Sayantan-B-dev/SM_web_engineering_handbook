# 6. REACT HOOKS - Complete Deep Dive

## Summary: React Hooks Deal-Breaker Checklist

| Hook | Deal-Breaker | Consequence |
|------|-------------|-------------|
| **useState** | Mutating state directly | No re-render |
| **useState** | Reading state after setter | Stale value |
| **useEffect** | Missing deps | Stale closures |
| **useEffect** | No cleanup for subs/timers | Memory leaks |
| **useEffect** | Async function directly | Returns Promise, no cleanup |
| **useEffect** | Fetch without abort | Race condition |
| **useEffect** | Object/function in deps | Runs every render |
| **useRef** | Reading `.current` during render | Unreliable in concurrent mode |
| **useRef** | Using ref for UI-driving values | No re-render |
| **useMemo** | Memoizing cheap computations | Overhead, no benefit |
| **useMemo** | Object in deps | Recomputes every render |
| **useCallback** | Missing deps | Stale closures |
| **useCallback** | On non-memoized child | Zero benefit |
| **useReducer** | Mutating state in reducer | No re-render |
| **useReducer** | Async work in reducer | Impure reducer |
| **useReducer** | Dispatch in render | Infinite loop |
| **useContext** | Unmemoized provider value | All consumers re-render |
| **useContext** | No default/sentinel | Runtime error |
| **Custom Hooks** | Not starting with `use` | ESLint can't enforce rules |
| **Rules** | Conditional hook call | Corrupted state |
| **Rules** | Early return before hooks | Hook order mismatch |

*Educational use only - AI-assisted content. See [DISCLAIMER.md](../DISCLAIMER.md) and [LICENSE.md](../LICENSE.md).*
