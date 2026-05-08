# arXiv source package

Recommended category: `cs.LG` (primary). Optional secondary category: `cs.AI`.

Compile locally with:

```bash
pdflatex main.tex
bibtex main
pdflatex main.tex
pdflatex main.tex
```

The arXiv upload should include `main.tex`, `references.bib`, `figures/`, and optional compact CSV tables under `tables/`.
