# 5. REACT FUNDAMENTALS - Complete Deep Dive

## Summary: React Fundamentals Deal-Breaker Checklist

| Area | Deal-Breaker | Consequence |
|------|-------------|-------------|
| **JSX** | `onClick={handleClick()}` | Fires during render |
| **JSX** | `dangerouslySetInnerHTML` unsanitized | XSS vulnerability |
| **JSX** | `class` instead of `className` | No styling applied |
| **Components** | Nested component definitions | State reset every render |
| **Components** | Lowercase component names | Renders as DOM tag |
| **Props** | Mutating props | Breaks data flow |
| **Props** | `prop="false"` (string) | Truthy - always enabled |
| **State** | Reading state after setState | Stale value |
| **State** | Multiple `setCount(count+1)` | Only +1, not +2 |
| **State** | Derived data in state | Sync bugs |
| **Events** | `onClick={fn()}` | Runs immediately |
| **Events** | Missing `preventDefault` | Page reload, state lost |
| **Conditional** | `{count && ...}` with count=0 | Renders "0" |
| **Lists** | Index as key | Wrong state on reorder |
| **Keys** | `key={Math.random()}` | Full remount every render |
| **Keys** | Accessing `props.key` | `undefined` - not a prop |
| **Forms** | Controlled `file` input | Runtime error |
| **Forms** | `value` without `onChange` | Read-only warning |
| **Forms** | `e.target.value` on checkbox | Returns "on" |
| **Controlled** | No debounce on validation | Hundreds of requests |
| **Uncontrolled** | Setting `value` on uncontrolled input | Warning, confusion |
| **Composition** | HOC nesting ("wrapper hell") | Hard to debug |
| **Children** | Assuming `children` is a single element | Breaks with arrays |
| **Design** | God component (500+ lines) | Unmaintainable |
| **Design** | Boolean prop explosion | 128 combinations |
