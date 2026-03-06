# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Repository Overview

LaTeX Beamer presentations repository using a shared Navy theme. Presentations live in `presentations/<name>/` subfolders and share the theme from `theme/navy-theme.tex`.

## Build Commands

```bash
# Build a presentation (from its folder, e.g., presentations/template/)
pdflatex main.tex
pdflatex main.tex  # Run twice for TOC/references

# Check TeX version
pdflatex --version
```

Pinned to TeX Live 2025, pdfTeX 3.141592653-2.6-1.40.27, Beamer 3.72.

## Architecture

- **`theme/navy-theme.tex`**: Shared Beamer theme (colors, footline, code listings). Edit here to change all presentations.
- **`presentations/*/`**: One subfolder per presentation, each with `main.tex` as entry point.
- **Theme path**: From `presentations/<name>/main.tex`, use `\input{../../theme/navy-theme.tex}`.

## Creating a New Presentation

1. Copy `presentations/template/` to `presentations/<new-name>/`
2. Edit `main.tex`: title, author, date, content
3. For CI builds: add empty `.ci-compile` file in the presentation folder

## CI Behavior

GitHub Actions (`.github/workflows/compile-presentations.yml`) compiles on push/PR to main when:
- `theme/**` changes (rebuilds all CI-enabled presentations)
- `presentations/**/main.tex` changes (rebuilds only changed ones)

Only presentations with a `.ci-compile` marker file are built. PDFs uploaded as `presentation-pdfs` artifact.
