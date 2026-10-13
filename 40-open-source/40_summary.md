# 40. OPEN SOURCE - Complete Deep Dive

## 40.12 Summary: Open Source Deal-Breaker Checklist

| Area | Deal-Breaker | Consequence |
|------|-------------|-------------|
| **Fundamentals** | Treating open source as free labour | Maintainer burnout (Jazzband shutdown) |
| **Fundamentals** | AI slop PRs without review | You become part of the problem |
| **Git** | Committing to `main` | No review, no CI |
| **Git** | Giant commits | Impossible to review |
| **GitHub** | No `CONTRIBUTING.md` | Contributors don't know how to contribute |
| **GitHub** | No CODEOWNERS | PRs sit unreviewed |
| **Workflow** | Starting without saying hello | Duplicate effort, wasted time |
| **Workflow** | Branching from stale `main` | Merge conflicts |
| **Branching** | Long-lived feature branches | Merge hell |
| **PRs** | No description | Reviewers don't know what changed |
| **PRs** | No linked issue | No context |
| **PRs** | >500 lines | Reviewers skim instead of review |
| **Code Review** | Approving without reading | Bugs ship to production |
| **Code Review** | No response to comments | PR stalls indefinitely |
| **Conventional Commits** | Non-conventional commits | Automated tools fail |
| **Conventional Commits** | `fix` for breaking change | Consumers don't know their code will break |
| **SemVer** | Breaking change without MAJOR | Consumers' code breaks silently |
| **SemVer** | `0.x` for production libraries | API may change at any time |
| **Licensing** | No license | No one can legally use your code |
| **Licensing** | GPL for a library | Companies won't touch it |
| **Licensing** | MIT for SaaS | Competitors can take your code |
| **Community** | Vague bug reports | Maintainers can't reproduce |
| **Community** | No Code of Conduct | Toxic behaviour drives contributors away |
| **Maintainer** | No CI | Maintainers manually test every PR |
| **Maintainer** | Single maintainer | Bus factor of 1 |
| **Maintainer** | No funding | Maintainers burn out working for free |

---

**The Big Rule:** Open source is **collaboration, not consumption**. Read `CONTRIBUTING.md` before you write code. Say hello before you commit. Keep PRs small and focused. Use Conventional Commits. Respect SemVer. Choose a license deliberately. Respond to review feedback within 24 hours. And if you're a maintainer: automate the pipeline, document the process, recruit co-maintainers, and **measure community health, not just velocity**.
