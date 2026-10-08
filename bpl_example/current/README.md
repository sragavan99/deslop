# BPL rewrite — run 2

This folder contains a complete lecture-note exposition of **Exact Derandomization of Logarithmic Space: L = RL = BPL**. The original mathematics is credited to OpenAI. The expository adaptation was prepared with Codex on October 8, 2026.

- [`main.tex`](main.tex): self-contained source, including the preamble, three TikZ figures, and bibliography.
- [`main.pdf`](main.pdf): compiled manuscript.
- [`LICENSE`](LICENSE): Apache License 2.0, retained from the source distribution.

## Sources and scope

The mathematical source is the [September 23, 2026 preprint](https://github.com/openai/math/blob/adc7f1241b42e322a6451854ab7e4b4c146bf78a/preprints/Exact-Derandomization-of-Logarithmic-Space-L-equals-RL-equals-BPL-September-23-2026/paper.pdf), pinned at `adc7f1241b42e322a6451854ab7e4b4c146bf78a`. The rewrite also adapts the expanded exposition in [`sragavan99/deslop/bpl_example`](https://github.com/sragavan99/deslop/tree/2021122121dc136f559583cf1b169d0213d73504/bpl_example), pinned at `2021122121dc136f559583cf1b169d0213d73504`.

The preparation followed [Writing for Humans](https://github.com/sragavan99/deslop/blob/2021122121dc136f559583cf1b169d0213d73504/human_friendly_writing_workflow.md) and the accompanying [explainer guide](https://github.com/sragavan99/deslop/blob/2021122121dc136f559583cf1b169d0213d73504/explainer.md). Before drafting, the source statements and proof dependencies were inventoried and the construction was separated into its exact targets, statistical estimator, and implementation obligations.

The principal presentation changes are:

- A substantial technical overview starting from the continuation-probability equation, the residual row-sum stopping condition, and the two correction extremes: zero correction and full squaring.
- A complete account of correction selection: pilot detection, frozen column multipliers, restarted thresholded propagation, and copying. Incoming load is defined as a scale-dependent count of substantial predecessors, with both its access and error-accounting roles explained.
- A three-panel propagation figure explicitly labeling residual edge weights and accumulated success values below the vertices.
- Visually distinct algorithm boxes, followed by their analyses. The exact construction is distinguished from the procedure that estimates its entries; accuracy, termination, and total live memory receive separate arguments.
- The approved vector/matrix notation, entry subscripts, explanatory names for the success vector and accuracy levels, and a source-notation glossary.
- Explicit connections with Richardson iteration, conditional expansion and hashing, Benczúr–Karger sampling, RVW/Reingold and derandomized squaring, and small-space Laplacian solvers. Electrical elimination is omitted.
- The complete proof material, including compression, adaptive fingerprints, arithmetic, simultaneous stack-space accounting, probability approximation, accepting-computation extraction, and the effective compiler. Longer arithmetic details and the compiler are placed in appendices.

This is an expository adaptation of the source's claims and proof route, not an independent certification of its main theorem.

## Build

With a standard TeX Live installation containing TikZ, `tcolorbox`, and the packages listed in the source:

```sh
latexmk -pdf -interaction=nonstopmode -halt-on-error main.tex
```

Alternatively, run `pdflatex -interaction=nonstopmode -halt-on-error main.tex` three times. No external `.bib`, figure, or section files are needed, and shell escape is unnecessary.

## Checks

The source inventory and final manuscript contain the same 69 theorem, lemma, proposition, corollary, and definition environments, all 67 proofs, and all seven remarks. Every original section-source label is retained. A separate comparison before the approved notation conversion located all 282 displayed formulas from the original technical sections in the editorial source. These are preservation checks, not proof verification.

The standalone source was compiled from a clean directory. The final build has no unresolved references or citations, duplicate labels, or overfull/underfull box warnings. All pages were rendered for layout review, with closer inspection of the overview, figures, algorithm boxes, tables, renamed equations, and page transitions. The figure's three updates were also checked with exact rational arithmetic.

This run adds only this new folder; the earlier rewrite is unchanged.
