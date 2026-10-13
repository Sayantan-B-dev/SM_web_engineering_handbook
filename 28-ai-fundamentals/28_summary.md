# 28. AI FUNDAMENTALS - Complete Deep Dive

## 28.12 AI Fundamentals - Summary Deal-Breaker Checklist

| Area | Deal-Breaker | Consequence |
|------|-------------|-------------|
| **LLMs** | Assuming deterministic output | LLMs are probabilistic; results vary |
| **LLMs** | Secrets in system prompt | Prompt injection extracts them |
| **LLMs** | Not streaming | Users stare at blank screen |
| **Tokens** | Assuming 1 token = 1 word | Underestimating cost by 25%+ |
| **Tokens** | Not counting tokens | Context overflow, failed requests |
| **Context Windows** | Assuming persistent memory | Every request is stateless |
| **Context Windows** | Filling the entire window | "Lost in the middle" - accuracy drops 30%+ |
| **Context Windows** | No compaction | Long sessions overflow |
| **Embeddings** | Exact match expectations | Embeddings capture semantics, not strings |
| **Embeddings** | No caching | Re-embedding wastes money |
| **Vector DB** | Over-engineering | pgvector is sufficient for millions of vectors |
| **Vector DB** | No metadata filtering | Irrelevant results from wrong category |
| **Vector Search** | Pure vector, no hybrid | Misses exact keyword matches |
| **Vector Search** | No reranking | Top-K results often not most relevant |
| **RAG** | No chunking strategy | Chunks too large (noise) or too small (missing context) |
| **RAG** | No evaluation | Don't know if retrieval is relevant |
| **RAG** | No reranking | Top-K vector results often irrelevant |
| **Tool Calling** | No argument validation | Model hallucinates arguments |
| **Tool Calling** | No tool error handling | Model doesn't know a tool failed |
| **Tool Calling** | Too many tools | Model gets confused (>15 tools) |
| **Structured Outputs** | No `strict: true` | Schema compliance not guaranteed |
| **Structured Outputs** | No retry logic | API errors happen |
| **Agents** | No max steps | Agent loops forever |
| **Agents** | No tool validation | Hallucinated tool names |
| **Agents** | No human-in-the-loop | Agent deletes production data |
| **Agents** | No observability | Can't debug agent decisions |
| **Agent Architecture** | No guardrails | Destructive actions without validation |
| **Agent Architecture** | No cost caps | Agent loop burns thousands in API fees |
| **Agent Architecture** | No evaluation | Don't know if agent is succeeding |

---

**The Big Rule:** LLMs are probabilistic text generators, not databases or reasoning engines. Tokens are the currency - count them, budget them, and compact them. Embeddings power semantic search - cache them, use hybrid search, and rerank. RAG grounds LLMs in your data - chunk carefully, evaluate rigorously, and always rerank. Tool calling enables actions - validate arguments, handle errors, and limit tool count. Agents are loops - cap steps, add guardrails, and observe everything. And always stream long responses.
