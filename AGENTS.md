# Slides - workflow & conventions

This repo is for standalone slide decks/presentations that can be hosted (e.g. GitHub Pages).

Key idea: **both `index.md` and `index.html` are source files**.
- `index.md` — content/structure scratchpad (what we iterate on first)
- `index.html` — the final page we may keep editing by hand after generation

## Folder layout (one presentation = one folder)

`<slug>/`
- `index.md` — working Markdown
- `index.html` — final HTML page (tracked in Git, can be hand-edited)
- `assets/` — images/video/pdf/etc used by the presentation

Optional (if needed later):
- `meta.json` — title/date/tags for building a catalog

## Conventions

- Paths inside `index.md` / `index.html` are **relative** (`./assets/...`) so the folder is portable.
- Use `kebab-case` for filenames and folders; avoid spaces and non-ASCII in paths.
- Keep `assets/` for files only (no HTML/MD in there).

## Editing & regeneration policy (no `draft.html`)

We keep only `index.html`.

When regenerating `index.html` from `index.md` (via agent/tool):
1. Save current `index.html` state in Git (commit, or at least stage) so nothing is lost.
2. Generate and overwrite `index.html`.
3. Review the diff and manually adjust as needed.

Rule: regeneration may overwrite `index.html`, but **Git is the safety net** and diff review is mandatory.
