# Web Engineering Notes (React Based)

A structured, React-centred web engineering knowledge base. It runs from web
foundations (HTML, CSS, JavaScript, TypeScript) through React, Next.js, backend,
production engineering, and AI-assisted frontend topics, ending in a master
project. There are 49 numbered modules in total.

## Introduction

Each module lives in its own numbered folder (for example
`01-web-foundations`, `02-css`). A module has one deep-dive source file,
`core.md`, which is split verbatim into one note per topic plus a summary file.
`core.md` is the local source of truth and is intentionally gitignored; the
per-topic files and the summary are what get committed.

Modules `01` through `04` are complete. Modules `05` through `49` have their
topic file structure in place and are filled in as their `core.md` deep dives
land.

## Goal

Build one complete, consistent, interview- and production-ready reference for
modern React-based web engineering, from fundamentals to advanced frontier
topics.

## Objectives

- Cover every topic in depth: subtopics, syntax, real-world examples, tricks,
  and deal-breakers.
- Keep one topic per file so notes stay navigable and reviewable.
- Never lose content when splitting: topic files mirror `core.md` exactly, with
  no summarising, rewording, or reduction.
- Keep history clean with one commit per module folder.
- Finish all 49 modules plus the master project in `49-master-project`.

## How to Use

1. Follow the numbered order, starting at `01-web-foundations`.
2. Inside a module, read the `*_summary.md` first for the deal-breaker
   checklist, then go topic by topic (`01.01`, `01.02`, and so on).
3. Code blocks, tables, and checklists in the topic files are the full content
   from that module's `core.md` deep dive.

## Conventions

- `core.md` is gitignored and never committed. It stays intact as the source.
- Each `## X.Y` section of `core.md` maps to exactly one topic file.
- The module title, `## Summary` section, and trailing pointer line map to the
  `*_summary.md` file.
- One commit per folder; `AGENT.md` changes get their own commit.
- Commit messages are plain, with no AI tags and no emoji.
- See `AGENT.md` for the full contributor rules.

## Progress

- Complete: `01-web-foundations`, `02-css`, `03-javascript`, `04-typescript`.
- Pending core content: `05` through `49` (structure ready, placeholder notes).

