# 31. AI-ASSISTED DEVELOPMENT - Complete Deep Dive

## 31.15 AI-Assisted Development - Summary Deal-Breaker Checklist

| Area | Deal-Breaker | Consequence |
|------|-------------|-------------|
| **Landscape** | More code = more value | 30% more code, zero more issues resolved |
| **Landscape** | No governance | 94% adoption, 6% governance |
| **GitHub Copilot** | Using for long-horizon tasks | Copilot is for inline completions; use Claude Code for deep reasoning |
| **Cursor** | Not using parallel sub-agents | Serial use wastes Cursor's strength |
| **Claude Code** | Using for simple autocomplete | It's an agentic tool; use Copilot for inline |
| **Claude Code** | Assuming 88.6% SWE-bench = real-world | SWE-bench Pro drops to ~45-50% |
| **Devin** | Using for ambiguous tasks | Devin works best with well-scoped tickets |
| **Devin** | Assuming autonomy = reliability | 79% merge rate within 30 days |
| **AI Code Review** | Using as a merge gate | F1 ≈ 19%; most flagged issues are noise |
| **AI Code Review** | No human review | AI review lowers cost but does not replace |
| **AI Code Review** | Not tuning sensitivity | Required configuration for effective review |
| **AI Testing** | No real browser verification | Agent's claim counts only when the running app confirms it |
| **AI Testing** | No side-effect verification | Test results alone are insufficient |
| **AI Debugging** | Single-agent debugging | 27 bugs found vs. 66 with multi-agent |
| **AI-SDLC** | Assuming AI-first = human-free | Humans move higher in the value chain |
| **AI-SDLC** | No backpressure | Review times jumped 49% |
| **Vibe Coding** | Treating Generate as finish line | Review and Refine are highest-value stages |
| **Vibe Coding** | Vibe coding safety-critical systems | AI generates plausible, not provably correct, code |
| **Best Practices** | No spec | Vague prompts produce vague code |
| **Best Practices** | Big tasks in one prompt | Break into small, iterative chunks |
| **Best Practices** | No rules file | Agents reinvent conventions every session |
| **Best Practices** | Treating AI like a senior developer | It's a pool of junior developers |
| **Best Practices** | No security pass | 40.8% of AI code is vulnerable |
| **Security** | Assuming AI code is secure | 40.8% vulnerable; 44% of tasks have known vulnerabilities |
| **Security** | Client-side-only auth | Common AI-generated vulnerability |
| **Security** | Browser-exposed API keys | AI may embed secrets in frontend code |
| **Security** | Missing RLS policies | AI-generated Supabase schemas often lack Row-Level Security |
| **Challenges** | Illusion of correctness | AI code looks right but isn't |
| **Challenges** | 4× code duplication | Enforce DRY in review |
| **Challenges** | Architectural degradation | AI operates tactically, not strategically |
| **Challenges** | Feeling productive vs. measured performance | Track real metrics, not feelings |
| **Challenges** | Cost as a barrier | 28% cite cost as top obstacle; token spend up 10-13× |

---

**The Big Rule:** AI-assisted development is not about writing more code faster. It's about **shifting human effort from generation to verification**. The 30% code increase with zero additional issues resolved is the defining data point of 2026. Use AI for generation, but invest in review, security, and architecture. Keep specs before code. Break work into small chunks. Maintain a rules file. Do a security pass on every AI-generated PR. Never merge code you cannot explain line by line. And remember: **the agent's claim that its code works counts only when the running app confirms it.**
