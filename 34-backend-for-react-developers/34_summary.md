# 34. BACKEND FOR REACT DEVELOPERS - Complete Deep Dive

## 34.15 Summary: Backend for React Developers Deal-Breaker Checklist

| Area | Deal-Breaker | Consequence |
|------|-------------|-------------|
| **Node.js** | Blocking the event loop | All concurrent requests freeze |
| **Express** | No body size limit | 500MB JSON body DoS |
| **Express** | No rate limiting | Unlimited requests per second |
| **Express** | Error handler not last | Errors not caught |
| **Fastify** | No schema | Performance advantage lost |
| **NestJS** | ValidationPipe not global | Opt-in validation; easy to forget |
| **NestJS** | NestJS on Express | Inherits Express CVE surface |
| **REST** | No versioning | Breaking changes break clients |
| **REST** | No pagination | `GET /users` returns 100K records |
| **GraphQL** | No depth limiting | Malicious query crashes server |
| **GraphQL** | No DataLoader | N+1 problem |
| **tRPC** | No request batching | Missing GraphQL's batching benefit |
| **HTTP** | HTTP/1.1 with many requests | Head-of-line blocking |
| **Headers** | No CSP | XSS vulnerability |
| **Headers** | No HSTS | MITM downgrade |
| **Cookies** | No `HttpOnly` | XSS reads session tokens |
| **Cookies** | No `SameSite` | CSRF vulnerability |
| **CORS** | `*` with credentials | Browser rejects response |
| **CORS** | No preflight caching | OPTIONS request per cross-origin call |
| **Auth** | JWT in `localStorage` | XSS reads token |
| **Auth** | No refresh token rotation | Stolen refresh token valid forever |
| **Auth** | No password hashing | Plaintext passwords |
| **Authz** | Client-side-only auth | API unprotected |
| **Authz** | No ownership checks | Any user accesses any resource |
| **Rate Limiting** | No rate limiting | Brute-force succeeds |
| **Rate Limiting** | In-memory store | Limits reset on restart |

---

**The Big Rule:** For React developers in 2026, the backend is not optional knowledge. Choose **Express** for brownfield, **Fastify** for performance, **NestJS** for enterprise structure. Use **REST** for public APIs, **GraphQL** for complex client composition, **tRPC** for TypeScript monorepos. Validate every input. Rate-limit every endpoint. Hash every password with Argon2id. Store tokens in `HttpOnly` cookies, not `localStorage`. Use `SameSite=Lax` for CSRF protection. And always - always - validate on the server.

*Educational use only - AI-assisted content. See [DISCLAIMER.md](../DISCLAIMER.md) and [LICENSE.md](../LICENSE.md).*
