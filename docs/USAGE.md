# Author guide

## Title and authors

```tex
\title[Short Running Title]{Full Paper Title}
\aesauthor[affil={1},equal,corresponding]{Author One}
\aesauthor[affil={1,2},equal]{Author Two}
\aesauthor[affil={2}]{Author Three}
\aesaffiliation{1}{Institution A}
\aesaffiliation{2}{Institution B}
\aesemails{\aesemail{author_one@example.org}}
```

The optional title argument supplies the running header. Use `affil` for
institution IDs, `equal` for joint contribution, and `corresponding` (or `corr`)
for the contact author. Remove flags you do not need. Multiple authors can share
either marker; the corresponding explanation is printed once.

Write email addresses literally, including `_` and `@`. Delete `\aesemails`
to omit the email row. Multiple addresses can be separated with `\quad`.

Optional notes and keywords go before `\begin{document}`:

```tex
\aesequalnote{These authors contributed equally.}
\aescorrespondingnote{Correspondence to Author One.}
\aeskeywords{Agent evaluation; Benchmarking; Reliability}
```

Omitting keywords, or leaving `\aeskeywords{}` empty, adds no space.

## Sections and paragraphs

```tex
\section{Method}
\label{sec:method}
\subsection{Evaluation Setup}
\subsubsection{Scoring}
```

Use a blank line between paragraphs. Do not add leading spaces, `\indent`, or
`\\` to start a paragraph. Refer to a heading with `Section~\ref{sec:method}`.
For equations, use `\label` and `\eqref` with the `amsmath` package.

## Citations and references

```tex
\citet{hua2025charting}       % Author (year)
\citep{na2025psychotherapy}       % (Author, year)
\citep{ma2025manipulation,hua2025scoping}
...
\bibliography{references}
```

Add entries to `references.bib`. Keep complete author lists in that file; the
style abbreviates long lists for display. A DOI is preferred to a URL when both
are present. Do not add `\bibliographystyle`: AES already selects it.

Citations link to References. Each reference has numbered return links to its
individual citation occurrences. `Cited at: 1, 2` means the first and second
citation of that reference, not pages 1 and 2. Finish the full latexmk build to
resolve these links.

## Figures and tables

```tex
\begin{figure}[htbp]
  \centering
  \includegraphics[width=\linewidth]{assets/example-figure.pdf}
  \caption{Describe the figure and define any abbreviations.}
  \label{fig:example}
\end{figure}
```

Put captions below both figures and tables, with `\label` after `\caption`.
Refer to them with `Figure~\ref{fig:example}` or `Table~\ref{tab:example}`.
The default placement is `htbp`; allow LaTeX to move large floats. Vector PDFs
work well for plots and diagrams. The sample figure has an optional editable
TikZ source in `assets/`.

```tex
\begin{table}[htbp]
  \centering
  \begin{tabular}{@{}lr@{}}
    \toprule
    System & Score \\
    \midrule
    Baseline & 61.0 \\
    Variant & 68.5 \\
    \bottomrule
  \end{tabular}
  \caption{Example values; replace with actual results.}
  \label{tab:example}
\end{table}
```

Use `tabularx` for wrapping columns, as in `main.tex`. Figures and tables share
the caption format `Figure 1 | ...` and `Table 1 | ...` automatically.

## Tables spanning pages

`aeslongtable` takes five arguments: column specification, column count,
caption, label, and repeated column headings. Do not wrap it in `table`.

```tex
\begin{aeslongtable}{@{}p{3cm}p{11cm}@{}}{2}
  {A description of the complete table.}
  {tab:records}
  {Field & Description}
Task ID & Stable identifier for the task.\\
Outcome & Success, failure, or an unresolved state.\\
\end{aeslongtable}
```

The continuation heading and column headings repeat on subsequent pages. The
full caption appears below the final fragment. Add rows to the example above
as needed, and use column widths that fit the text area.

## Optional end sections and appendices

```tex
\begin{aespubliconly}
\aesbackmattersection{Acknowledgments}
Acknowledgments go here.
\end{aespubliconly}

\aesbackmattersection{Ethics Statement}
This section remains visible in review mode.

\bibliography{references}
\appendix
\section{Additional Results}
\label{app:results}
```

Delete optional sections that do not apply. Put identity-bearing end matter
inside `aespubliconly` to omit it from review mode. The appendix begins on a new
page; figure and table numbering restarts in each appendix as A1, B1, and so on.
First-level headings appear as PDF bookmarks; no printed contents page is added.

## Before sharing

Replace the sample names, affiliations, prose, and fictional results. Compile
the intended mode, check the PDF, and resolve missing citations or references.
The sample paper demonstrates layout, not a completed study.
