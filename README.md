# HKU CV Template

A clean, professional LaTeX CV template styled with The University of Hong Kong's
brand colours (HKU Green `#007B5E`).

## Requirements

| Component | Purpose |
|-----------|---------|
| **XeLaTeX** | Main compiler (supports system fonts via `fontspec`) |
| `fontspec` | System font loading |
| `fontawesome5` | Contact icons (envelope, phone, ORCID, GitHub…) |
| `tikz` | Top accent bar |
| `geometry`, `xcolor`, `hyperref` | Standard layout/colour/links |
| `tabularx`, `booktabs` | Entry layout |
| `titlesec`, `enumitem`, `parskip` | Typography control |
| **TeX Gyre Pagella** | Body serif — free, ships with TeX Live / MiKTeX |
| **TeX Gyre Heros** | Sans-serif labels — free, ships with TeX Live / MiKTeX |
| **TeX Gyre Cursor** | Monospace — free, ships with TeX Live / MiKTeX |

All fonts are part of a standard TeX Live or MiKTeX installation — no extra
downloads required. To use a different font simply replace the `\setmainfont`
block with any other font available on your system.

## Compile

```bash
xelatex hku_cv.tex
xelatex hku_cv.tex   # run twice for correct page refs
```

Or using `latexmk`:

```bash
latexmk -xelatex hku_cv.tex
```

## Structure

```
hku_cv/
└── hku_cv.tex      ← single-file template, all macros inline
```

## Customisation Guide

### Personal details
Edit the header block — replace `Your Full Name`, department/faculty,
and all contact fields.

### Sections
Each section uses `\cvsection{Title}`.  
Reorder or delete sections freely — they are independent blocks.

### Entry macros

| Macro | Arguments | Used for |
|-------|-----------|----------|
| `\cventry` | `{dates}{title}{org}{location}{description}` | Experience, Education |
| `\pubentry` | `{authors}{title}{venue}{year}{url}` | Publications |
| `\awardentry` | `{year}{description}{amount}` | Awards |
| `\skillrow` | `{category}{items}` | Skills |

### Colours
All colours are defined at the top of the preamble:

```latex
\definecolor{hkugreen}{HTML}{007B5E}
\definecolor{hkudark}{HTML}{004D3A}
```

Change `hkugreen` to match your faculty's accent colour if needed.

### Font swap
The template uses TeX Gyre Pagella (body), TeX Gyre Heros (sans), and
TeX Gyre Cursor (mono) — all free and bundled with TeX Live / MiKTeX.

To switch to a different font:
```latex
\setmainfont{Latin Modern Roman}   % or any other installed font
```

## Licence
Free to use and adapt. No attribution required.
