# Deslop

AI-generated proofs can be hard for a human to read even when they are correct. This folder describes a three-prompt sequence that rewrites such a proof so a person can follow it, then checks that the rewrite is still correct.

| Step | Where | Attach |
|---|---|---|
| 1. Plan the rewrite | New chat | `human_friendly_writing_workflow.md` |
| 2. Write the rewrite | Same chat as step 1 | Nothing |
| 3. Audit the rewrite | New chat | `verifier.md` |

[`human_friendly_writing_workflow.md`](human_friendly_writing_workflow.md) tells the model how to write for a human reader, and [`verifier.md`](verifier.md) tells it how to check a proof adversarially. In the prompts below, replace the bracketed parts.

## 1. Plan

Start a new chat, attach `human_friendly_writing_workflow.md`, and send:

> Can you review the writeup at [LINK TO WRITEUP]?
>
> This is incomprehensible to a human. I would like to see if you can rewrite this using the attached human_friendly_writing_workflow.md to make it clearer (with a technical overview and all).
>
> Take a look and let me know what changes you would make.

Discuss the proposed changes until you agree on a plan. A few rounds of back-and-forth are worth the time, because the structure of the rewrite is much easier to change now than after it has been written.

## 2. Write

In the same chat, send:

> The plan we've arrived at sounds good. Please prepare a full rewrite of this paper along the lines of your suggestions. When in doubt, err on the side of pedagogy and lecture-note-level explanations. The pedagogy is more important than stylistically resembling typical CS theory papers.

End the prompt with one of these sentences, depending on where you want the result:

- **Chat mode:** "Send a .tex file and its compiled PDF here in the chat."
- **Git mode**, if the model can open pull requests: "Submit a .tex file and its compiled PDF to [REPOSITORY URL] under a new folder titled [FOLDER NAME], as a pull request."

## 3. Audit

Start a new chat so that the auditor does not inherit the writer's reasoning. Attach `verifier.md` and send:

> Adversarially audit [LINK TO THE REWRITE] for correctness subject to the verifier.md standards attached. Be pedantic.

The review opens with a single verdict, such as VERIFIED or INCOMPLETE, and then lists the problems that the main result depends on.

## Example: L = RL = BPL

[`bpl_example/`](bpl_example/) contains a rewrite of OpenAI's preprint *Exact Derandomization of Logarithmic Space: L = RL = BPL* (September 23, 2026). You can compare [the original](https://github.com/openai/math/blob/adc7f1241b42e322a6451854ab7e4b4c146bf78a/preprints/Exact-Derandomization-of-Logarithmic-Space-L-equals-RL-equals-BPL-September-23-2026/paper.pdf) with [the rewrite](bpl_example/main.pdf).

We make no claim to originality. The mathematics, theorem statements and proofs are OpenAI's. We only put the OpenAI version through a predecessor of this workflow, which reorganized the presentation and expanded the explanations. [`bpl_example/README.md`](bpl_example/README.md) describes what changed.

Like the OpenAI original, `bpl_example/` is distributed under the Apache License 2.0 (see [`bpl_example/LICENSE`](bpl_example/LICENSE)). The rest of this repository is under the MIT License.

## Attribution and Feedback Form

This folder is the result of iterations by Aparna Gupte (MIT) and Seyoon Ragavan (MIT) to assist with our own research. This was prepared using GPT-5.6 Sol, GPT-6 Astra, and Claude Opus 5.5.

If you would like to give feedback, please fill out [this form](https://docs.google.com/forms/d/e/1FAIpQLSdUxJtw3jFhZHynOe6IPheNxXginvY_B7AHHi1d5uh4KwNvdw/viewform); we greatly appreciate it.
