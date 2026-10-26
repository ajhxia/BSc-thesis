# Tailscale Thesis — modular LaTeX project

## Files

- Thesis.tex: root document. It includes the other files; compile this file.
- styles/thesis-style.sty: packages, typography, theorem environments,
  hyperlinks and TikZ diagrams.
- config/metadata.tex: thesis title, author, advisor and degree details.
- frontmatter/abstract.tex: abstract.
- chapters/: one file for each chapter, including the existing empty outlines.
- backmatter/acknowledgements.tex: acknowledgements.
- bibliography/references.tex: your current thebibliography entries.
- figures/: place future image files here.

## VS Code / LaTeX Workshop

Open the entire extracted folder in VS Code, then open Thesis.tex and
build with LaTeX Workshop (or latexmk -pdf Thesis.tex).

Each chapter has a % !TeX root = ../Thesis.tex comment so LaTeX Workshop
can compile the main document even when you are editing a chapter file.

You need the sapthesis document class installed in your LaTeX distribution,
or its sapthesis.cls file in the root directory. The uploaded file referred
to this class but did not include it; it is not bundled in this archive.

## How to write

For a new chapter, create chapters/06_new_chapter.tex with a chapter command,
then add an input call for that chapter in Thesis.tex at the desired position.
Write chapter, section, label, ref and cite commands normally inside the
chapter files: LaTeX processes them as part of one document.

To add an image, place it under figures/ and write:
\includegraphics[width=0.7\textwidth]{image-name.png}
To change the appearance of your thesis, edit styles/thesis-style.sty.

Original layout values are preserved: linespread=0.9,
parindent=0pt and parskip=0.4em.

The existing prose, manual bibliography, and figure/citation keys
were carried over unchanged. The heading hierarchy was simplified.

## Section hierarchy

Use chapters for the major parts, sections for distinct topics, and
subsections for topics requiring sustained discussion. The completed
Fundamentals chapter uses no numbered subsubsections: the short
mapping/filtering distinctions use run-in paragraph headings.

The Tailscale and Experimental Analysis chapters are still outlines.
Their future subsection headings are preserved as LaTeX comments
(lines starting with %). Remove the % when you actually write a
substantial subsection. This keeps empty placeholders out of the
table of contents and prevents excessive subdivision.
