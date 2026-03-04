# Presentations

This folder holds individual presentations. Each presentation can live in its own subfolder (e.g. `template/`, `workshop-2025-12/`) with its `.tex` file and any assets.

## Tool versions (pinned)

Builds are tested with:

| Tool        | Version |
|------------|---------|
| TeX Live   | 2025    |
| pdfTeX     | 3.141592653-2.6-1.40.27 (TeX Live 2025) |
| Beamer     | 3.72 (2025/02/04) |

Check your setup with `pdflatex --version` and ensure Beamer is from the same TeX Live year (e.g. `kpsewhich beamerthemedefault.sty`).

## Using the Navy theme

Each presentation should load the shared theme from the repo root:

```latex
\input{../../theme/navy-theme.tex}
```

Adjust the path if your `.tex` is not in `presentations/<subfolder>/`.

## CI: Compile on push

A GitHub Action compiles every presentation subfolder that contains a **blank `.ci-compile` file**. To include a presentation in CI:

1. Add an empty file named `.ci-compile` in that presentation’s folder (e.g. `presentations/my-talk/.ci-compile`).
2. Ensure the main source is `main.tex` in that folder.

On each push to `main` (and on pull requests), those presentations are built and the PDFs are uploaded as the `presentation-pdfs` artifact.

## Building locally

From the folder containing your `.tex` file:

```bash
pdflatex main.tex
# run twice if you use \tableofcontents or references
```

Or use your preferred LaTeX workflow (Overleaf, latexmk, etc.).
