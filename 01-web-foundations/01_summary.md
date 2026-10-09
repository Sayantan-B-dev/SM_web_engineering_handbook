# 1. WEB FOUNDATIONS — Complete Deep Dive

## Summary: WEB FOUNDATIONS Deal-Breaker Checklist

| Area | Deal-Breaker | Consequence |
|------|-------------|-------------|
| **HTML** | Missing `alt` | WCAG failure, no image SEO |
| **HTML** | Multiple H1s | Confused crawlers |
| **Semantic** | Div soup | No landmarks for AT |
| **Forms** | No server validation | Security breach |
| **Forms** | No `<label>` | Inaccessible inputs |
| **Accessibility** | `outline: none` | Keyboard users lost |
| **Accessibility** | Color-only info | Colorblind users blocked |
| **ARIA** | `aria-hidden` on focusable | AT invisibility violation |
| **ARIA** | `role="button"` on div | Broken keyboard behavior |
| **SEO** | Generic titles | Poor CTR, no ranking |
| **SEO** | No structured data | No rich snippets |
| **DOM** | Layout thrashing | Jank, dropped frames |
| **DOM** | `innerHTML +=` | Lost listeners, state |
| **CRP** | Render-blocking JS | Blank page until loaded |
| **CRP** | No image dimensions | CLS penalty |

---

Next topic? Send **2. CSS** or any other numbered topic from your list and I'll give the same treatment.
