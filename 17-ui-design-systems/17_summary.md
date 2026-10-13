# 17. UI / DESIGN SYSTEMS - Complete Deep Dive

## Summary: UI / Design Systems Deal-Breaker Checklist

| Area | Deal-Breaker | Consequence |
|------|-------------|-------------|
| **Design Systems** | Components before tokens | Changing brand color touches 40 files |
| **Design Systems** | No governance model | System becomes a dumping ground |
| **Design Systems** | Accessibility bolted on | 10× cost to retrofit |
| **Component Libraries** | React not a peer dep | Two React copies, hooks break |
| **Component Libraries** | No tree-shaking | Import one Button, ship 500KB |
| **Component Libraries** | Boolean prop explosion | 128 combinations |
| **Design Tokens** | Tokens only in Figma | Engineers hardcode hex values |
| **Design Tokens** | No typed TS map | `bg-primry` renders wrong |
| **Design Tokens** | Theming at component tier | Every theme forks components |
| **Accessibility** | Reimplementing a combobox | 200 lines of fragile keyboard handling |
| **Accessibility** | No a11y tests in CI | Regressions ship silently |
| **Headless UI** | Overriding primitive behavior | Broken keyboard/focus/ARIA |
| **Radix** | Fighting accessibility | You break what you didn't build |
| **Radix** | Per-component packages, no pinning | Version drift between primitives |
| **shadcn/ui** | No update mechanism | Missing upstream fixes |
| **shadcn/ui** | Customizing without CVA | Unmaintainable conditional classes |
| **Tailwind** | `@apply` everywhere | Recreates CSS architecture you avoided |
| **Tailwind** | No `tailwind-merge` | Conflicting classes resolve unpredictably |
| **CSS Modules** | No `.module.css` suffix | Global style collisions |
| **CSS Modules** | No TS declaration | Import errors, no autocomplete |
| **CSS-in-JS** | Runtime CSS-in-JS in RSC | Incompatible |
| **CSS-in-JS** | `styled-components` for new apps | Building on a declining foundation |

---

**The Big Rule:** Build tokens first, then primitives, then components. Use headless primitives (Radix/Base UI) for behavior. Style with Tailwind or CSS Modules. Ship accessibility at v1. Theme at the semantic token tier only.
