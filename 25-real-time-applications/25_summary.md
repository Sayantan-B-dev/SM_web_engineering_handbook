# 25. REAL-TIME APPLICATIONS - Complete Deep Dive

## 25.10 Real-Time Applications - Summary Deal-Breaker Checklist

| Area | Deal-Breaker | Consequence |
|------|-------------|-------------|
| **Fundamentals** | WebSocket for server-to-client only | SSE is simpler, HTTP-native |
| **Fundamentals** | No fallback for blocked transports | Some networks block UDP/WebSocket |
| **WebSockets** | No heartbeat | Proxies kill idle connections after 60-120s |
| **WebSockets** | No reconnection | Connections drop constantly in production |
| **WebSockets** | Unbounded send buffer | Memory exhaustion on slow clients |
| **SSE** | No `X-Accel-Buffering: no` | Nginx buffers; events never stream |
| **SSE** | No keep-alive | 4-minute idle timeout kills the connection |
| **SSE** | No `Last-Event-ID` | Client misses messages during reconnect |
| **WebRTC** | No TURN server | 10-20% of connections fail behind symmetric NAT |
| **WebRTC** | Unreliable channel for critical data | Chat messages silently dropped |
| **Presence** | High-frequency updates via Presence | Floods the channel; use Broadcast |
| **Presence** | No TTL | Disconnected clients stay "online" forever |
| **Presence** | No multi-device reconciliation | One user appears as 3 users |
| **Reconnection** | No jitter | Thundering herd keeps server down |
| **Reconnection** | No sequence numbers | Client can't request missed data |
| **Reconnection** | No buffering strategy | Gap too large to replay |
| **Heartbeats** | Heartbeat interval > idle timeout | Proxy kills connection first |
| **Heartbeats** | No pong timeout | Dead server never detected |
| **Backpressure** | No `maxBackpressure` | Slow client exhausts server memory |
| **Backpressure** | Drop newest instead of oldest | Stale messages delivered, fresh ones dropped |
| **Synchronization** | Timestamps for ordering | Clock skew causes out-of-order application |
| **Synchronization** | No idempotency keys | Retried messages applied twice |
| **Synchronization** | No gap detection | Out-of-order messages applied incorrectly |
| **Collaboration** | No CRDT/OT | User changes silently overwritten |
| **Collaboration** | No room isolation | Messages leak between rooms |

---

**The Big Rule:** Start with SSE for server-to-client. Use WebSocket for bidirectional. Use WebRTC only for P2P. Always implement exponential backoff **with jitter** (500ms base, 30s cap, ±20% jitter). Always send heartbeats every 30s. Always assign sequence numbers for replay. Always enforce `maxBackpressure`. And always keep the main thread as the authoritative state holder.
