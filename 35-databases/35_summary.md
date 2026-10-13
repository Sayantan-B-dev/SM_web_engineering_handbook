# 35. DATABASES - Complete Deep Dive

## 35.11 Summary: Databases Deal-Breaker Checklist

| Area | Deal-Breaker | Consequence |
|------|-------------|-------------|
| **PostgreSQL** | No connection pooling | Connection limit hit at scale |
| **PostgreSQL** | No RLS for multi-tenant | Application-level auth bypassable |
| **PostgreSQL** | No JSONB index | Full table scan for JSON queries |
| **PostgreSQL** | Forgetting VACUUM | Bloat, performance degradation |
| **SQL** | String concatenation | SQL injection |
| **SQL** | OFFSET pagination for large datasets | Linear performance degradation |
| **SQL** | No EXPLAIN ANALYZE | Guessing at query performance |
| **Design** | `TIMESTAMP` instead of `TIMESTAMPTZ` | Timezone bugs |
| **Design** | Auto-increment for public IDs | Guessable, reveals count |
| **Design** | No `created_at`/`updated_at` | Can't debug when data changed |
| **Design** | Direct `organization_id` on `users` | Multi-tenant trap |
| **Design** | Hard deletes only | Referential integrity broken |
| **Indexes** | No index on foreign keys | JOINs do full table scans |
| **Indexes** | Wrong composite index column order | Index unusable |
| **Indexes** | Over-indexing | Write overhead on every INSERT |
| **Transactions** | Long-running transactions | Bloat, lock contention |
| **Transactions** | No deadlock handling | Application crashes |
| **Transactions** | Serializable everywhere | 10× throughput reduction |
| **Redis** | No TTL | Cache grows forever |
| **Redis** | No cache invalidation | Stale data served indefinitely |
| **Redis** | No connection pooling | Connection per request |
| **NoSQL** | NoSQL for ACID-critical data | Financial transactions break |
| **NoSQL** | SQL for extreme write throughput | Can't handle 1M+ writes/sec |
| **React Integration** | No client-side database | Every read is a network round-trip |
| **React Integration** | No React Query for server state | Manual fetch with no caching |
| **React Integration** | N+1 queries | Each component fetches its own data |
| **Connection Pooling** | No pooling | Connection limit hit at scale |
| **Connection Pooling** | Session mode instead of transaction mode | Fewer connections saved |
| **Migrations** | Single massive migration | Blocks all reads/writes for minutes |
| **Migrations** | No backfill strategy | `UPDATE` locks the table |
| **Migrations** | No rollback plan | Failed migration leaves inconsistent state |

---

**The Big Rule:** PostgreSQL is the default. Add Redis for caching. Add SQLite WASM for local-first. Use connection pooling from day one. Index for your query patterns, not for every column. Keep transactions short. Use UUIDv7 for distributed systems. Always use `TIMESTAMPTZ`. Start normalized, denormalize only when measured. And never - ever - concatenate strings into SQL.

*Educational use only - AI-assisted content. See [DISCLAIMER.md](../DISCLAIMER.md) and [LICENSE.md](../LICENSE.md).*
