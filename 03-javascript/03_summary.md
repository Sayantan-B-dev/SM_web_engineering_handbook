# 3. JAVASCRIPT — Complete Deep Dive

## Summary: JavaScript Deal-Breaker Checklist

| Area | Deal-Breaker | Consequence |
|------|-------------|-------------|
| **Variables** | `var` in loops + closures | All closures share final value |
| **Scope** | Accidental globals | Memory leaks, collisions |
| **Closures** | Capturing large data in long-lived listeners | Memory never freed |
| **`this`** | Arrow function as object method | Wrong `this` |
| **Prototypes** | Mutating `Object.prototype` | Breaks all objects globally |
| **Objects** | `||` instead of `??` | `0`/`''`/`false` treated as missing |
| **Arrays** | `sort()` without comparator | String sort (`[1,10,9]`) |
| **Destructuring** | Destructuring `null`/`undefined` | TypeError |
| **Spread** | Shallow copy mistaken for deep | Nested mutations affect original |
| **Modules** | Circular dependencies | `undefined` imports |
| **HOFs** | Memoizing with `JSON.stringify` | Slow, fails on circular refs |
| **Callbacks** | Zalgo (sync/async inconsistency) | Unpredictable ordering |
| **Promises** | Unhandled rejection | Process crash |
| **async/await** | `await` in loop | Sequential instead of parallel |
| **Event Loop** | Infinite microtask chain | Browser freeze |
| **Fetch** | Not checking `res.ok` | 404/500 treated as success |
| **AbortController** | Reusing aborted signal | Always aborted |
| **DOM Events** | Anonymous listener | Can't remove → leak |
| **Delegation** | `stopPropagation` in children | Breaks parent delegation |
| **Iterators** | Modifying array during `for...of` | Skipped elements |
| **Generators** | Forgetting laziness | Code doesn't run until `.next()` |
| **Errors** | Swallowing errors silently | Hidden bugs |
| **Memory** | Forgotten timers/listeners | Leaks |
| **GC** | Relying on `FinalizationRegistry` for cleanup | Non-deterministic |
| **Execution** | Blocking main thread | UI freeze |
| **Execution** | Type instability | Deoptimization |

---

Next topic? Send **4. TypeScript** and I'll give the same complete treatment.
