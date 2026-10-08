# BPL rewrite

A pedagogical rewrite of **Exact Derandomization of Logarithmic Space: L = RL = BPL**, OpenAI, September 23, 2026. The mathematical results and proof construction are attributed to that preprint. This expository adaptation was prepared with Codex on October 7, 2026.

Read [main.pdf](main.pdf). The LaTeX entry point is [main.tex](main.tex).

## What changed

The presentation now begins with the computational problem, a technical overview, and a worked example of the reward identity. The overview follows the construction from the configuration graph through the reward hierarchy, sparse estimation, total memory bound, and deterministic median calculation.

A separate section describes a complete estimator query before the component lemmas. Throughout the paper, new explanations state what each construction must accomplish, why the preceding approach is insufficient, and how the next estimate addresses that difficulty. The explanations distinguish statistical budgets from numerical precision, exact targets from computed estimates, and local storage from the memory retained across an entire recursion.

The detailed proof development remains complete. In particular, the fingerprint analysis explains its adaptive dependence issue, and the controller analysis keeps the accounting for all live memory in the main text. The longer arithmetic constructions follow the main argument in an appendix; the numerical interface they establish remains in the main text. The effective compiler and its proofs are also included. The longer historical discussion has moved to the end.

Existing mathematical notation, normalizations, theorem statements, hypotheses, and proof calculations are retained. Terminology is explained where it is needed; the rewrite does not introduce a competing notation system. This is an exposition of the source argument, not a proposal of new mathematical results.

## Source and attribution

The source is pinned to commit [`adc7f1241b42e322a6451854ab7e4b4c146bf78a`](https://github.com/openai/math/commit/adc7f1241b42e322a6451854ab7e4b4c146bf78a) of `openai/math`:

- [Original PDF](https://github.com/openai/math/blob/adc7f1241b42e322a6451854ab7e4b4c146bf78a/preprints/Exact-Derandomization-of-Logarithmic-Space-L-equals-RL-equals-BPL-September-23-2026/paper.pdf).
- [Original LaTeX directory](https://github.com/openai/math/tree/adc7f1241b42e322a6451854ab7e4b4c146bf78a/preprints/Exact-Derandomization-of-Logarithmic-Space-L-equals-RL-equals-BPL-September-23-2026/build).

The source repository distributes this material under Apache License 2.0; its [LICENSE](LICENSE) is included. Modified source files carry an adaptation notice. The original bibliography and both original figures are retained, including their citations and mathematical content.

## Build

From this directory, with a TeX distribution containing `latexmk` and the packages imported by `preamble.tex`:

```sh
latexmk -pdf -interaction=nonstopmode -halt-on-error main.tex
```

This produces `main.pdf`. All required LaTeX sources, figures, and bibliography entries are included. No external data or generated figure assets are needed.

## Checks on this version

- All 69 original theorem, lemma, proposition, corollary, claim, definition, and assumption statements are unchanged apart from whitespace. All seven original remarks are also unchanged.
- All 67 proof environments remain. All displayed mathematical blocks outside the original introduction are preserved apart from whitespace; the introductory displays are incorporated into the expanded overview.
- All original cross-reference labels and all 34 cited bibliography keys remain. The bibliography file is unchanged.
- The PDF compiles without undefined references, undefined citations, or overfull/underfull box warnings. Its pages were rendered and inspected for layout problems.

These checks concern preservation and presentation of the source argument. A mathematical correctness review is a separate task.
