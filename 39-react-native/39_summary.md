# 39. REACT NATIVE - Complete Deep Dive

## 39.7 React Native - Summary Deal-Breaker Checklist

| Area | Deal-Breaker | Consequence |
|------|-------------|-------------|
| **Fundamentals** | Attempting to disable New Architecture | Build fails in 0.82+ |
| **Fundamentals** | Using JavaScriptCore | Hermes is the only supported engine |
| **Architecture** | Still on legacy bridge | 42% slower startup, 30% jankier UI |
| **Architecture** | Third-party libs without New Arch | Crashes or no-op native calls |
| **Architecture** | No Codegen spec files | TurboModule doesn't work |
| **Expo** | Using Expo Go for production | Push notifications and Maps unsupported |
| **Expo** | SDK 54 → 55 without migration | Legacy Architecture removed; build fails |
| **Expo** | Using `expo-av` | Deprecated; use `expo-audio`/`expo-video` |
| **Navigation** | Importing `@react-navigation/*` in SDK 56+ | Breaking change; use codemod |
| **Navigation** | Not using typed routes | Runtime errors from navigation typos |
| **Performance** | No `getItemLayout` | FlatList measures every item height |
| **Performance** | Unstable `keyExtractor` | Reconciliation churn on every data change |
| **Performance** | Heavy sync JS on main thread | Dropped frames even if GPU is idle |
| **Performance** | FlatList for large lists | FlashList gives 10× throughput |
| **Native Modules** | Spec file without `Native` prefix | Codegen ignores it |
| **Native Modules** | No Codegen config | Scaffolding never generated |
| **Native Modules** | Platform-specific native code | Duplicated logic across iOS/Android |
| **Platform-Specific** | `Platform.OS` for large components | Inline conditionals become unreadable |
| **Platform-Specific** | No `.native.js` bundler config | Unused code in web bundles |
| **Platform-Specific** | Assuming `Platform.Version` is OS version | On Android it's the API version |

---

**The Big Rule:** React Native in 2026 is **New Architecture or nothing**. The legacy bridge is gone. Hermes V1 is the only engine. TurboModules load lazily. Fabric renders concurrently. Use **FlashList with `getItemLayout`** for lists. Use **Worklets** for heavy computation. Use **Expo Router** for file-based routing (SDK 56+). Validate dependencies with `npx expo-doctor`. Split platform-specific code into `.ios.tsx` / `.android.tsx` files. And never - ever - try to disable the New Architecture.
