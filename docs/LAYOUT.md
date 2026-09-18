# Layout settings

AES v0.1 uses the approved layout. Authors normally need no spacing overrides.
Related content stays together; transitions between content groups receive more
space. Headings sit closer to the text they introduce than to preceding content.

| Element | Setting |
|---|---|
| Paper and body margins | A4; 22 mm on all sides |
| First-page logo top | Approximately 16 mm from the paper edge |
| Logo to title | 14 pt |
| Title to authors | 12 pt |
| Authors to abstract | 16 pt |
| Body and abstract | Open Sans Regular, 11 pt; 13.6 pt baseline distance |
| Paragraphs | 4 pt separation; no first-line indent |
| Section spacing | 16 pt before; 6 pt after |
| Subsection spacing | 12 pt before; 4 pt after |
| Subsubsection spacing | 9 pt before; 3 pt after |
| Abstract box | 14 pt inner padding; 10 pt corner radius |
| List items | 2 pt separation; 6 pt topsep |
| Floats and surrounding text | 16 pt, with limited stretch and shrink |
| Consecutive floats | 12 pt, with limited stretch and shrink |
| Captions | 10/12 pt; 6 pt from the figure or table |
| Multipage tables | 16 pt before and after |
| Displayed equations | Normally 10 pt before and after |
| Footnotes | 9/12 pt; 6 pt between notes |
| References | 10/12 pt; 6 pt between entries |
| Headers and page numbers | 8/10 pt |

These are TeX spacing parameters, not measurements between visible letterforms.
Pages use `raggedbottom` to avoid stretching local spaces to fill the page.
The standard article heading policy discourages a break after only one line of
the following paragraph.

## Maintainer controls

The `Layout settings` block near the top of `aes.sty` holds the first-page and
heading dimensions. For a local first-page adjustment, a document can use:

```tex
\usepackage{aes}
\setlength{\aesfirstpagetop}{16mm}
```

This is a physical top-distance target. Do not add compensating negative
`\vspace` commands in the paper. Body geometry is set when the package loads;
change its defaults in the style if a different house layout is required.
