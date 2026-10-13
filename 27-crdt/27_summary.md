# 27. CRDT (Conflict-free Replicated Data Types) - Complete Deep Dive

## 27.12 CRDT - Summary Deal-Breaker Checklist

| Area | Deal-Breaker | Consequence |
|------|-------------|-------------|
| **Fundamentals** | Confusing CRDTs with "no conflicts" | Convergence ≠ intended result |
| **Fundamentals** | CRDTs for server-authoritative data | Incorrect for financial/inventory data |
| **Fundamentals** | Ignoring metadata overhead | 10-100× larger than plain data |
| **State-Based** | Full state broadcast for large docs | Prohibitive bandwidth |
| **State-Based** | LWW-Register for collaborative text | Data loss |
| **Op-Based** | No reliable messaging layer | Permanent divergence |
| **Op-Based** | No causal delivery | Incorrect operation ordering |
| **Op-Based** | Non-commutative operations | Divergent outcomes |
| **Delta-State** | No delta compaction | Deltas accumulate indefinitely |
| **Delta-State** | No Merkle-DAG for sync | O(n) sync for large docs |
| **Pure Op-Based** | No snapshot compaction | Log grows forever |
| **Libraries** | Yjs for JSON-heavy apps | Automerge is better for JSON |
| **Libraries** | Automerge for text-heavy apps | Yjs is 3× faster for text |
| **Performance** | No snapshot compaction | Unbounded growth |
| **Performance** | No tombstone TTL | Deleted keys resurrect |
| **P2P** | No group membership | Breaks beyond 2-3 peers |
| **P2P** | No encryption | Data visible to all peers |
| **Collaborative Editing** | No interleaving prevention | Garbled text |
| **Collaborative Editing** | No undo/redo scoping | Undoing another user's changes |
| **Limitations** | No GC strategy | Tombstones accumulate |
| **Limitations** | GUI coupling bottleneck | CRDT fast, UI slow |
| **Limitations** | Assuming CRDT eliminates centralization | Most production systems still use a central server |
| **OT vs CRDT** | Choosing CRDT because it's "newer" | OT dominates production co-editors |
| **OT vs CRDT** | Assuming CRDT is always correct | Representative CRDT solutions have algorithmic flaws |

---

**The Big Rule:** CRDTs guarantee **convergence**, not **correctness of intent**. Use them for collaborative data where concurrent edits are expected - text, cursors, presence, shared maps. Do not use them for financial transactions, inventory counts, or anything requiring a single source of truth. Choose state-based for simplicity and reliability, operation-based for small messages (with reliable delivery), and delta-state for the best of both worlds. Always plan for garbage collection, tombstone TTL, and snapshot compaction. And remember: **CRDTs are difficult to design, prone to subtle bugs** - use a battle-tested library like Yjs, Automerge, or Loro rather than rolling your own.

*Educational use only - AI-assisted content. See [DISCLAIMER.md](../DISCLAIMER.md) and [LICENSE.md](../LICENSE.md).*
