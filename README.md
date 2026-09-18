# Agent Evaluation Science LaTeX Template

**Version 0.1** · A paper template for [Agent Evaluation Science](https://evalscience.org/).

Write your paper in `main.tex`. AES handles typography, author information,
figures, tables, references, and appendices through a single `aes.sty` file.

[Sample PDF](main.pdf) · [Anonymous PDF](main-review.pdf) · [Author guide](docs/USAGE.md)

## Quick start

### Overleaf

1. Download the complete project as a ZIP and upload it to Overleaf.
2. Select **XeLaTeX** as the compiler in project settings.
3. Set **main.tex** as the main document and compile.
4. Replace the sample title, authors, abstract, and body with your paper.

Keep the folder structure intact, including `fonts/` and `assets/`.
The `% !TeX program = xelatex` comment does not change Overleaf's compiler.

### Local compilation

With TeX Live or MacTeX and `latexmk` installed, run from the project root:

```sh
latexmk -xelatex main.tex
```

LuaLaTeX is also supported:

```sh
latexmk -lualatex main.tex
```

**pdfLaTeX is not supported.** Open Sans font files are bundled with the template.

## Public and anonymous review modes

Use public mode to display authors, affiliations, and emails:

```tex
\documentclass[11pt,a4paper]{article}
\usepackage{aes}
```

For anonymous review, replace `\usepackage{aes}` with:

```tex
\usepackage[review]{aes}
```

You can also compile `main-review.tex` without editing the mode in `main.tex`:

```sh
latexmk -xelatex main-review.tex
```

Review mode displays anonymous authors, hides the template's author details
and public-only blocks, clears author metadata, and adds line numbers.
Check the body, figures, self-citations, and external links for identifying
information yourself.

## Title and authors

```tex
% Optional short title for the running header.
\title[Short Paper Title]{Your Full Paper Title}

% Institution IDs; optional contribution and correspondence markers.
\aesauthor[affil={1},equal,corresponding]{Author One}
\aesauthor[affil={1,2},equal]{Author Two}
\aesauthor[affil={2}]{Author Three}

\aesaffiliation{1}{Institution A}
\aesaffiliation{2}{Institution B}
\aesemails{\aesemail{author_one@example.org}}
```

- `affil={1,2}` associates an author with multiple institutions.
- `equal` marks joint contribution.
- `corresponding`, or `corr`, marks a corresponding author.
- Write email addresses literally: do not escape `_` or `@` inside `\aesemail`.
- Delete `\aesemails` to omit the email row.

Optional keywords and custom notes go before `\begin{document}`:

```tex
\aeskeywords{Agent evaluation; Benchmarking; Reliability}
\aesequalnote{These authors contributed equally.}
\aescorrespondingnote{Correspondence to Author One.}
```

Omitted or empty keywords take up no space.

## Writing your paper

Use ordinary LaTeX sections and blank lines between paragraphs. The template
sets paragraph spacing and removes first-line indentation automatically.

```tex
\section{Method}
\label{sec:method}

Describe the method here.

Start a new paragraph with a blank line.
```

`main.tex` includes working examples of figures, tables, equations, lists,
footnotes, and appendices. Place captions below figures and tables, with
`\label` after `\caption`. See the [author guide](docs/USAGE.md) for copyable
examples, including tables that span multiple pages.

### Citations

Add sources to `references.bib` and cite them using:

```tex
\citet{hua2025charting}  % Author (year)
\citep{na2025psychotherapy}  % (Author, year)
```

Print the reference list with:

```tex
\bibliography{references}
```

AES selects the bibliography style and loads `natbib`. Do not add another
`\bibliographystyle` or mix in `biblatex`.

Citations link to their reference entries. The numbered **Cited at** links in
References return to individual citation occurrences, including repeated
citations on the same page. These numbers are not page numbers.

### Optional end matter

```tex
\begin{aespubliconly}
\aesbackmattersection{Acknowledgments}
Acknowledgments go here.
\end{aespubliconly}

\bibliography{references}

\appendix
\section{Additional Results}
```

The `aespubliconly` block is omitted in review mode. Appendices start on a new
page, with figure and table numbering such as A1 and B1.

## Project files

| File | Purpose |
|---|---|
| [`main.tex`](main.tex) | Editable paper scaffold; start here |
| [`main-review.tex`](main-review.tex) | Anonymous review entry point |
| [`references.bib`](references.bib) | Sample bibliography |
| [`aes.sty`](aes.sty) | All AES formatting |
| `aes-author-year.bst` | Author-year bibliography style |
| `fonts/` | Bundled Open Sans fonts and font license |
| `assets/` | AES logo and replaceable example figure |
| [`docs/USAGE.md`](docs/USAGE.md) | Author commands and examples |
| [`docs/LAYOUT.md`](docs/LAYOUT.md) | Layout settings for maintainers |
| [`CHANGELOG.md`](CHANGELOG.md) | Release history |

The sample names and numerical results are fictional. Replace them before
sharing your paper. The sample demonstrates layout, not a completed study.

## Troubleshooting

| Problem | What to check |
|---|---|
| Compiler error or many undefined commands | Select XeLaTeX, then recompile from scratch |
| Missing fonts or logo | Upload the full project and preserve its folders |
| Citation appears as `?` | Check the key in `references.bib` and complete the latexmk build |
| Email or URL causes an error | Use a raw address inside `\aesemail{...}` or `\url{...}`, without Markdown syntax |
| Old formatting after an update | Recompile from scratch |

The style already loads `graphicx`, `booktabs`, `natbib`, and `hyperref`.
Add other packages as needed. Avoid manual spacing overrides for routine prose.
The default font setup targets English and Latin scripts; other writing systems
require appropriate font configuration.

For a bug report, include the compiler, a minimal example, and the relevant
error message. Include a PDF screenshot for a layout issue.

## Credits and licenses

Open Sans is distributed under the [SIL Open Font License](fonts/OFL.txt).
The bibliography style is derived from `plainnat.bst`; its attribution is
preserved and the [LPPL text](licenses/LPPL-1.3c.txt) is included.

See [third-party notices](THIRD-PARTY-NOTICES.md) for details about the fonts,
bibliography style, and AES artwork.
