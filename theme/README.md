# Navy Beamer Theme

Reusable Professional Navy theme for Beamer presentations.

## How to use

1. In your presentation `.tex` file, use the **default** theme with **miniframes** and **circles**, then load the navy theme.

2. **Path:** From a presentation inside `presentations/<your-slides>/`, the theme path is `../../theme/navy-theme.tex` (two levels up to repo root, then `theme/`).

### Minimal preamble

```latex
\documentclass{beamer}
\usetheme{default}
\useoutertheme{miniframes}
\useinnertheme{circles}
\usepackage{listings}
\usepackage{xcolor}
\usepackage{bookmark}
\usepackage{url}

% Load the navy theme (adjust path if your .tex is in a different location)
\input{../../theme/navy-theme.tex}

\title[Short Title]{Your Full Title}
\subtitle{Optional Subtitle}
\author[Short Name]{Your Name}
\date{\today}

\begin{document}
\maketitle
% ... your frames ...
\end{document}
```

### Path reference

| Your .tex location                    | Path to theme              |
|--------------------------------------|----------------------------|
| `presentations/my-talk/main.tex`     | `../../theme/navy-theme.tex` |
| `presentations/main.tex`             | `../theme/navy-theme.tex`   |
| Repo root `main.tex`                 | `theme/navy-theme.tex`      |

## What this theme sets

- **Colours:** NavyDark, NavyMid, NavyLight (header/footer, titles, items).
- **Footline:** Author | Short title | Date + slide number.
- **Code listings:** Gray background, single frame, breaklines (if you use `\usepackage{listings}`).

To tweak colours, edit `theme/navy-theme.tex` and reuse in all presentations.
