# 21. OBSERVABILITY - Complete Deep Dive

## Summary: Observability Deal-Breaker Checklist

| Area | Deal-Breaker | Consequence |
|------|-------------|-------------|
| **Fundamentals** | Monitoring ≠ observability | Can't investigate root cause |
| **Fundamentals** | No SLOs | No basis for alerting or release gates |
| **Logging** | No structured logs | Zero context in production |
| **Logging** | Logging PII | Legal and security exposure |
| **Logging** | No sampling | Log volume explodes |
| **Metrics** | Unbounded labels | Cardinality explodes; cost surges |
| **Metrics** | No percentiles | Averages hide tail latency |
| **Tracing** | No `propagateTraceHeaderCorsUrls` | Browser and backend traces disconnected |
| **Tracing** | No sampling | Tracing cost balloons |
| **Errors** | No sourcemap upload | Stack traces minified and useless |
| **Errors** | No release tracking | Can't correlate errors with deploys |
| **Errors** | No error boundary | React errors silently lost |
| **Errors** | Prioritize by volume | Miss the conversion killer |
| **Performance** | Lighthouse only | Lab data ≠ field data |
| **Performance** | No performance budgets | Bundle grows silently |
| **Performance** | Ignoring INP | Fast page, slow input, feels broken |
| **User Monitoring** | No user action tracking | Know it's fast, not if it works |
| **User Monitoring** | No session replay | Debugging is guesswork |
| **User Monitoring** | No segmentation | Miss browser/region-specific bugs |
| **Frontend Telemetry** | No PII filtering | GDPR violation, fines |
| **Frontend Telemetry** | No batching | Battery drain, network cost |
| **Frontend Telemetry** | No consent gating | Legal exposure |
| **Grafana** | Too many dashboards | Nobody looks at them |
| **Grafana** | No alerting routing | Alerts muted |
| **Faro** | No `beforeSend` PII filter | User emails/tokens in Grafana Cloud |
| **Faro** | No `app.version` | Can't filter errors by deploy |
| **Faro** | No `paused` on localhost | Dev errors pollute production |
| **OpenTelemetry** | No context propagation | Traces break at boundaries |
| **OpenTelemetry** | No semantic conventions | Inconsistent attributes |
| **Alloy** | No PII scrubbing at collector | Sensitive data leaves network |
| **Alloy** | No batching | Network per event; cost explodes |
| **Sentry** | 100% tracing | Huge bill |
| **Sentry** | No ownership rules | Errors go to no one |

---

**The Big Rule:** Observability is not just monitoring. Logs, metrics, traces, and user actions must connect end-to-end. Always propagate trace context browser → backend. Always filter PII. Always tag releases. Prioritize by user impact, not error volume. And never let observability break the product.

*Educational use only - AI-assisted content. See [DISCLAIMER.md](../DISCLAIMER.md) and [LICENSE.md](../LICENSE.md).*
