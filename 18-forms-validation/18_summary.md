# 18. FORMS & VALIDATION - Complete Deep Dive

## Summary: Forms & Validation Deal-Breaker Checklist

| Area | Deal-Breaker | Consequence |
|------|-------------|-------------|
| **RHF** | Missing `defaultValues` | Uncontrolled warnings, `undefined` state |
| **RHF** | `Controller` for every input | Unnecessary re-renders |
| **RHF** | Index as key in `useFieldArray` | Field state jumps on reorder |
| **RHF** | `useFormContext` without `React.memo` | Full-form re-renders |
| **RHF** | Not spreading `{...field}` in `Controller` | Field doesn't work |
| **TanStack Form** | Overkill for simple forms | More code, smaller ecosystem |
| **Conform** | Used outside Server Actions | No benefit; use RHF |
| **Zod** | No `path` in `.refine()` | Error on wrong field |
| **Zod** | `.parse()` in forms | Throws on failure |
| **Zod** | No `z.coerce` for numeric fields | Form values are strings |
| **Zod** | Client-only validation | Security vulnerability |
| **State** | Controlled inputs for large forms | Full re-render per keystroke |
| **State** | Switching controlled ↔ uncontrolled | React warning |
| **Best Practices** | No `noValidate` on form | Browser validation conflicts |
| **Best Practices** | Not mapping server errors | Generic error messages |
| **Multi-Step** | No `shouldUnregister` | Old step data persists |
| **Accessibility** | No `role="alert"` on errors | Screen readers miss errors |
| **Accessibility** | No `aria-invalid` | AT doesn't know field is invalid |
| **Server** | Different client/server schemas | Schema drift |
| **Server** | No server validation | Security vulnerability |

---

**The Big Rule:** The 2026 default stack is **React Hook Form + Zod + `zodResolver`**. Use TanStack Form when TypeScript inference is the top priority for deeply nested forms. Use Conform when Server Actions and progressive enhancement are the architecture. Always validate on the server.
