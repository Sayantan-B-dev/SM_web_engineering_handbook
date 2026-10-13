# 32. AI SAFETY - Complete Deep Dive

## 32.14 AI Safety - Summary Deal-Breaker Checklist

| Area | Deal-Breaker | Consequence |
|------|-------------|-------------|
| **Fundamentals** | Treating safety as "model alignment" | The system is the attack surface |
| **Fundamentals** | Assuming prompt injection is a chatbot problem | Indirect injection is the default case |
| **Prompt Injection** | Assuming the user is hostile | IPI bypasses all user-identity controls |
| **Prompt Injection** | No output validation | Tool outputs carry IPI payloads back into context |
| **Prompt Injection** | Single-agent with full permissions | One compromise = full access |
| **IPI** | No retrieval hardening | Poisoned docs reach context 97% of the time |
| **IPI** | Trusting similarity scores | Cosine underreports semantic compromise by 5× |
| **IPI** | No provenance tracking | Can't distinguish user data from attacker content |
| **Data Leakage** | No tenant isolation | One tenant retrieves another's documents |
| **Data Leakage** | System prompts contain secrets | Prompt injection extracts them |
| **Tool Security** | No input validation | Model output directly hits your database |
| **Tool Security** | No output validation | Tool outputs carry IPI payloads |
| **Tool Security** | Long-lived service tokens | Compromised agent has permanent access |
| **Permission Boundaries** | Bulk tool access | One compromise = full cloud access |
| **Permission Boundaries** | Wildcard IAM policies | Agent has access to everything |
| **Permission Boundaries** | No cross-stage approvals | Full workflow executes without checkpoints |
| **Input Validation** | Type-level validation only | `../../../etc/passwd` passes as `string` |
| **Input Validation** | No URL allowlist | Model calls attacker-controlled endpoints |
| **Output Validation** | No semantic validation | Syntactically valid tool call is still destructive |
| **Output Validation** | No output sanitization | Tool outputs carry IPI payloads |
| **Hallucinations** | Mitigating hallucination without monitoring refusal | Weakened safety alignment |
| **Hallucinations** | No abstention mechanism | Model answers even when it doesn't know |
| **Retrieval Poisoning** | No corpus vetting | Attackers plant documents in the vector store |
| **Retrieval Poisoning** | No provisional visibility | Unvetted content is retrievable |
| **Agent Sandboxing** | No sandbox | Agent has unrestricted access |
| **Agent Sandboxing** | Policy inside agent's control | Agent can modify its own policy |
| **Secret Management** | Secrets in system prompts | Prompt injection extracts them |
| **Secret Management** | No secret scanning in tool outputs | Agent exfiltrates credentials |
| **Secret Management** | AI-generated code with embedded secrets | Client-side API keys leaked |
| **HITL** | HITL without capacity calibration | Human approves everything blindly |
| **HITL** | No kill switch | Cannot stop runaway agent |
| **HITL** | No traceability logs | Cannot investigate incidents |
| **Architecture** | No layered architecture | Safety depends on a single control |
| **Architecture** | No runtime governance | Oversight is static, not adaptive |
| **Architecture** | No action contract | Agent actions unconstrained |

---

**The Big Rule:** AI safety in 2026 is **system safety, not model safety**. The model will be fooled. Design for it. Assume the model is not trusted, the network is not trusted, and the user is not trusted. Enforce boundaries independently of the agent. Validate every tool input and output. Sandbox every execution. Decompose privileges into stages. Require approval for destructive actions. Log everything. And never - ever - put secrets in a system prompt.

*Educational use only - AI-assisted content. See [DISCLAIMER.md](../DISCLAIMER.md) and [LICENSE.md](../LICENSE.md).*
