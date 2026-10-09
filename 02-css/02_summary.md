# 2. CSS — Complete Deep Dive

## Summary: CSS Deal-Breaker Checklist

| Area | Deal-Breaker | Consequence |
|------|-------------|-------------|
| **Box Model** | No `border-box` | Layout overflow, broken widths |
| **Units** | `px` for everything | Doesn't respect user font size |
| **Positioning** | `z-index: 9999` without stacking context | Modal trapped behind header |
| **Cascade** | `!important` wars | Unmaintainable CSS |
| **Specificity** | Deep nesting | Impossible to override |
| **Flexbox** | No `min-width: 0` | Horizontal overflow |
| **Grid** | `repeat(auto-fit, minmax(300px, 1fr))` without `min()` | Overflow on narrow screens |
| **Responsive** | Missing viewport meta | Tiny text on mobile |
| **Responsive** | No `width`/`height` on images | Cumulative Layout Shift |
| **Container Queries** | `container-type: size` without height | Queries fail |
| **Variables** | `var()` in media queries | Doesn't work |
| **Animations** | Animating `width`/`left` | Jank, dropped frames |
| **Animations** | No `prefers-reduced-motion` | Vestibular disorders |
| **Transitions** | `transition: all` | Unintended animations, layout thrash |
| **Architecture** | No naming convention | Unmaintainable, collisions |
| **Modern CSS** | No fallbacks for new features | Broken in older browsers |
| **Accessible UI** | `outline: none` | Keyboard users lost |
| **Accessible UI** | Hover-only interactions | Unusable on touch |
| **Accessible UI** | Low contrast placeholder | WCAG failure |

---

Next topic? Send **3. JavaScript** and I'll give the same complete treatment — every subtopic, syntax, real-world examples, tricks, and deal-breakers.
