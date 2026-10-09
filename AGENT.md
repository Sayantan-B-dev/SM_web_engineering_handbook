# AGENT Rules — web-engineering-notes

These rules apply to every agent and contributor working in this repo. Follow them strictly.

## 1. Commits

- Use plain commit messages, e.g. `docs: split 01-web-foundations core into individual topics`.
- Never add AI tags, footers, or trailers such as `Co-Authored-By`, `Generated with`, `Assisted by`, or any mention of AI tooling.
- Never use emoji in commit messages, titles, or bodies.
- Never add anything after the commit message (no signatures, no tags, no extra lines).

## 2. Splitting core.md Into Topic Parts

- Each numbered folder (e.g. `01-web-foundations`, `02-css`) contains one `core.md` source of truth plus one file per topic plus one `*_summary.md`.
- When splitting a `core.md` into its individual topic files:
  - Copy content verbatim. No alteration, no summarising, no rewording, no reduction.
  - Preserve all subtopics, syntax blocks, code examples, tables, tricks, and deal-breakers exactly as written.
  - Each `## X.Y` section from `core.md` goes into its matching topic file, starting with its own `## X.Y` heading.
  - The `# N. ...` title plus the `## Summary ...` section plus the trailing `Next topic? ...` line go into the `*_summary.md` file.
  - Do not add new introductions, notes, placeholders, or commentary to topic files.
  - Never delete or shrink `core.md`. It stays intact as the source.
  - Verify after splitting that every non-empty, non-separator line of `core.md` exists in the outputs.

## 3. One Commit Per Folder

- Split and commit exactly one folder at a time.
- Stage and commit only that folder, e.g. `git add '01-web-foundations'` then commit.
- Do not mix multiple folders, `AGENT.md`, or unrelated files into the same commit.
- `AGENT.md` changes get their own separate commit.
- Check `git status --short` and `git diff --cached --stat` before every commit to confirm scope.

## 4. General

- Keep the existing folder and file naming exactly (`01.01-html.md`, `02.01-css-fundamentals.md`, etc.).
- Do not create new files inside topic folders except the already-listed topic and summary files.
- If a `core.md` section count does not match the topic file count, stop and ask instead of guessing.
