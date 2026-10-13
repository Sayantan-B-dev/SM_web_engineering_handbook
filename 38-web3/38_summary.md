# 38. WEB3 - Complete Deep Dive

## 38.9 Web3 - Summary Deal-Breaker Checklist

| Area | Deal-Breaker | Consequence |
|------|-------------|-------------|
| **Fundamentals** | Treating Web3 as a monolith | Each layer (L1, L2, wallet, RPC) has different trade-offs |
| **Fundamentals** | Ignoring the UX gap | Extra steps, software, and education hurdle adoption |
| **Blockchain** | Confusing immutability with "no changes" | Upgrades happen via forks or migration |
| **Ethereum** | Assuming all L2s are equally secure | Stage 0 vs Stage 2 rollups have vastly different trust assumptions |
| **Ethereum** | Ignoring blob capacity expansion | L2 economics change with each upgrade |
| **Smart Contracts** | No audit | Even minor bugs can cause major losses |
| **Smart Contracts** | Using outdated Solidity | The compiler version itself is a risk |
| **Smart Contracts** | Ignoring reentrancy | Still the most critical vulnerability class in 2026 |
| **Wallets** | Seed phrases as the only recovery | UX disaster; ERC-4337 enables social recovery and passkeys |
| **Wallets** | No EIP-6963 support | Users with multiple wallets can't choose which to connect |
| **Wallets** | Assuming ERC-4337 works everywhere | Requires bundler, paymaster, EntryPoint |
| **RPC** | Single RPC provider | If your provider goes down, your dApp goes down |
| **RPC** | Ignoring tail latency | A provider with great median can have a 1,370ms p99 |
| **RPC** | No API key rotation | Leaked keys can be abused |
| **Transaction Signing** | Signing raw hex | Users can't verify what they're signing |
| **Transaction Signing** | No nonce management | Concurrent transactions fail |
| **Transaction Signing** | Signing without domain binding | Signature replay across dApps |
| **SIWE** | No nonce validation | Replay attacks |
| **SIWE** | No domain binding | Signature replay |
| **SIWE** | No expiration | Signature valid forever |
| **SIWE** | Storing the signature as a credential | Use HttpOnly session cookies after verification |
| **React + Web3** | Not using TanStack Query | wagmi requires it for caching; stale data otherwise |
| **React + Web3** | RainbowKit without Reown Project ID | RainbowKit requires it |
| **React + Web3** | Wagmi v3 with RainbowKit | RainbowKit pins wagmi v2; don't upgrade until supported |
| **React + Web3** | No multi-chain support | Users expect to switch chains |
| **React + Web3** | Hardcoding contract addresses | Addresses differ per chain |

---

**The Big Rule:** Web3 in 2026 is not just speculation - it's a production stack. Use **viem + wagmi + RainbowKit + TanStack Query** for React frontends. Use **SIWE (EIP-4361)** for authentication. Use **ERC-4337 smart accounts** for new users and **EIP-7702** to bridge existing EOAs. Benchmark **RPC providers by region and tail latency**, not global averages. Check **L2BEAT stages** before bridging. Always **audit smart contracts**. And never - ever - ask users to sign raw hex.

*Educational use only - AI-assisted content. See [DISCLAIMER.md](../DISCLAIMER.md) and [LICENSE.md](../LICENSE.md).*
