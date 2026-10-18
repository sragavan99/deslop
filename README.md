# Deslop

AI-generated proofs can be hard to read even when they are correct. This workflow helps you understand a writeup, plan and produce a clearer version, and check the result.

| Step | Where | Attach |
|---|---|---|
| 1. Digest | Working chat | `explainer.md` |
| 2. Plan | Same chat | `human_friendly_writing_workflow.md` |
| 3. Write | Same chat | Nothing new |
| 4. Verify | Fresh chat | `verifier.md` |

Use [`explainer.md`](explainer.md) for the discussion, [`human_friendly_writing_workflow.md`](human_friendly_writing_workflow.md) for the manuscript, and [`verifier.md`](verifier.md) for the independent check. Replace the bracketed parts in the prompts below.

## 1. Digest

Attach `explainer.md` and send:

> Can you review the writeup at [LINK TO WRITEUP]? This is incomprehensible to a human. Explain the high-level ideas to me. Throughout this interaction, adhere stringently to the principles in explainer.md.

Ask follow-up questions until you understand the main ideas and what makes the argument work.

## 2. Plan

In the same chat, attach `human_friendly_writing_workflow.md` and send:

> Using the insights we've gleaned, I would like to see how you would rewrite the original writeup using the attached human_friendly_writing_workflow.md to make it clearer, including a clear technical overview. Let me know what changes you would make. Throughout this interaction, adhere stringently to the principles in explainer.md.

Discuss the proposed changes until you agree on a plan. Identify where simplifications used in the discussion need their technical details restored in the rewrite.

## 3. Write

In the same chat, send:

> The plan we've arrived at sounds good. Please prepare a full rewrite of the original paper following it and human_friendly_writing_workflow.md. When in doubt, prioritize pedagogy and lecture-note-level explanations over the terseness of a typical research paper.

End the prompt with one of these sentences:

- **Chat mode:** "Send a .tex file and its compiled PDF here in the chat."
- **Git mode**, if the model can open pull requests: "Submit a .tex file and its compiled PDF to [REPOSITORY URL] under a new folder titled [FOLDER NAME], as a pull request."

## 4. Verify

Start a fresh chat so the auditor does not inherit the writer's reasoning.
Attach `verifier.md` and both writeups at exact recorded versions. State the
audit purpose and full or component scope. The default full correctness check
is an **independent audit**.

Before sending, inspect the actual writeups, supporting material, prompts,
ledgers, filenames and launch instructions. Withhold internal checks, previous
reviews, and direct or indirect disclosures of their favorable or unfavorable
judgments or review reasoning. Remove pressure toward either acceptance or
rejection. Preserve the mathematics, assumptions, attribution, limitations and
open proof obligations. If these share a source with evaluative history,
prepare an identified audit copy, retain the original and record the mapping;
do not silently change the candidate or conceal a missing argument. Record
the content check with the packet version; filenames or hashes alone are not
a content check.

> Independently audit [LINK AND EXACT VERSION OF THE REWRITE] in full for correctness subject to the attached verifier.md. Test the argument adversarially while remaining indifferent to the outcome. Compare it with [LINK AND EXACT VERSION OF THE ORIGINAL] for omitted claims or changes in assumptions and conclusions. Do not seek earlier judgments of these writeups.

The review opens with a verdict, such as VERIFIED or INCOMPLETE, followed by
the findings, exact version, scope and any observed prior-judgment exposure.
Use the same completeness standard for an internal check and an external
audit; the verifier distinguishes routine expansion from substantive repair.

Bring the findings back to the writing chat for repairs. For the next review,
choose and declare the purpose:

- **Independent audit:** withhold earlier judgments and review reasoning
  again. Freeze the complete independent report before any later comparison;
  an initial proof map is insufficient.
- **Adjudication:** supply exact prior findings and manuscript versions to
  resolve specified objections or conflicting reviews.
- **Delta audit:** supply the exact baseline, its review and the patch, and
  identify inherited coverage and rechecked dependencies. Changes to a
  load-bearing interface or proof layer require fresh end-to-end review.

Adjudication and delta audits are not blind full audits. Reconcile disputed
inferences using the exact versions and supporting mathematics. A newer
VERIFIED label alone does not resolve an earlier objection. Preserve both
reviews and hold acceptance of affected claims until their load-bearing
objections are resolved. A substantive repair creates a revised candidate to
audit; it does not retrospectively verify the original. If earlier judgments
are encountered during an independent review, disclose what and when, retain
the useful review as non-blind, and do not count it as independent replication.

## Example: L = RL = BPL

[`bpl_example/`](bpl_example/) contains a rewrite of OpenAI's preprint *Exact Derandomization of Logarithmic Space: L = RL = BPL* (September 23, 2026). You can compare [the original](https://github.com/openai/math/blob/adc7f1241b42e322a6451854ab7e4b4c146bf78a/preprints/Exact-Derandomization-of-Logarithmic-Space-L-equals-RL-equals-BPL-September-23-2026/paper.pdf) with [the rewrite](bpl_example/current/main.pdf), and read [the adversarial audit of the rewrite](bpl_example/current/adversarial-audit.pdf) from Step 4.

We make no claim to originality. The mathematics, theorem statements and proofs are OpenAI's. We only put the OpenAI version through this workflow with some light questioning and steering. [`bpl_example/current/README.md`](bpl_example/current/README.md) describes what changed. An earlier rewrite, made with a predecessor of this workflow, is kept in [`bpl_example/old_v1/`](bpl_example/old_v1/).

Like the OpenAI original, `bpl_example/` is distributed under the Apache License 2.0 (see [`bpl_example/current/LICENSE`](bpl_example/current/LICENSE)). The rest of this repository is under the MIT License.

## Attribution and Feedback Form

This folder is the result of iterations by Aparna Gupte (MIT) and Seyoon Ragavan (MIT) to assist with our own research. This was prepared using GPT-5.6 Sol, GPT-6 Astra, and Claude Opus 5.5.

If you would like to give feedback, please fill out [this form](https://docs.google.com/forms/d/e/1FAIpQLSdUxJtw3jFhZHynOe6IPheNxXginvY_B7AHHi1d5uh4KwNvdw/viewform); we greatly appreciate it.

