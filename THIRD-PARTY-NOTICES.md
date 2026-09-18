# Sources and third-party notices

## Open Sans

The four unmodified TTF files in `fonts/` are Open Sans (Regular, Bold,
Italic, Bold Italic), supplied with the reference materials used to build
this template. The embedded font metadata identifies the Open Sans Project.
They are distributed under the SIL Open Font License 1.1; see `fonts/OFL.txt`.
Upstream: https://github.com/googlefonts/opensans

## Bibliography style

`aes-author-year.bst` is a renamed, modified version of `plainnat.bst`,
copyright 1993–2007 Patrick W. Daly. The original license and attribution
are preserved in the file. It is distributed under the LaTeX Project
Public License, version 1 or later; a copy of version 1.3c is included
in `licenses/LPPL-1.3c.txt`.

Modifications: year placement for articles; hyperlink presentation;
six-author display limit without truncating the source database;
DOI preference over URL. Sorting and natbib citation-label behavior are retained.

## AES artwork and new template files

`assets/aes-mark.pdf` is derived from the AES artwork supplied for this project,
using the purple/navy/cyan palette selected during template design.
The mark is provided for AES paper identity. Third-party font and bibliography
licenses do not license the AES name, mark, or trademarks.

The AES style, examples and documentation are project deliverables
for the template owner. This package does not assign them an additional public
software or brand license on the owner's behalf.

## TeX dependencies

The package uses standard TeX distribution components (fontspec, babel,
geometry, hyperref, natbib, caption, booktabs, longtable, tcolorbox, parskip,
fancyhdr, lineno, enumitem, etoolbox, xurl, xparse, environ and fix-cm).
These dependencies are loaded from the user's TeX installation and are not
vendored. The optional sample figure source additionally loads TikZ and the
standalone class; the paper uses its precompiled PDF.