## Syllabus
```txt
web-engineering-handbook/
├── README.md
│
├── 01-web-foundations/
│   ├── 01.01-html.md
│   ├── 01.02-semantic-html.md
│   ├── 01.03-forms.md
│   ├── 01.04-accessibility.md
│   ├── 01.05-aria.md
│   ├── 01.06-seo.md
│   ├── 01.07-dom.md
│   └── 01.08-browser-rendering-pipeline.md
│
├── 02-css/
│   ├── 02.01-css-fundamentals.md
│   ├── 02.02-cascade.md
│   ├── 02.03-specificity.md
│   ├── 02.04-flexbox.md
│   ├── 02.05-grid.md
│   ├── 02.06-responsive-design.md
│   ├── 02.07-container-queries.md
│   ├── 02.08-css-variables.md
│   ├── 02.09-animations.md
│   ├── 02.10-transitions.md
│   ├── 02.11-css-architecture.md
│   ├── 02.12-modern-css.md
│   └── 02.13-accessible-ui.md
│
├── 03-javascript/
│   ├── 03.01-variables.md
│   ├── 03.02-scope.md
│   ├── 03.03-closures.md
│   ├── 03.04-this.md
│   ├── 03.05-prototypes.md
│   ├── 03.06-objects.md
│   ├── 03.07-arrays.md
│   ├── 03.08-destructuring.md
│   ├── 03.09-spread-rest.md
│   ├── 03.10-modules.md
│   ├── 03.11-higher-order-functions.md
│   ├── 03.12-callbacks.md
│   ├── 03.13-promises.md
│   ├── 03.14-async-await.md
│   ├── 03.15-event-loop.md
│   ├── 03.16-microtasks.md
│   ├── 03.17-macrotasks.md
│   ├── 03.18-fetch.md
│   ├── 03.19-abortcontroller.md
│   ├── 03.20-web-apis.md
│   ├── 03.21-dom-events.md
│   ├── 03.22-event-delegation.md
│   ├── 03.23-iterators.md
│   ├── 03.24-generators.md
│   ├── 03.25-error-handling.md
│   ├── 03.26-memory-management.md
│   ├── 03.27-garbage-collection.md
│   └── 03.28-javascript-execution-model.md
│
├── 04-typescript/
│   ├── 04.01-types.md
│   ├── 04.02-interfaces.md
│   ├── 04.03-type-aliases.md
│   ├── 04.04-generics.md
│   ├── 04.05-unions.md
│   ├── 04.06-intersections.md
│   ├── 04.07-utility-types.md
│   ├── 04.08-type-narrowing.md
│   ├── 04.09-discriminated-unions.md
│   ├── 04.10-unknown-vs-any.md
│   ├── 04.11-function-typing.md
│   ├── 04.12-mapped-types.md
│   ├── 04.13-conditional-types.md
│   ├── 04.14-advanced-generics.md
│   └── 04.15-type-safe-apis.md
│
├── 05-react-fundamentals/
│   ├── 05.01-jsx.md
│   ├── 05.02-components.md
│   ├── 05.03-props.md
│   ├── 05.04-state.md
│   ├── 05.05-events.md
│   ├── 05.06-conditional-rendering.md
│   ├── 05.07-lists.md
│   ├── 05.08-keys.md
│   ├── 05.09-forms.md
│   ├── 05.10-controlled-components.md
│   ├── 05.11-uncontrolled-components.md
│   ├── 05.12-composition.md
│   ├── 05.13-children.md
│   └── 05.14-component-design.md
│
├── 06-react-hooks/
│   ├── 06.01-usestate.md
│   ├── 06.02-useeffect.md
│   ├── 06.03-useref.md
│   ├── 06.04-usememo.md
│   ├── 06.05-usecallback.md
│   ├── 06.06-usereducer.md
│   ├── 06.07-usecontext.md
│   └── 06.08-custom-hooks.md
│
├── 07-react-mental-models/
│   ├── 07.01-rendering.md
│   ├── 07.02-re-rendering.md
│   ├── 07.03-render-phase.md
│   ├── 07.04-commit-phase.md
│   ├── 07.05-reconciliation.md
│   ├── 07.06-component-identity.md
│   ├── 07.07-referential-equality.md
│   ├── 07.08-batching.md
│   ├── 07.09-stale-closures.md
│   ├── 07.10-effects-vs-events.md
│   ├── 07.11-derived-state.md
│   ├── 07.12-state-ownership.md
│   └── 07.13-composition.md
│
├── 08-react-internals/
│   ├── 08.01-virtual-dom.md
│   ├── 08.02-fiber.md
│   ├── 08.03-reconciliation.md
│   ├── 08.04-scheduling.md
│   ├── 08.05-concurrent-rendering.md
│   ├── 08.06-lanes.md
│   ├── 08.07-suspense.md
│   ├── 08.08-transitions.md
│   ├── 08.09-streaming.md
│   ├── 08.10-hydration.md
│   ├── 08.11-selective-hydration.md
│   └── 08.12-react-scheduling.md
│
├── 09-react-compiler/
│   ├── 09.01-react-compiler.md
│   ├── 09.02-automatic-memoization.md
│   ├── 09.03-compiler-transformations.md
│   ├── 09.04-use-memo-directive.md
│   ├── 09.05-use-no-memo-directive.md
│   ├── 09.06-compiler-configuration.md
│   ├── 09.07-compiler-limitations.md
│   ├── 09.08-manual-memoization.md
│   └── 09.09-compiler-performance.md
│
├── 10-react-performance/
│   ├── 10.01-react-profiler.md
│   ├── 10.02-react-devtools.md
│   ├── 10.03-render-profiling.md
│   ├── 10.04-memoization.md
│   ├── 10.05-component-splitting.md
│   ├── 10.06-lazy-loading.md
│   ├── 10.07-code-splitting.md
│   ├── 10.08-dynamic-imports.md
│   ├── 10.09-bundle-analysis.md
│   ├── 10.10-tree-shaking.md
│   ├── 10.11-network-performance.md
│   ├── 10.12-image-optimization.md
│   ├── 10.13-font-optimization.md
│   ├── 10.14-cpu-bottlenecks.md
│   ├── 10.15-network-bottlenecks.md
│   └── 10.16-core-web-vitals.md
│
├── 11-modern-react/
│   ├── 11.01-react-server-components.md
│   ├── 11.02-server-components.md
│   ├── 11.03-client-components.md
│   ├── 11.04-server-boundaries.md
│   ├── 11.05-client-boundaries.md
│   ├── 11.06-use-client.md
│   ├── 11.07-use-server.md
│   ├── 11.08-serialization.md
│   ├── 11.09-server-actions.md
│   ├── 11.10-streaming.md
│   ├── 11.11-suspense.md
│   └── 11.12-hydration.md
│
├── 12-nextjs/
│   ├── 12.01-nextjs-fundamentals.md
│   ├── 12.02-app-router.md
│   ├── 12.03-routing.md
│   ├── 12.04-nested-layouts.md
│   ├── 12.05-pages.md
│   ├── 12.06-loading-ui.md
│   ├── 12.07-error-ui.md
│   ├── 12.08-route-groups.md
│   ├── 12.09-dynamic-routes.md
│   ├── 12.10-parallel-routes.md
│   ├── 12.11-intercepting-routes.md
│   ├── 12.12-server-components.md
│   ├── 12.13-client-components.md
│   ├── 12.14-server-actions.md
│   ├── 12.15-middleware-proxy.md
│   ├── 12.16-streaming.md
│   ├── 12.17-rendering-strategies.md
│   ├── 12.18-static-rendering.md
│   ├── 12.19-dynamic-rendering.md
│   ├── 12.20-data-fetching.md
│   ├── 12.21-caching.md
│   ├── 12.22-revalidation.md
│   ├── 12.23-request-memoization.md
│   ├── 12.24-cache-invalidation.md
│   ├── 12.25-nextjs-performance.md
│   └── 12.26-deployment.md
│
├── 13-state-management/
│   ├── 13.01-local-state.md
│   ├── 13.02-derived-state.md
│   ├── 13.03-global-state.md
│   ├── 13.04-server-state.md
│   ├── 13.05-url-state.md
│   ├── 13.06-form-state.md
│   ├── 13.07-cache-state.md
│   ├── 13.08-context.md
│   ├── 13.09-redux.md
│   ├── 13.10-redux-toolkit.md
│   ├── 13.11-zustand.md
│   ├── 13.12-jotai.md
│   └── 13.13-swr.md
│
├── 14-tanstack/
│   ├── 14.01-tanstack-query.md
│   ├── 14.02-queries.md
│   ├── 14.03-mutations.md
│   ├── 14.04-query-keys.md
│   ├── 14.05-query-cache.md
│   ├── 14.06-stale-time.md
│   ├── 14.07-garbage-collection.md
│   ├── 14.08-optimistic-updates.md
│   ├── 14.09-cache-invalidation.md
│   ├── 14.10-pagination.md
│   ├── 14.11-infinite-queries.md
│   ├── 14.12-prefetching.md
│   ├── 14.13-tanstack-router.md
│   └── 14.14-tanstack-start.md
│
├── 15-routing/
│   ├── 15.01-react-router.md
│   ├── 15.02-react-router-v7.md
│   ├── 15.03-nested-routing.md
│   ├── 15.04-data-routers.md
│   ├── 15.05-loaders.md
│   ├── 15.06-actions.md
│   ├── 15.07-route-boundaries.md
│   └── 15.08-tanstack-router.md
│
├── 16-frontend-architecture/
│   ├── 16.01-component-architecture.md
│   ├── 16.02-feature-based-architecture.md
│   ├── 16.03-modular-frontend.md
│   ├── 16.04-modular-monolith.md
│   ├── 16.05-component-libraries.md
│   ├── 16.06-design-systems.md
│   ├── 16.07-shared-packages.md
│   ├── 16.08-monorepos.md
│   ├── 16.09-micro-frontends.md
│   ├── 16.10-module-federation.md
│   ├── 16.11-dependency-boundaries.md
│   ├── 16.12-api-abstraction.md
│   ├── 16.13-domain-driven-frontend.md
│   ├── 16.14-frontend-scalability.md
│   └── 16.15-multi-team-architecture.md
│
├── 17-ui-design-systems/
│   ├── 17.01-design-systems.md
│   ├── 17.02-component-libraries.md
│   ├── 17.03-design-tokens.md
│   ├── 17.04-accessibility.md
│   ├── 17.05-headless-ui.md
│   ├── 17.06-radix.md
│   ├── 17.07-shadcn-ui.md
│   ├── 17.08-tailwind-css.md
│   ├── 17.09-css-modules.md
│   └── 17.10-css-in-js.md
│
├── 18-forms-validation/
│   ├── 18.01-react-hook-form.md
│   ├── 18.02-form-state.md
│   ├── 18.03-form-validation.md
│   ├── 18.04-zod.md
│   ├── 18.05-schema-validation.md
│   └── 18.06-type-safe-forms.md
│
├── 19-testing/
│   ├── 19.01-unit-testing.md
│   ├── 19.02-integration-testing.md
│   ├── 19.03-component-testing.md
│   ├── 19.04-end-to-end-testing.md
│   ├── 19.05-jest.md
│   ├── 19.06-vitest.md
│   ├── 19.07-react-testing-library.md
│   ├── 19.08-playwright.md
│   ├── 19.09-mocking.md
│   └── 19.10-contract-testing.md
│
├── 20-production-engineering/
│   ├── 20.01-build-systems.md
│   ├── 20.02-environment-variables.md
│   ├── 20.03-secrets.md
│   ├── 20.04-ci-cd.md
│   ├── 20.05-github-actions.md
│   ├── 20.06-preview-deployments.md
│   ├── 20.07-release-strategies.md
│   ├── 20.08-rollbacks.md
│   ├── 20.09-docker.md
│   ├── 20.10-cdn.md
│   ├── 20.11-https.md
│   ├── 20.12-reverse-proxies.md
│   ├── 20.13-vercel.md
│   ├── 20.14-cloudflare.md
│   └── 20.15-aws-fundamentals.md
│
├── 21-observability/
│   ├── 21.01-logging.md
│   ├── 21.02-metrics.md
│   ├── 21.03-tracing.md
│   ├── 21.04-error-monitoring.md
│   ├── 21.05-performance-monitoring.md
│   ├── 21.06-user-monitoring.md
│   ├── 21.07-frontend-telemetry.md
│   ├── 21.08-grafana.md
│   ├── 21.09-grafana-faro.md
│   ├── 21.10-opentelemetry.md
│   ├── 21.11-alloy-collector.md
│   └── 21.12-sentry.md
│
├── 22-browser-engineering/
│   ├── 22.01-web-apis.md
│   ├── 22.02-web-workers.md
│   ├── 22.03-shared-workers.md
│   ├── 22.04-service-workers.md
│   ├── 22.05-indexeddb.md
│   ├── 22.06-cache-api.md
│   ├── 22.07-broadcastchannel.md
│   ├── 22.08-websockets.md
│   ├── 22.09-webrtc.md
│   ├── 22.10-web-streams.md
│   ├── 22.11-notifications-api.md
│   ├── 22.12-permissions-api.md
│   └── 22.13-file-apis.md
│
├── 23-web-workers/
│   ├── 23.01-worker-lifecycle.md
│   ├── 23.02-message-passing.md
│   ├── 23.03-cpu-heavy-workloads.md
│   ├── 23.04-off-main-thread-computation.md
│   ├── 23.05-shared-memory.md
│   └── 23.06-worker-architecture.md
│
├── 24-webassembly/
│   ├── 24.01-wasm-fundamentals.md
│   ├── 24.02-javascript-wasm.md
│   ├── 24.03-wasm-performance.md
│   ├── 24.04-wasm-use-cases.md
│   ├── 24.05-browser-computation.md
│   └── 24.06-compute-intensive-applications.md
│
├── 25-real-time-applications/
│   ├── 25.01-websockets.md
│   ├── 25.02-server-sent-events.md
│   ├── 25.03-webrtc.md
│   ├── 25.04-presence.md
│   ├── 25.05-reconnection.md
│   ├── 25.06-heartbeats.md
│   ├── 25.07-backpressure.md
│   └── 25.08-real-time-synchronization.md
│
├── 26-offline-first-local-first/
│   ├── 26.01-offline-first-architecture.md
│   ├── 26.02-local-first-architecture.md
│   ├── 26.03-indexeddb.md
│   ├── 26.04-service-workers.md
│   ├── 26.05-local-storage.md
│   ├── 26.06-optimistic-updates.md
│   ├── 26.07-synchronization.md
│   ├── 26.08-conflict-resolution.md
│   └── 26.09-offline-caching.md
│
├── 27-crdt/
│   ├── 27.01-crdt-fundamentals.md
│   ├── 27.02-conflict-resolution.md
│   ├── 27.03-collaborative-editing.md
│   ├── 27.04-operational-transformation.md
│   ├── 27.05-crdt-vs-ot.md
│   ├── 27.06-peer-to-peer-synchronization.md
│   └── 27.07-distributed-state.md
│
├── 28-ai-fundamentals/
│   ├── 28.01-llms.md
│   ├── 28.02-tokens.md
│   ├── 28.03-context-windows.md
│   ├── 28.04-embeddings.md
│   ├── 28.05-vector-databases.md
│   ├── 28.06-vector-search.md
│   ├── 28.07-rag.md
│   ├── 28.08-tool-calling.md
│   ├── 28.09-function-calling.md
│   ├── 28.10-structured-outputs.md
│   ├── 28.11-agents.md
│   └── 28.12-agent-architecture.md
│
├── 29-ai-plus-react/
│   ├── 29.01-ai-chat-interfaces.md
│   ├── 29.02-streaming-ai-responses.md
│   ├── 29.03-ai-state-management.md
│   ├── 29.04-ai-copilots.md
│   ├── 29.05-ai-search.md
│   ├── 29.06-rag-applications.md
│   ├── 29.07-ai-agents.md
│   ├── 29.08-agent-interfaces.md
│   ├── 29.09-tool-use-interfaces.md
│   └── 29.10-ai-native-frontend-architecture.md
│
├── 30-generative-ui/
│   ├── 30.01-generative-ui.md
│   ├── 30.02-ai-generated-interfaces.md
│   ├── 30.03-structured-ui-schemas.md
│   ├── 30.04-tool-driven-ui.md
│   ├── 30.05-dynamic-components.md
│   ├── 30.06-model-to-ui-protocols.md
│   └── 30.07-ai-interaction-design.md
│
├── 31-ai-assisted-development/
│   ├── 31.01-github-copilot.md
│   ├── 31.02-cursor.md
│   ├── 31.03-claude-code.md
│   ├── 31.04-ai-coding-agents.md
│   ├── 31.05-agentic-coding.md
│   ├── 31.06-ai-code-review.md
│   ├── 31.07-ai-testing.md
│   ├── 31.08-ai-debugging.md
│   ├── 31.09-ai-software-development-lifecycle.md
│   ├── 31.10-vibe-coding.md
│   └── 31.11-ai-developer-workflows.md
│
├── 32-ai-safety/
│   ├── 32.01-prompt-injection.md
│   ├── 32.02-indirect-prompt-injection.md
│   ├── 32.03-data-leakage.md
│   ├── 32.04-tool-security.md
│   ├── 32.05-permission-boundaries.md
│   ├── 32.06-input-validation.md
│   ├── 32.07-output-validation.md
│   ├── 32.08-hallucinations.md
│   ├── 32.09-retrieval-poisoning.md
│   ├── 32.10-agent-sandboxing.md
│   ├── 32.11-secret-management.md
│   ├── 32.12-human-in-the-loop.md
│   └── 32.13-ai-safety-architecture.md
│
├── 33-in-browser-ai-ml/
│   ├── 33.01-browser-ml.md
│   ├── 33.02-client-side-inference.md
│   ├── 33.03-webgpu.md
│   ├── 33.04-model-loading.md
│   ├── 33.05-model-optimization.md
│   ├── 33.06-ai-performance.md
│   └── 33.07-privacy-preserving-ai.md
│
├── 34-backend-for-react-developers/
│   ├── 34.01-nodejs.md
│   ├── 34.02-express.md
│   ├── 34.03-fastify.md
│   ├── 34.04-nestjs.md
│   ├── 34.05-rest-apis.md
│   ├── 34.06-graphql.md
│   ├── 34.07-rpc.md
│   ├── 34.08-http.md
│   ├── 34.09-headers.md
│   ├── 34.10-cookies.md
│   ├── 34.11-cors.md
│   ├── 34.12-authentication.md
│   ├── 34.13-authorization.md
│   └── 34.14-rate-limiting.md
│
├── 35-databases/
│   ├── 35.01-postgresql.md
│   ├── 35.02-sql.md
│   ├── 35.03-database-design.md
│   ├── 35.04-indexes.md
│   ├── 35.05-transactions.md
│   ├── 35.06-redis.md
│   └── 35.07-nosql-fundamentals.md
│
├── 36-backend-architecture/
│   ├── 36.01-monolith.md
│   ├── 36.02-modular-monolith.md
│   ├── 36.03-microservices.md
│   ├── 36.04-event-driven-architecture.md
│   ├── 36.05-message-queues.md
│   ├── 36.06-background-jobs.md
│   └── 36.07-distributed-systems.md
│
├── 37-security/
│   ├── 37.01-xss.md
│   ├── 37.02-csrf.md
│   ├── 37.03-cors.md
│   ├── 37.04-csp.md
│   ├── 37.05-clickjacking.md
│   ├── 37.06-session-security.md
│   ├── 37.07-jwt.md
│   ├── 37.08-oauth-2-0.md
│   ├── 37.09-openid-connect.md
│   ├── 37.10-secure-cookies.md
│   ├── 37.11-dependency-vulnerabilities.md
│   ├── 37.12-supply-chain-attacks.md
│   └── 37.13-secret-exposure.md
│
├── 38-web3/
│   ├── 38.01-blockchain-fundamentals.md
│   ├── 38.02-ethereum.md
│   ├── 38.03-smart-contracts.md
│   ├── 38.04-wallets.md
│   ├── 38.05-rpc.md
│   ├── 38.06-transaction-signing.md
│   ├── 38.07-wallet-authentication.md
│   └── 38.08-react-plus-web3.md
│
├── 39-react-native/
│   ├── 39.01-react-native.md
│   ├── 39.02-expo.md
│   ├── 39.03-navigation.md
│   ├── 39.04-native-modules.md
│   ├── 39.05-platform-specific-code.md
│   ├── 39.06-push-notifications.md
│   ├── 39.07-offline-storage.md
│   └── 39.08-mobile-performance.md
│
├── 40-open-source/
│   ├── 40.01-git.md
│   ├── 40.02-github.md
│   ├── 40.03-branching.md
│   ├── 40.04-pull-requests.md
│   ├── 40.05-issues.md
│   ├── 40.06-code-review.md
│   ├── 40.07-conventional-commits.md
│   ├── 40.08-semantic-versioning.md
│   ├── 40.09-changelogs.md
│   ├── 40.10-npm-packages.md
│   ├── 40.11-monorepos.md
│   ├── 40.12-open-source-contribution.md
│   ├── 40.13-good-first-issues.md
│   └── 40.14-maintainer-workflows.md
│
├── 41-git-contribution-workflow/
│   ├── 41.01-git-branches.md
│   ├── 41.02-git-commits.md
│   ├── 41.03-commit-conventions.md
│   ├── 41.04-prs.md
│   ├── 41.05-pr-reviews.md
│   ├── 41.06-merge-strategies.md
│   ├── 41.07-rebase.md
│   ├── 41.08-conflict-resolution.md
│   ├── 41.09-github-issues.md
│   ├── 41.10-issue-templates.md
│   ├── 41.11-pr-templates.md
│   └── 41.12-release-management.md
│
├── 42-commit-conventions/
│   ├── 42.01-build.md
│   ├── 42.02-ci.md
│   ├── 42.03-docs.md
│   ├── 42.04-feat.md
│   ├── 42.05-fix.md
│   ├── 42.06-perf.md
│   ├── 42.07-refactor.md
│   ├── 42.08-test.md
│   ├── 42.09-commit-scope.md
│   ├── 42.10-commit-summary.md
│   ├── 42.11-commit-body.md
│   ├── 42.12-commit-footer.md
│   ├── 42.13-breaking-change.md
│   ├── 42.14-deprecated.md
│   └── 42.15-revert-commits.md
│
├── 43-community-developer-skills/
│   ├── 43.01-technical-communication.md
│   ├── 43.02-architecture-discussions.md
│   ├── 43.03-explaining-tradeoffs.md
│   ├── 43.04-technical-presentations.md
│   ├── 43.05-lightning-talks.md
│   ├── 43.06-public-speaking.md
│   ├── 43.07-q-and-a.md
│   ├── 43.08-mentoring.md
│   ├── 43.09-networking.md
│   ├── 43.10-code-review.md
│   ├── 43.11-constructive-feedback.md
│   └── 43.12-community-contribution.md
│
├── 44-technical-decision-making/
│   ├── 44.01-architecture-tradeoffs.md
│   ├── 44.02-performance-tradeoffs.md
│   ├── 44.03-complexity-vs-simplicity.md
│   ├── 44.04-build-vs-buy.md
│   ├── 44.05-client-vs-server.md
│   ├── 44.06-csr-vs-ssr.md
│   ├── 44.07-static-vs-dynamic-rendering.md
│   ├── 44.08-sql-vs-nosql.md
│   ├── 44.09-rest-vs-graphql.md
│   ├── 44.10-monolith-vs-microservices.md
│   ├── 44.11-local-first-vs-server-first.md
│   └── 44.12-ai-vs-deterministic-systems.md
│
├── 45-project-product-building/
│   ├── 45.01-project-architecture.md
│   ├── 45.02-product-requirements.md
│   ├── 45.03-ux.md
│   ├── 45.04-prototyping.md
│   ├── 45.05-mvp-development.md
│   ├── 45.06-feature-prioritization.md
│   ├── 45.07-technical-debt.md
│   ├── 45.08-scalability.md
│   ├── 45.09-deployment.md
│   ├── 45.10-monitoring.md
│   ├── 45.11-documentation.md
│   └── 45.12-open-source-projects.md
│
├── 46-react-kolkata-community-participation/
│   ├── 46.01-meetups.md
│   ├── 46.02-workshops.md
│   ├── 46.03-lightning-talks.md
│   ├── 46.04-project-showcases.md
│   ├── 46.05-buildathons.md
│   ├── 46.06-quizzes.md
│   ├── 46.07-networking.md
│   ├── 46.08-mentorship.md
│   ├── 46.09-community-champions.md
│   ├── 46.10-call-for-speakers.md
│   ├── 46.11-project-parbon.md
│   ├── 46.12-open-source-contribution.md
│   └── 46.13-community-partnerships.md
│
├── 47-community-platform-opportunities/
│   ├── 47.01-developer-directory.md
│   ├── 47.02-speaker-directory.md
│   ├── 47.03-mentor-directory.md
│   ├── 47.04-project-showcase.md
│   ├── 47.05-event-archive.md
│   ├── 47.06-talk-archive.md
│   ├── 47.07-learning-hub.md
│   ├── 47.08-jobs-board.md
│   ├── 47.09-tech-calendar.md
│   ├── 47.10-community-profiles.md
│   ├── 47.11-contributor-leaderboard.md
│   ├── 47.12-community-badges.md
│   ├── 47.13-topic-voting.md
│   ├── 47.14-community-q-and-a.md
│   ├── 47.15-event-matchmaking.md
│   ├── 47.16-qr-networking.md
│   └── 47.17-community-newsletter.md
│
├── 48-advanced-frontier-topics/
│   ├── 48.01-react-compiler.md
│   ├── 48.02-react-server-components.md
│   ├── 48.03-concurrent-react.md
│   ├── 48.04-distributed-browser-computing.md
│   ├── 48.05-webassembly.md
│   ├── 48.06-web-workers.md
│   ├── 48.07-webrtc.md
│   ├── 48.08-local-first-systems.md
│   ├── 48.09-crdts.md
│   ├── 48.10-in-browser-ml.md
│   ├── 48.11-ai-agents.md
│   ├── 48.12-generative-ui.md
│   ├── 48.13-ai-native-frontend-architecture.md
│   ├── 48.14-ai-safety.md
│   ├── 48.15-observability.md
│   └── 48.16-distributed-systems.md
│
└── 49-master-project/
    ├── 49.01-react.md
    ├── 49.02-typescript.md
    ├── 49.03-nextjs.md
    ├── 49.04-server-components.md
    ├── 49.05-client-components.md
    ├── 49.06-react-compiler.md
    ├── 49.07-tailwind.md
    ├── 49.08-design-system.md
    ├── 49.09-tanstack-query.md
    ├── 49.10-postgresql.md
    ├── 49.11-redis.md
    ├── 49.12-authentication.md
    ├── 49.13-authorization.md
    ├── 49.14-ai-chat.md
    ├── 49.15-rag.md
    ├── 49.16-ai-agents.md
    ├── 49.17-generative-ui.md
    ├── 49.18-websockets.md
    ├── 49.19-collaborative-editing.md
    ├── 49.20-indexeddb.md
    ├── 49.21-offline-first.md
    ├── 49.22-crdt.md
    ├── 49.23-testing.md
    ├── 49.24-playwright.md
    ├── 49.25-vitest.md
    ├── 49.26-ci-cd.md
    ├── 49.27-docker.md
    ├── 49.28-observability.md
    ├── 49.29-performance-optimization.md
    ├── 49.30-security.md
    ├── 49.31-cloud-deployment.md
    └── 49.32-open-source-contribution.md
```