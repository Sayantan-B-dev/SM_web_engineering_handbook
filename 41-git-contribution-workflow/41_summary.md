# 41. GIT / CONTRIBUTION WORKFLOW - Complete Deep Dive

## 41.16 Summary: Git / Contribution Workflow Deal-Breaker Checklist

| Area | Deal-Breaker | Consequence |
|------|-------------|-------------|
| **Fundamentals** | `git add .` without checking | Stages `.env`, secrets, build artifacts |
| **Fundamentals** | Committing to `main` | No review, no CI |
| **Branches** | Long-lived feature branches | Merge hell |
| **Branches** | No branch protection | Force-push to `main` |
| **Branching** | Git Flow for small team | Overkill; use GitHub Flow |
| **Commits** | Non-atomic commits | Impossible to revert one change |
| **Commits** | Vague commit messages | History is useless |
| **Commits** | Amending pushed commits | Rewriting shared history |
| **Conventional Commits** | Non-conventional commits | Tools can't generate changelogs |
| **SemVer** | Breaking change without MAJOR | Consumers' code breaks silently |
| **Merge Strategies** | No documented strategy | Every developer does it differently |
| **Rebase** | Rebasing a shared branch | Divergent history for everyone |
| **Rebase** | `--force` instead of `--force-with-lease` | Overwrites others' work |
| **Conflict Resolution** | `git add .` during conflict | Stages leftover conflict markers |
| **Conflict Resolution** | `-X ours` for all conflicts | Silently discards one side |
| **Pull Requests** | PR without description | Reviewers don't know what changed |
| **Pull Requests** | PR >500 lines | Reviewers skim instead of review |
| **PR Reviews** | Approving without reading | Bugs ship to production |
| **PR Reviews** | No response to comments | PR stalls indefinitely |
| **Issues** | No issue templates | Vague bug reports |
| **PR Templates** | No PR template | Every PR has different structure |
| **Release** | Manual artifact publishing | Ship the wrong binary at 2 a.m. |
| **Release** | Committed version files | Merge conflicts |
| **Git Hooks** | No pre-commit hooks | Secrets reach production |
| **Advanced** | No `git bisect` | Hours manually finding regression |
| **Advanced** | Using `git stash` for parallel work | Error-prone; use `git worktree` |
| **Advanced** | Large binaries without LFS | Repository becomes gigabytes |

---

**The Big Rule:** Git is a **distributed system**. Every clone is a full repository. Treat commit history as a public API - once pushed, it's shared. Use **GitHub Flow** by default. Write **atomic, conventional commits**. Keep PRs **small and focused**. Review within **24 hours**. Use **tag-triggered releases**. Enable **pre-commit hooks** for linting and secrets scanning. And never - ever - rebase a shared branch.
