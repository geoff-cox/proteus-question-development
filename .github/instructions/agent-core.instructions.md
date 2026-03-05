# AGENT-CORE.md — Global Instructions (apply to every task)

This file is the **project-wide core** for this Repository. Use it as the first block in any agent prompt.

---

## Repo summary
- Repository for interactive calculus question development written in **PreTeXt XML**.
- Core content is modular `.ptx` in `source/`.
- Builds/outputs are controlled by `project.ptx` and `publication/*.ptx`.

## High-level info
- Type: PreTeXt XML textbook project.
- Languages: PreTeXt XML (`.ptx`), MATLAB code (embedded), Python/JS/CSS/Markdown for tooling and interactives.
- Tooling/runtime: PreTeXt CLI (Python). PreTeXt may invoke npm for theme/CSS builds. Optional LaTeX for PDF.

## Layout / architecture (where to look)
- `project.ptx`: PreTeXt project manifest (targets such as `web`, `dev`, `pdf`, `runestone` if used).
- `source/`: main PreTeXt sources.
- `publication/`: publication configs (`publication.ptx`, and any platform-specific publications).
- `requirements.txt`: PreTeXt CLI dependency set (project-specific).

## Editing guardrails (agent safety)
1. **Do not alter XML structure unintentionally.**
   - Preserve all tags, attributes, ids, labels, and entity escapes unless the task explicitly requests changes.
   - Never pretty-print/reflow XML wholesale.
2. **Never edit inside tag brackets** `<...>` unless explicitly instructed.
3. **Preserve identifiers**: do not change `xml:id`, `label`, `ref`, target names, publication parameters unless explicitly requested.
4. Avoid modifying generated output directories (e.g., `web/`, `print/`) unless the task explicitly targets them.
5. Preserve escapes/entities exactly: `&amp;`, `&lt;`, `&gt;`, etc.

## Writing style (student-facing)
- Clear, approachable, conversational (use “we” and “you” naturally).
- Prefer short paragraphs, explicit transitions, and concrete examples.
- Define terms the first time they appear.

## Output contract (choose one mode per task)
### Mode A — Patch Output
Return:
1. Updated PreTeXt content (full file or clearly delimited excerpt), and
2. A short change log (bullets).

## Quality gates (self-check)
- XML remains well-formed; no tags accidentally removed/duplicated.
- Examples run as written (or would run with stated assumptions).
- Concepts are introduced in a pedagogically sensible order.
- Terminology is consistent across the section/chapter.
