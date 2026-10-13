# 42. COMMIT CONVENTIONS - Complete Deep Dive

## 42.13 Summary: Commit Conventions Deal-Breaker Checklist

| Area | Deal-Breaker | Consequence |
|------|-------------|-------------|
| **Fundamentals** | No convention | History is unparseable; changelogs are manual |
| **Fundamentals** | Convention without enforcement | Developers forget; pre-commit hooks required |
| **Type** | `fix` for a breaking change | Consumers' code breaks on upgrade |
| **Type** | Uppercase type | `commitlint` fails |
| **Type** | Empty type | `commitlint` fails |
| **Scope** | Uppercase scope | `commitlint` fails |
| **Scope** | Scope too vague (`app`) | Useless context |
| **Summary** | "fix bug" | What bug? Where? |
| **Summary** | "WIP" | Never commit WIP to shared branch |
| **Summary** | Past tense ("added") | Inconsistent history |
| **Summary** | Subject >72 chars | Truncated in `git log --oneline` |
| **Body** | No body for complex change | Six months later, no one knows why |
| **Body** | Body repeats subject | Useless |
| **Body** | No line wrapping | 500-character line, unreadable |
| **Footer** | No `BREAKING CHANGE:` for breaking change | Consumers upgrade without knowing |
| **Footer** | No blank line before footer | Git doesn't parse it |
| **BREAKING CHANGE** | `!` without footer | Changelog has no migration notes |
| **BREAKING CHANGE** | Vague description | "The API changed" is useless |
| **DEPRECATED** | Removal without deprecation period | Consumers have no time to migrate |
| **DEPRECATED** | No `Deprecation:` footer | Deprecations invisible in changelog |
| **Revert** | `git reset --hard` on shared branch | Rewrites history, breaks everyone |
| **Revert** | No `Refs:` footer | No trace of what was reverted |
| **SemVer** | `fix` for a feature | No MINOR bump |
| **SemVer** | `feat` for breaking change | MINOR bump instead of MAJOR |
| **Commitlint** | No commitlint | History unparseable |
| **Commitlint** | `type-enum` without `revert` | Revert commits fail |
| **Commitlint** | `header-max-length: 100` | Truncated in `git log --oneline` |
| **Commitizen** | No Commitizen for new contributors | They don't know the convention |
| **Changelog** | No changelog | Users don't know what changed |
| **Changelog** | Manual changelog | Out of date within a week |

---

**The Big Rule:** Commit conventions are not bureaucracy - they are **automation infrastructure**. A well-written commit message is parsed by tools, rendered in changelogs, and drives version bumps. Use **Conventional Commits** as the format. Enforce with **commitlint** and **Husky**. Guide new contributors with **Commitizen**. Mark breaking changes with **both `!` and `BREAKING CHANGE:`**. Mark deprecations with a **`Deprecation:` footer**. And never - ever - write "fix bug" and call it a commit message.

*Educational use only - AI-assisted content. See [DISCLAIMER.md](../DISCLAIMER.md) and [LICENSE.md](../LICENSE.md).*
