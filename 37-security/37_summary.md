# 37. SECURITY - Complete Deep Dive

## 37.10 Summary: Security Deal-Breaker Checklist

| Area | Deal-Breaker | Consequence |
|------|-------------|-------------|
| **XSS** | `dangerouslySetInnerHTML` without DOMPurify | Instant XSS |
| **XSS** | No URL scheme validation | `javascript:` URLs execute |
| **XSS** | No CSP | Injected script runs |
| **CSRF** | No SameSite attribute | CSRF via cross-site requests |
| **CSRF** | State-changing GET requests | SameSite=Lax bypass (CVE-2026-71378) |
| **CSRF** | Relying only on SameSite | Incomplete defense |
| **CSP** | `unsafe-inline` in `script-src` | Defeats entire policy |
| **CSP** | `unsafe-eval` | Allows eval-based XSS |
| **CSP** | Static/reused nonces | Worthless nonce |
| **CSP** | No `object-src 'none'` | Plugin injection vectors open |
| **CSP** | Enforcing without report-only | Breaks production |
| **OAuth** | Implicit flow | Removed in OAuth 2.1 |
| **OAuth** | No PKCE | Mandatory in OAuth 2.1 |
| **OAuth** | Wildcard redirect URIs | Authorization server must reject |
| **OAuth** | Tokens in localStorage | XSS exfiltrates instantly |
| **OAuth** | No `state` validation | CSRF on callback |
| **JWT** | `algorithms: ['none']` | Unsigned tokens accepted |
| **JWT** | No algorithm pinning | Algorithm confusion attack |
| **JWT** | HS256 with shared secrets | Use RS256/ES256 |
| **JWT** | No `exp`/`iss`/`aud` validation | Token reuse across services |
| **Headers** | No HSTS | MITM downgrade |
| **Headers** | No `X-Content-Type-Options` | MIME sniffing |
| **Headers** | No COOP/COEP | No cross-origin isolation |
| **Cookies** | No `HttpOnly` | XSS reads session token |
| **Cookies** | No `Secure` | Token sent over HTTP |
| **Cookies** | No `SameSite` | CSRF vulnerability |
| **Clickjacking** | No `X-Frame-Options` | Site embedded in invisible iframe |
| **Session** | No session ID regeneration on login | Session fixation |
| **Session** | No session expiry | Sessions live forever |

---

**The Big Rule:** Security is **defense in depth**. No single control is sufficient. React escapes JSX - but `dangerouslySetInnerHTML`, URL attributes, and DOM refs are still yours to handle. CSP is your safety net for the XSS that slips past code review. SameSite cookies are your primary CSRF defense - but state-changing GETs still bypass them. OAuth 2.1 makes PKCE mandatory and removes implicit flow. JWTs need algorithm pinning and 15-minute expiry. Tokens belong in `HttpOnly`, `Secure`, `SameSite` cookies - preferably behind a BFF. And every response needs security headers. Trust nothing. Validate everything.

*Educational use only - AI-assisted content. See [DISCLAIMER.md](../DISCLAIMER.md) and [LICENSE.md](../LICENSE.md).*
