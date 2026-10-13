# 20. PRODUCTION ENGINEERING - Complete Deep Dive

## 20.21 Production Engineering - Summary Deal-Breaker Checklist

| Area | Deal-Breaker | Consequence |
|------|-------------|-------------|
| **Fundamentals** | Deploy = release | Nobody ships on Fridays |
| **Build Systems** | CommonJS deps | No tree shaking; entire module ships |
| **Build Systems** | No `sideEffects: false` | Bundler conservatively includes everything |
| **Env Variables** | `NEXT_PUBLIC_` on a secret | Secret embedded in JS bundle |
| **Env Variables** | No env validation | Missing env crashes at runtime |
| **Secrets** | Plaintext `.env` on disk | AI assistants can read it |
| **Secrets** | No rotation | Leaked key valid forever |
| **CI/CD** | No path filtering | README change triggers 30-min build |
| **CI/CD** | No dependency caching | `npm install` from scratch every time |
| **GitHub Actions** | No concurrency group | Redundant pipelines on every push |
| **GitHub Actions** | Long-lived AWS credentials | Use OIDC instead |
| **Preview Deployments** | Preview uses prod DB | PR migration wipes production |
| **Release Strategies** | All-or-nothing deploys | One bad deploy takes down 100% |
| **Release Strategies** | Feature flags never cleaned | Code unreadable |
| **Rollbacks** | No rollback plan | 30-60 min manual recovery |
| **Rollbacks** | Destructive migrations | Rollback impossible |
| **Docker** | No multi-stage build | 1GB image with dev dependencies |
| **Docker** | `COPY . .` before `npm ci` | Cache invalidated on every code change |
| **Docker** | Running as root | Security vulnerability |
| **CDN** | Caching HTML too long | Stale HTML points to deleted assets |
| **CDN** | Deleting old assets immediately | Stale HTML 404s |
| **HTTPS** | No HSTS | MITM downgrade possible |
| **Reverse Proxies** | Still using ingress-nginx | Retired March 2026 |
| **Vercel** | Heavy ISR usage | Vendor lock-in |
| **Cloudflare** | Workers runtime limitations | No Node.js APIs |
| **AWS** | S3 bucket public | Anyone can list and download files |
| **Observability** | No user action tracking | You know it's fast, not if it works |
| **Observability** | No session replay | Debugging user issues is guesswork |
| **Observability** | Error prioritization by volume | Fix frequent errors, not impactful ones |
| **Grafana Faro** | No `beforeSend` PII filter | User emails/tokens logged to observability |
| **Grafana Faro** | No `app.version` | Can't filter errors by deploy |
| **Grafana Faro** | No sourcemap upload | Stack traces minified and useless |

---

**The Big Rule:** Decouple deploy from release. Use content-hashed assets with immutable cache headers. Never put secrets in frontend code - use a BFF. Preview every PR. Roll back in seconds, not hours. Monitor users, not just servers. Design for failure from day one.

*Educational use only - AI-assisted content. See [DISCLAIMER.md](../DISCLAIMER.md) and [LICENSE.md](../LICENSE.md).*
