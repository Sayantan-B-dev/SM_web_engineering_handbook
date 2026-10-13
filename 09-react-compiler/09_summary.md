# 9. REACT COMPILER - Complete Deep Dive

## Summary: React Compiler Deal-Breaker Checklist

| Area | Deal-Breaker | Consequence |
|------|-------------|-------------|
| **React Compiler** | Plugin not first in Babel pipeline | Wrong analysis, incorrect output |
| **React Compiler** | Using `eval`/`with` | Component silently skipped |
| **Automatic memoization** | Relying on referential equality for correctness | Compiler may break app |
| **Automatic memoization** | Expecting compiler to fix all perf issues | Algorithmic problems remain |
| **Transformations** | Mutating during render | Bailout, no optimization |
| **Transformations** | `try/catch` around render | Bailout |
| **`use memo`** | Using instead of fixing naming | Masks code smell |
| **`use memo`** | Directive not first statement | Ignored |
| **`use no memo`** | Everywhere | Zero benefit from compiler |
| **`use no memo`** | No removal plan | Permanent perf loss |
| **Configuration** | `compilationMode: 'all'` | Utility functions compiled incorrectly |
| **Configuration** | Disabling validation | Missed bugs |
| **Limitations** | Rules of React violations | Silent bailout, no warning |
| **Limitations** | No warnings on bailout | Don't know component wasn't optimized |
| **Limitations** | Memoization-dependent correctness | Infinite loops, missing updates |
| **Manual memoization** | Doesn't match compiler output | Entire component bails out |
| **Manual memoization** | Double memoization | Overhead, maintenance burden |
| **Manual memoization** | Removing before enabling compiler | Performance regression |
| **Performance** | No benchmarking | Unknown impact |
| **Performance** | Not checking "Memo ✨" badge | Silent skip undetected |
