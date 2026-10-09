# 4. TYPESCRIPT — Complete Deep Dive

## Summary: TypeScript Deal-Breaker Checklist

| Area | Deal-Breaker | Consequence |
|------|-------------|-------------|
| **Types** | `any` everywhere | No type safety |
| **Types** | Numeric enums | Reverse mapping confusion |
| **Interfaces** | `readonly` is shallow | Nested mutation allowed |
| **Interfaces** | Over-merging | Conflicting declarations |
| **Type Aliases** | Over-aliasing primitives | No value added |
| **Generics** | Unconstrained `T` | Property access errors |
| **Generics** | Too many type params | Unusable API |
| **Unions** | No discriminant | Can't narrow |
| **Unions** | Missing exhaustiveness | Silent runtime errors |
| **Intersections** | Conflicting properties | `never` type |
| **Utility Types** | `Partial` is shallow | Nested required fields |
| **Utility Types** | `Omit` doesn't validate keys | Silent typos |
| **Narrowing** | `as` instead of guards | Runtime crashes |
| **Narrowing** | `typeof null === 'object'` | Null check missed |
| **Discriminated Unions** | Non-literal discriminant | No narrowing |
| **Discriminated Unions** | No `never` check | Missing case not caught |
| **`unknown` vs `any`** | `any` in signatures | Type safety lost |
| **`unknown` vs `any`** | Catch without narrowing | `err.message` error |
| **Function Typing** | Overload implementation mismatch | Compile error |
| **Function Typing** | `void` misunderstood | Return value ignored |
| **Mapped Types** | `keyof` on arrays | Includes array methods |
| **Conditional Types** | Forgetting distribution | Unexpected union behavior |
| **Conditional Types** | Infinite recursion | "Excessively deep" error |
| **Advanced Generics** | Branded types without validation | Unsafe cast |
| **Type-Safe APIs** | `as T` without validation | Runtime crashes |
| **Type-Safe APIs** | Unvalidated env vars | Production crash |

---

Next topic? Send **5. React Fundamentals** and I'll give the same complete treatment.
