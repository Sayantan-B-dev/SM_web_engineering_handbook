# 30. GENERATIVE UI - Complete Deep Dive

## 30.13 Generative UI - Summary Deal-Breaker Checklist

| Area | Deal-Breaker | Consequence |
|------|-------------|-------------|
| **Fundamentals** | `dangerouslySetInnerHTML` for LLM output | XSS vulnerability |
| **Fundamentals** | No Zod validation at stream boundary | Malformed JSON crashes renderer |
| **Fundamentals** | No component registry | JSON types don't map to components |
| **AI-Generated Interfaces** | One-shot generation | Users can't refine the UI |
| **AI-Generated Interfaces** | No editable intent | AI misunderstanding can't be corrected |
| **json-render** | No catalog | AI generates arbitrary components |
| **json-render** | No Zod schemas | Props are `any`; runtime errors |
| **A2UI** | Assuming Google Cloud required | It's framework-agnostic and open |
| **A2UI** | No catalog | Agent generates components you don't have |
| **Streaming JSON** | No incremental parser | You wait for full JSON before rendering |
| **Streaming JSON** | No layout shift prevention | CLS as content streams in |
| **Declarative** | No catalog | AI generates components you don't have |
| **Declarative** | Using for brand-critical surfaces | AI layout may not match design |
| **Controlled** | No progressive rendering | Users wait for full tool result |
| **Controlled** | Too many tools | Agent gets confused (>15) |
| **Open-Ended** | `dangerouslySetInnerHTML` without sanitization | XSS |
| **Open-Ended** | No CSP | Script injection |
| **Open-Ended** | No prompt injection defense | Agent executes malicious instructions |
| **Component Registry** | No Zod schema per component | Props are `any`; runtime errors |
| **Component Registry** | No fallback | Unknown component types crash renderer |
| **AI Interaction Design** | No proposal-first | AI generates without approval |
| **AI Interaction Design** | No undo | User can't recover from bad generation |
| **Security** | `dangerouslySetInnerHTML` on model output | XSS (CVE-2026-17496) |
| **Security** | No CSP | Script injection |
| **Security** | No approval for destructive tools | Agent deletes production data |
| **Performance** | No `contain: layout` | Streaming content reflows entire page |
| **Performance** | No reserved space | CLS as content streams in |
| **Accessibility** | No accessibility in catalog | AI generates inaccessible components (29% compliance) |
| **Accessibility** | No color contrast validation | 26.8% adherence |
| **Accessibility** | No keyboard navigation | Focus issues and keyboard failures |

---

**The Big Rule:** Generative UI is not "AI generates HTML." It's **typed component trees from streaming JSON schemas**. Define a catalog with Zod schemas. Validate every node at the stream boundary. Map catalog types to a component registry. Never use `dangerouslySetInnerHTML` on model output. Bake accessibility into the catalog. Reserve space to prevent CLS. Choose the right paradigm: **controlled** for brand-critical, **declarative** for the long tail, **open-ended** only for sandboxed, non-critical surfaces. And always treat model output as untrusted.
