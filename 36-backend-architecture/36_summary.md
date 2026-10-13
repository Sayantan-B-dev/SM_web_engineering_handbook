# 36. BACKEND ARCHITECTURE - Complete Deep Dive

## 36.10 Summary: Backend Architecture Deal-Breaker Checklist

| Area | Deal-Breaker | Consequence |
|------|-------------|-------------|
| **Fundamentals** | Microservices for 10-person team | DevOps tax without benefits |
| **Fundamentals** | Premature decomposition | Freezes wrong boundaries |
| **Monolith** | No internal boundaries | Big ball of mud |
| **Monolith** | One change forces full redeploy | Slow iteration |
| **Modular Monolith** | No enforcement | Boundaries decay within weeks |
| **Modular Monolith** | Modules reach into each other's tables | Distributed monolith |
| **Microservices** | No platform team | Every service reinvents CI, observability |
| **Microservices** | No service mesh | No mTLS, no workload identity |
| **Microservices** | Distributed monolith | Worst of both worlds |
| **Microservices** | No Saga | Distributed transactions impractical |
| **EDA** | No transactional outbox | Dual-writes fail silently 1-5% |
| **EDA** | No schema evolution | Hundred undocumented event shapes |
| **EDA** | No idempotency | Retried events create duplicates |
| **EDA** | No observability | Can't debug subtle failure modes |
| **Message Queues** | No DLQ | Poison messages block queue forever |
| **Message Queues** | No idempotency | At-least-once delivery means duplicates |
| **Message Queues** | Kafka for simple work queue | Overkill; SQS/RabbitMQ better |
| **Background Jobs** | Cron for complex workflows | Stateless, manual intervention |
| **Background Jobs** | No retry strategy | Transient failures = permanent loss |
| **Background Jobs** | BullMQ for multi-day workflows | Use Temporal for long-running state |
| **Distributed Systems** | No circuit breaker | One failure cascades to all |
| **Distributed Systems** | No bulkhead | One workload consumes all resources |
| **Distributed Systems** | No distributed tracing | Can't debug across boundaries |
| **Distributed Systems** | No leader election | Multiple writers corrupt data |
| **API Gateway** | No gateway | No central auth, rate limiting, routing |
| **Service Mesh** | Mesh for north-south traffic | Wrong tool; use API gateway |
| **Service Mesh** | No mTLS | Unencrypted service-to-service traffic |

---

**The Big Rule:** Default to a **modular monolith**. Extract microservices only when organizational signals demand it. Use **event-driven architecture** for async workloads, but always with transactional outbox, schema evolution, and idempotency. Use **SQS/RabbitMQ** for task queues, **Kafka** for event streaming. Use **BullMQ** for simple jobs, **Temporal** for long-running workflows. API gateway for north-south, service mesh for east-west. And always - **measure, don't guess**.
