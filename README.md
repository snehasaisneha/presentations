# presentations

Repository for Beamer presentations using the shared **Navy** theme.

- **GitHub:** [snehasaisneha/presentations](https://github.com/snehasaisneha/presentations)
- **Theme:** `theme/navy-theme.tex` — Professional Navy colour scheme and footline; see `theme/README.md` for usage.
- **Slides:** `presentations/` — One subfolder per presentation (e.g. `presentations/template/`).

## Quick start

1. Copy `presentations/template/` to a new folder, e.g. `presentations/my-talk/`.
2. Edit `main.tex`: title, author, date, and content.
3. Build from the presentation folder: `pdflatex main.tex`.

Theme path in each `.tex` must point to `theme/navy-theme.tex` (e.g. `\input{../../theme/navy-theme.tex}` from `presentations/my-talk/main.tex`).
