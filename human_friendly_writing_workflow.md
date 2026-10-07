# Writing for Humans: A Workflow for Mathematical Exposition

**Commissioned by Aparna Gupte and Seyoon Ragavan.**  
**Document prepared with GPT-6 Astra and Claude Opus 5.5.**

Write mathematical papers and explanations so that a thoughtful human reader can understand why the argument works and verify its details. Aim for precise, natural prose, economical notation, and a visible chain of reasoning. Preserve the mathematical substance while improving the reader's route into it.

This workflow consolidates two writing guides, the manuscript guidance accompanying them, and lessons from earlier rewrites. It is intended for reuse across mathematics and theoretical computer science.

**Critical priorities.** The following four requirements are mandatory throughout. Their detailed rules appear in the linked sections:

- **Notation discipline (critical):** apply the reader-benefit test in [Section 3](#3-make-notation-earn-its-place).
- **Minimum sufficient exposition (critical):** subject to an easy-to-follow, complete logical chain, make the output as short as possible; see [Sections 1](#1-fix-the-audience-purpose-and-scope) and [9](#9-write-direct-connected-prose).
- **Proof-paragraph discipline (critical):** each proof paragraph must correspond to one main point in the proof outline; see [Section 7](#7-motivate-proof-steps-and-make-them-checkable).
- **Reader-relative terminology (critical):** explain terminology unfamiliar to the intended reader before relying on it; see [Section 4](#4-use-terminology-grounded-in-the-literature-and-suited-to-the-reader).

## 1. Fix the audience, purpose, and scope

Match the requested audience, level, length, and format. A short conceptual answer should answer the question directly; it need not have the architecture of a paper. A substantial manuscript needs enough organization to make its construction and proof understandable as a whole. When explaining a paper while also revising it, distinguish conversational commentary from prose intended to enter the manuscript.

Assume a smart reader who may know the broader area but not this problem or its neighboring subfields. Decide what that reader can reasonably be expected to know. Explain the remaining prerequisites where they become relevant, or supply the necessary preliminaries.

For substantial rewrites, favor lecture-note-level explanations when they prevent nontrivial reconstruction by the reader. Pedagogy takes priority over resembling the terseness of a typical research paper. First make the complete logical chain easy to follow; then minimize word count aggressively subject to that constraint. Lecture-note-level detail does not justify redundant explanation: among equally understandable drafts, always choose the shorter one. This is a constraint on the reader's work, not a target page count.

Respect the author's editing boundaries. Preserve sections, conventions, or notes the author has explicitly reserved. Do not turn a local request into an unrequested revision of the rest of the paper.

## 2. Preserve the mathematics and its attribution

Treat supplied and approved definitions, theorem statements, assumptions, quantifiers, constants, parameter regimes, normalizations, and proof dependencies as locked. Do not silently strengthen, weaken, generalize, simplify, or repair them. Keep editorial changes separate from mathematical corrections and changes of scope. Flag a suspected issue or unresolved substantive choice for the author rather than choosing an interpretation silently.

Before a long or claim-dense rewrite, privately record the formal and informal claims, their exact assumptions and ranges, their status, and their dependencies. Use this record to keep the abstract, introduction, overview, proofs, and applications consistent. Retain the source version so that the final rewrite can be compared with the material it was meant to preserve.

Keep theorems, conditional results, conjectures, heuristics, empirical evidence, and intuition visibly distinct. In LaTeX manuscripts, use separate `conjecture` and `heuristic` environments. Distinguish an equality from a bound and a sufficient condition from a necessary one. State important conditionality wherever the result is advertised, and identify which later conclusions depend on it. An intuitive explanation must actually follow from the mathematics; it must not suggest a broader result than the proof establishes.

Cite the source of an imported result at its first substantive use, with a theorem or section reference when available. Where relevant, also credit the particular proof or exposition being used. Rewriting, shortening, or reorganizing an argument does not remove its attribution requirements. Distinguish new mathematics from a clearer presentation of existing mathematics, and do not infer a proof's historical origin from similarity alone.

Do not invent references, novelty claims, or comparisons with prior work. Use calibrated priority language when priority has not been independently established. A successful compilation, numerical experiment, preservation check, or audit verdict is not a proof of mathematical correctness.

## 3. Make notation earn its place

Preserve good existing notation and prefer established conventions. Introduce a symbol when it names a recurring object, exposes useful structure, or makes a difficult expression easier to follow; the benefit must outweigh the burden of learning and remembering it. Change existing notation only when the change offers a clear benefit to the reader. Avoid renamed copies, unnecessary half-sums and differences, long chains of aliases, and separate names for expressions used only once. Keep temporary notation local.

**Notation discipline:** reuse supplied notation by default and judge additions or replacements by the reader-benefit test above, rather than a universal numerical cap. Do not add symbols, shorthand, or names merely to make the presentation look tidier. For manuscript work or a rewrite, identify proposed notation changes, define them completely, explain their benefit, and obtain the author's explicit permission before using them unless those changes have already been authorized. An author-requested notation freeze must be respected. When no notation has been supplied, prefer words where they suffice and introduce only notation that earns its place.

Economy of notation does not mean hiding structure. Retain indices, domains, codomains, dependencies, identity operators, registers, and tensor factors when they clarify the expression or prevent mistakes. In particular, err toward keeping tensor factors explicit when they identify where an operator acts. Suppress information only when an established convention makes it immediately and unambiguously recoverable.

Define symbols near their first use and explain the role of important parameters. A short notation paragraph or glossary can help with recurring notation, but the prose should remain readable without constant consultation of it.

## 4. Use terminology grounded in the literature and suited to the reader

Use technical terms in their established sense in the relevant field. Check unfamiliar terminology before relying on it. Do not coin impressive-sounding names for ordinary quantities or proof steps, and do not present local shorthand as accepted vocabulary. When new terminology is genuinely needed, define it precisely, explain its usefulness, and explicitly distinguish it from standard usage. Proposals for new terminology are subject to the notation rule above.

A term being standard somewhere does not make it familiar to the intended reader. Leave specialized vocabulary unexplained only when it is standard in an area the reader has demonstrated familiarity with. Expertise in one topic does not imply expertise in a neighboring variant. If familiarity is uncertain, explain the substance briefly in ordinary language before relying on the name.

Even an established term should serve the exposition. If naming an identity or technique adds no useful information, describe the operation itself: which terms cancel, which property gives the inequality, or which space is being selected. When the exact technical name is necessary, use it and explain what it means in this argument.

Judge words in context rather than maintaining a blanket list of forbidden technical terms. Terminology that is misplaced in one setting may be conventional and useful in another.

## 5. Organize around the argument the reader needs

Lead with the answer, main claim, or central idea. For substantial exposition, a useful order is:

1. State the problem operationally and identify the objects involved.
2. Explain a familiar construction, known baseline, or tempting first attempt.
3. Isolate the precise obstruction or gap.
4. Introduce the central idea because it addresses that obstruction.
5. State the result with its assumptions and scope.
6. Develop the construction and proof, then explain the consequences and limitations.

Use only the parts needed for the task. Do not preserve the chronological order in which an argument was discovered. Keep a failed approach only when a brief example or counterexample helps motivate the successful idea, and place it immediately before that idea. Remove abandoned routes, obsolete bounds, duplicated derivations, and alternatives that no longer serve the argument.

Choose a coherent approved proof route. Where several ingredients are needed, give a compact explanation of how they depend on one another before entering the details. Repeat an idea at a different level of detail only when the new treatment materially reduces the reader's work; repetition merely for emphasis should go.

## 6. Make the opening and technical overview teach the paper

The title should identify the main result, construction, or application, rather than an internal proof device; avoid uninformative generic titles such as “Better (X).” The abstract should be understandable without the body's auxiliary notation. It should communicate the problem, headline result and assumptions, the prior limitation addressed, the main conceptual ingredient, and the relevant quantitative guarantee or limitation. It should not recount the proof line by line.

The introduction should define the problem from first principles, specify the regime under discussion, explain the baseline and prior gap, and state the principal results and their significance. Introduce the construction informally before its formal notation. Give a problem-focused account of prior work; move a longer historical discussion later if it interrupts the main explanation. State applications, comparisons, conditionality, and limitations explicitly, and discuss optimality and concurrent work when relevant. Use a contributions subsection, comparison table, or organization paragraph when the complexity of the paper warrants it.

Include a substantial technical overview when the proof has several nontrivial ingredients. Begin from the exact mathematical target, preferably through a familiar construction or a simple special case. The overview should explain why the proof works, not merely list its lemmas or sections.

For each central object or parameter, explain what it represents, why it is introduced, which obstacle it addresses, what the governing lemma says informally, and how that conclusion feeds into the next step. Show the identity or inequality that makes the idea work, and point to the corresponding formal argument. Explain the reason for a split into parameter regimes before presenting the separate formulas.

A worked example should expose a real difficulty, illustrate a mechanism, or prevent a tempting mistake. Avoid decorative examples that repeat what the prose already makes clear. When a new abstraction is the contribution, explain what it captures, why it suffices, whether necessity is known, how it is instantiated, which earlier constructions it explains, and what lies outside its scope, using the supplied or approved terminology.

For an algorithmic construction, describe a complete operation early enough that the reader knows what the component lemmas are establishing. Explain its inputs, outputs, order of operations, and dependencies. Where relevant, distinguish the mathematical object being defined from the procedure that computes or approximates it. Separate accuracy guarantees from termination and resource guarantees, and explain how local guarantees combine into the required global one.

Keep the overview faithful to the formal argument. Preserve the distinctions on which the proof depends, and identify which details are deferred. By its end, a careful reader should understand the main ideas and dependencies without checking all the algebra.

## 7. Motivate proof steps and make them checkable

Before a substantial definition, construction, or calculation, explain the immediate problem it addresses. Introduce an auxiliary object by its purpose before its formula. Say what a change of variables exposes, what a decomposition separates, or what a parameter controls. Follow an important calculation with its consequence for the proof. State the intermediate claim, justify it, and explain how it advances the target. A sequence of correct equations should also have an intelligible direction.

Keep this guidance proportionate. Routine algebra needs little commentary; a surprising choice, delicate inference, or unusual order of operations deserves more. Replace announcements that a step is “crucial,” “natural,” or “powerful” with an explanation of what it makes possible.

**Proof-paragraph discipline:** each proof paragraph must correspond to one main point in the proof outline. Begin a new paragraph when the proof changes main points. Do not combine unrelated steps in one paragraph or fragment one idea into unnecessary short paragraphs.

Make formal statements self-contained enough to identify their domains, quantifiers, hypotheses, normalizations, and parameter restrictions. In the proof, explain non-obvious equalities and inequalities, check the hypotheses of imported lemmas, and handle relevant boundary cases. Use explicit case splits when the logic branches. State what is fixed, random, conditioned on, or allowed to depend on earlier choices whenever that distinction is used. Signpost approximations and their error terms, and give the exact claim before an asymptotic simplification when the distinction matters.

Do not hide a substantive inference behind “clearly,” “similarly,” “straightforward,” “standard,” or “one can check.” Prove it, explain it, or cite it precisely. Such phrases are appropriate only when the omitted verification is genuinely immediate from what has already been shown.

Prefer a structural explanation when it accounts for a long calculation. Identifying a projector or an orthogonality relation, for example, can be more illuminating than expanding every term. State the property that makes the recognition valid and show enough of the connection for the reader to check it. Remove algebra that merely repeats an established identity, but preserve the steps where assumptions, normalization, inequalities, or the order of operations matter.

Conclude by connecting the final calculation to the stated claim. Intuition may orient a formal proof, but it cannot replace a necessary argument.

## 8. Keep the central difficulty visible in the organization

Separate background and definitions, the construction, its correctness or structural analysis, applications, and any conjectural or empirical discussion when these serve different purposes. Give reusable primitives clear definitions and important implications explicit theorem or lemma statements. If an approved general theorem is already available, state it once and derive the concrete application from it; do not invent a generalization for elegance. Prove necessity and sufficiency separately when both are claimed.

Open a technical section with enough orientation to explain what it establishes, why it is needed, and where its conclusion will be used. Keep these local signposts short and specific; do not repeatedly restate the whole paper's plan.

Keep the argument that resolves the central difficulty in the main text. Move routine but lengthy calculations or secondary developments to appendices when that improves the reading order. State clearly the guarantees supplied by deferred material and retain the proofs needed to justify them. Reorganization must not make a difficult obligation disappear behind an unexplained reference.

For a long document, provide useful navigation through descriptive headings, cross-references, and a contents list. Use a conclusion or open-questions discussion when there are substantive consequences, limitations, or further directions to explain; do not force one into a short, focused argument.

## 9. Write direct, connected prose

Use a direct, pedagogical scholarly voice, normally in the first-person plural. Follow the surrounding paper's spelling conventions; use American spelling by default when none has been established. Use familiar words and concrete mathematical verbs: define, expand, subtract, commute, bound, average, and conclude. Let each sentence build on the preceding one and each paragraph develop a coherent point. A short paragraph connecting two displays may save the reader substantial effort.

Avoid symbol-first exposition without interpretation, needless sectioning, inflated vocabulary, excessive marketing, and unexplained claims that an argument is “clean,” “sharp,” or “key.” Transitions should express an actual relationship, such as an obstruction, consequence, or dependency. Phrases such as “The obstruction is…,” “To see why…,” and “The upshot is…” are welcome when they genuinely guide the reader; they are examples, not a script to repeat mechanically. The prose can have personality, and an occasional rhetorical question can help when it sharpens the reasoning.

Remove conversation artifacts, prompt-specific narration, agent or verifier language, raw search output, and scratch calculations from finished exposition, subject to the author's explicit instructions about retained notes. Use tables and diagrams when they communicate needed structure more effectively than prose. Give tables self-contained captions identifying the quantities, assumptions, and regimes needed to understand them. Do not add them as decoration.

Every remaining sentence should state the answer, carry reasoning, define or motivate something needed, or prevent a likely misunderstanding. Shorten by removing repetition and unnecessary work, not by making the reader supply missing reasoning.

## 10. Check the draft and deliver it cleanly

For LaTeX manuscripts, reuse the existing template and macros where possible. Use theorem environments, semantic labels such as `thm:security`, `lem:interpolation`, and `eq:main-bound`, and `\ref`, `\Cref`, or `\eqref` rather than hard-coded numbering. Keep short formulas inline, group genuine derivations in `align` or `align*`, and number displays when they need to be referenced. Avoid manual equation tags, repeated `\boxed{...}` displays, decorative main-result cards, unused template machinery, and unexplained macros.

**Line-break discipline.** Do not insert unnecessary paragraph breaks or forced line breaks. In prose, start a new line only for a new paragraph or a genuine structural element such as a displayed equation, theorem environment, list, or table, except where an established source-wrapping convention calls for ordinary line wrapping. Respect that convention: ordinary source newlines that leave the rendered paragraph unchanged are not paragraph breaks.

Perform three final passes:

1. **Mathematical consistency.** Compare the draft with the recorded claims and source. Check agreement among the overview, statements, proofs, and applications; check assumptions, dependencies, constants, normalization, and claim status. Review any proposed notation against Section 3. Confirm that each significant inference is justified and each imported result is properly attributed.
2. **Reader orientation.** Read for the intended audience. Check whether the opening supplies a useful understanding of the problem, each central object has a purpose before its technical use, and the proof can be followed without reconstructing nontrivial steps. Check paragraph structure, unfamiliar terminology, and whether repetition or compression increases the reader's work. Explicitly ask: can this draft be shortened without omitting necessary reasoning or increasing the reader's work? Remove what can be removed under that constraint.
3. **Presentation.** Check for undefined symbols or macros, duplicate labels, unresolved references, and missing citations. Check paragraph and line breaks against the discipline above, including any established source-wrapping convention. Compile the manuscript when applicable and inspect the rendered equations, figures, tables, self-contained captions, and page transitions. Check that decorative or unused template elements have been removed. A long rewrite should also be checked for accidentally omitted statements or proofs.

Return the complete polished draft in the requested format. Put unresolved mathematical or bibliographic questions in a short separate list for the author, rather than mixing them into finished prose or silently resolving them.

If an AI-use statement is requested, describe the assistance factually, including the human contributions, checks actually performed, and responsibility for the final paper as agreed by its authors. Do not invent verification or use AI involvement or an audit outcome as evidence of correctness. Keep detailed disclosure separate from the mathematical narrative; at most one concise sentence belongs in the abstract.
