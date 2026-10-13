# 29. AI + REACT - Complete Deep Dive

## 29.11 AI + React - Summary Deal-Breaker Checklist

| Area | Deal-Breaker | Consequence |
|------|-------------|-------------|
| **Stack** | Building chat UI from scratch | Weeks of work; use assistant-ui or AI Elements |
| **Stack** | No streaming layer | Users wait 5-30 seconds for a response |
| **Chat Interfaces** | Rendering raw Markdown during streaming | Broken HTML from incomplete tokens |
| **Chat Interfaces** | No scroll management | Chat doesn't auto-scroll or fights the user |
| **Chat Interfaces** | No message branching | Users can't edit and explore alternatives |
| **Streaming** | No SSE framing stripped | Client sees `data: {...}` instead of JSON |
| **Streaming** | No error handling | Mid-stream error leaves UI broken |
| **State** | Chat state in Redux | Rebuilding `useChat` poorly |
| **State** | Prop drilling chat state | `messages`, `status`, `toolCalls` through 5 levels |
| **State** | Mixing chat state with app state | Clearing chat clears the app |
| **Copilots** | No context awareness | Copilot suggests actions that don't apply |
| **Copilots** | No approval flow | Copilot deletes production data |
| **AI Search** | Pure vector search | Misses exact matches |
| **AI Search** | No reranking | Top-K results often not most relevant |
| **RAG** | No source citations | Users can't verify answers |
| **RAG** | No streaming | RAG responses are long; streaming is essential |
| **RAG** | No chunking strategy | Chunks too large (noise) or too small (missing context) |
| **Agents** | No reasoning display | Users can't see why the agent decided |
| **Agents** | No max steps | Agent loops forever |
| **Agents** | Too many tools | Agent gets confused (>15 tools) |
| **Agent Interfaces** | Raw JSON output | Users can't read tool results |
| **Agent Interfaces** | No approval flow | Destructive tools execute without confirmation |
| **Tool-Use** | No Zod validation | Runtime errors from bad argument shapes |
| **Tool-Use** | No tool state machine | UI doesn't show loading/success/error |
| **Tool-Use** | Client-side execution of server tools | Security vulnerability |
| **Generative UI** | `dangerouslySetInnerHTML` for LLM output | XSS vulnerability |
| **Generative UI** | No Zod validation at stream boundary | Malformed JSON crashes renderer |
| **Generative UI** | No layout shift prevention | Content reflows as it streams in |
| **Generative UI** | Proprietary lock-in | Tied to a vendor; works with raw SSE + Zod + RSC |

---

**The Big Rule:** The 2026 AI+React stack is **Vercel AI SDK + Zustand (or ai-sdk-zustand) + shadcn/ui (or assistant-ui)**. Stream everything. Harden incomplete Markdown during streaming. Render tool calls as typed UI cards, not raw JSON. Validate every tool argument with Zod. Require approval for destructive tools. Use generative UI (streaming JSON → Zod → component registry → React tree) instead of `dangerouslySetInnerHTML`. And always keep the model loop client-side when possible (Prompt API with cloud fallback).

*Educational use only - AI-assisted content. See [DISCLAIMER.md](../DISCLAIMER.md) and [LICENSE.md](../LICENSE.md).*
