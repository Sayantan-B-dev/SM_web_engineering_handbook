# AGENT Rules - web-engineering-notes

These rules apply to every agent and contributor working in this repo. Follow them strictly.

## 1. Commits

- Use plain, descriptive messages, e.g. `docs: split 05-react-fundamentals core into individual topics`.
- Never add AI tags, footers, or trailers such as `Co-Authored-By`, `Generated with`, `Assisted by`, or any mention of AI tooling.
- Never use emoji in commit messages, titles, or bodies.
- Never add anything after the commit message (no signatures, no tags, no extra lines).
- Create exactly one commit per numbered chapter for chapter-specific content work.
  Never combine several chapters into a single commit.
- A repo-wide uniform change (a text substitution, a standard footer, a formatting
  sweep) is ONE commit covering every affected file. Do not create one commit per
  chapter for a change that is identical across chapters.

## 2. Splitting a Chapter Core Into Topic Parts

- Each numbered folder (e.g. `05-react-fundamentals`) contains one `<NN>_core.md` source plus one file per topic plus one `<NN>_summary.md`.
- Complete content preservation is mandatory:
  - Copy content verbatim. No alteration, no summarising, no rewording, no reduction.
  - Preserve all subtopics, syntax blocks, code examples, tables, tricks, and deal-breakers exactly as written.
  - Never omit, shorten, reorder, or duplicate content.
- Mapping from the core file to the topic files:
  - Each `## X.Y` section goes into its own topic file, starting with its own `## X.Y` heading.
  - The `# N. ...` module title plus the `## Summary ...` section go into the `<NN>_summary.md` file.
  - Match each section to the topic file that already exists for that topic.
  - If a chapter contains more topics than the currently listed files, add the extra topic files inside that chapter folder. Do not rename or restructure the existing files.
- Do not add new introductions, notes, placeholders, or commentary to topic files.

## 3. Verify Before Committing

- Before committing a chapter, verify that every line of `<NN>_core.md` is present in the split files:
  - Reconstruct the module from the topic files plus the summary file and confirm it matches the core.
  - Confirm that nothing was omitted, altered, or duplicated.
- Remove the original `<NN>_core.md` only after its content has been distributed and verified.
- If verification fails, fix the split and re-verify. Never commit unverified content.

## 4. Scope and One Commit Per Chapter

- Split, verify, and commit exactly one chapter at a time, in order.
- The one-commit-per-chapter rule covers chapter content work. A uniform change
  applied repo-wide is a single commit, per section 1.
- Stage and commit only that chapter's folder, e.g. `git add '05-react-fundamentals'`.
- Do not mix chapters, `AGENT.md`, or unrelated files into the same commit.
- `AGENT.md` changes get their own separate commit.
- Do not change unrelated files, folders, or content.
- Check `git status --short` and `git diff --cached --stat` before every commit to confirm scope.

## 5. General

- Keep the existing folder and file naming exactly (`05.01-jsx.md`, `05_summary.md`, etc.).
- The original `<NN>_core.md` files are gitignored; they are removed after their content has been distributed and verified, and are never committed.

## 6. Filling Leftover Topic Files

- A "leftover" is a topic file named in the syllabus that has no matching `## X.Y` section in the chapter core.
- Never leave a leftover file as an empty placeholder. Fill it with real content written in the same style as the rest of the chapter.
- Structure it like the other topic files: a `## <Title>` heading, a `### Subtopic Tree`, explanatory sections with code examples, and a `### Real-World Deal-Breakers` list.
- Use the unnumbered `## <Title>` heading, because the chapter's `## X.Y` numbers are already assigned to other files.
- Keep the file's existing name and write about the topic that name describes.
- Filled content is authored rather than copied from a core, so it gets its own per-chapter commit and is not subject to the verbatim-copy verification in section 3.
