# 19. TESTING - Complete Deep Dive

## Summary: Testing Deal-Breaker Checklist

| Area | Deal-Breaker | Consequence |
|------|-------------|-------------|
| **Strategy** | Testing implementation details | Tests break on every refactor |
| **Strategy** | 100% coverage goal | Low-value tests, wasted effort |
| **Strategy** | Only E2E tests | Slow CI, flaky tests |
| **Unit** | No edge cases | Bugs ship in production |
| **Unit** | Over-mocking | Testing mocks, not code |
| **Integration** | Mocking `fetch` directly | Testing your mock, not your API layer |
| **Integration** | No `onUnhandledRequest: 'error'` | Unmocked requests hit real APIs |
| **Integration** | No `resetHandlers()` | Test overrides leak |
| **Component** | `getByTestId` as primary | Doesn't verify accessibility |
| **Component** | `fireEvent` over `userEvent` | Misses focus/keyboard behavior |
| **Component** | `waitFor` + `getBy` over `findBy` | Verbose, slower |
| **E2E** | Too many E2E tests | 30-min CI, flaky |
| **E2E** | `waitForTimeout` | Flaky, slow |
| **E2E** | No trace on failure | Impossible to debug CI |
| **Jest** | Snapshot everything | Huge snapshots, no review |
| **Jest** | No `clearAllMocks` | Mock state leaks |
| **Vitest** | `globals: true` without types | `describe` undefined in TS |
| **Vitest** | `environment: 'node'` for React | `document` undefined |
| **RTL** | No `await` on `userEvent` | Interactions not processed |
| **RTL** | Testing internal state | Breaks on refactor |
| **Playwright** | CSS selectors | Break on style refactor |
| **Playwright** | No test isolation | Order-dependent flakiness |
| **Mocking** | Mocking module under test | Testing the mock, not the code |
| **Mocking** | MSW without error mode | Unmocked requests hit real API |
| **Contract** | No provider verification | Frontend and backend drift |
| **Contract** | Only happy path | Error responses untested |
| **RSC** | `render(<ServerComponent />)` | Async component not awaited |

---

**The Big Rule:** Test user-visible behavior, not implementation. Use MSW for network mocking. Use RTL for component tests, Vitest for unit/integration, Playwright for E2E and component-in-real-browser. Add contract tests when frontend and backend teams need to move independently.

*Educational use only - AI-assisted content. See [DISCLAIMER.md](../DISCLAIMER.md) and [LICENSE.md](../LICENSE.md).*
