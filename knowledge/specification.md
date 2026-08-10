---
title: Specification
project:
  name: "Grounded Vault Research Blog and Paper"
  repository: "chpollin/grounded-vault-paper"
method:
  name: Promptotyping
  url: https://dhcraft.org/Promptotyping/
status: draft
language: en
created: "2026-08-10"
updated: "2026-08-10"
expected-warnings: [W-EMPTY, W-NO-OUTPUT]
related: [index, schema, operations]
---

# Specification

Purpose, parameters and settled decisions of this vault instance. The invariant architecture (layer model, anchor mechanics, check contracts, status progression) lives in [[knowledge/schema]] and [[knowledge/operations]]; this document holds what this project decided.

## Purpose

This vault produces a research blog on the Grounded Vault architecture and, from the same assertion layer, a scholarly article on it. The audience of the blog is the digital humanities practice that builds agentic knowledge systems, the audience of the article is digital humanities research together with the adjacent computer science. Every substantive statement either output makes about the architecture and about its real instances carries an anchor into the recorded evidence of those instances, meaning their journals, commit histories, validator runs and review reports, so that a reader can hold any claim about what the architecture did against the artifact that shows it. The construction is self-applying, because the texts about the build form are written with the build form, and this vault is therefore part of what it describes. A conclusion the vault cannot ground enters an output as a marked posit and stays visible as one.

## The two output tracks

The blog is written first and the article is derived from it, with one constraint that decides the architecture of this instance. A blog post never becomes a source of the article. Agent-produced output that re-entered the source layer would count as material from then on, which [[knowledge/schema]] forbids for the same reason it forbids treating a deep research report as a source. Both tracks therefore hang off the same assertion layer. The blog is the track in which sources are acquired, distilled and hardened into assertions, and the article is the second composition of that checked stock, re-sequenced for the scholarly genre and grounded in the same assertions.

A consequence for the working order is that an assertion passes machine review and human verification once and then carries both texts. Where the article needs a statement the blog never made, the missing work is source work, and it enters through the ordinary chain rather than through rewriting a post.

## Claims

The argument both outputs have to carry, as the list of claims. Each claim names the evidence that would carry it and the state of that evidence, where `recorded` means the material exists and awaits ingest into this vault, and `to be gathered` means it has to be produced or located first.

1. Provenance in model-assisted knowledge work can be enforced as a structural property of the artifact instead of being hoped for as a behavioural property of the model.
   - Evidence: the validator's finding catalogue together with runs over the real instances, showing that a missing or unresolvable anchor fails the artifact regardless of how the producing model behaved.
   - State: recorded in the template repository; the instance runs still have to enter as sources.
2. The error curve of the real migrations shows that the enforcement holds, and it shows no quality gain in the finished text, because the controlled comparison against an unanchored text was never run.
   - Evidence: validator error counts per run across the migrations, as a `data` source with a deterministic computation over the run log, plus the record that no control condition exists.
   - State: to be gathered. The run logs have to be assembled from the instances' histories into one dataset.
3. Full anchor depth cannot be produced retroactively once the sources were not archived at the time of distillation, so the build form is decided by the source situation at the outset.
   - Evidence: journal entries and commits of the instance that distilled from unarchived sources, showing which anchor depth remained unreachable afterwards and what was substituted for it.
   - State: recorded in the affected instance's journal; not yet ingested.
4. The separation of the producing instance from the reviewing instance is effective, and the human bottleneck at the top rung of the status ladder is left in place deliberately.
   - Evidence: verdict distributions of machine review runs over the instances for the effectiveness, and the dated decision record for the deliberateness of the bottleneck.
   - State: to be gathered for the verdict distributions; the decision itself is recorded in the architecture's own documents.
5. A body of knowledge that counts its unchecked places as unchecked is more usable scholarly than one that stays silent about them.
   - Evidence: the status distributions of the instances as a `data` source, and the surrounding literature on provenance and declared uncertainty as `publication` sources.
   - State: to be gathered. Without a publication anchor this claim carries only as far as the architecture's own reasoning and would enter an output as a posit.
6. An anchor guarantees traceability to a source; the correctness of that source is a separate question, and checking it is a separate act.
   - Evidence: the definitions of grounding, evidence and the three checking instances in the architecture's own schema and operations documents, taken as `document` sources.
   - State: recorded. The documents lie in the template repository and enter as ordinary sources.

## Parameters

| Parameter | Value |
|---|---|
| Controlled topic set | Provenance, Verification, Architecture, Agentic Workflow, Instances <!-- becomes the MOC set in 30_assertions/ --> |
| Active source types | document, publication, data |
| Output genre | two tracks off one assertion layer, research blog posts in `40_output/blog/` and a scholarly article in `40_output/paper/` |
| Chapter register | see [[knowledge/state]] |
| Working language of content | English for distillates, assertions, glossary and the article; German for the blog prose |
| Verification role | The authoring role, digital humanities research at the University of Graz and at Digital Humanities Craft |
| Validation mechanism | `tools/validate.py` |
| Machine review mechanism | `tools/review.py`, run with a reviewer model from a different model family than the producing agent |

## Style sheet

Both tracks are matter-of-fact prose without ornament. Four rules bind every output document regardless of language.

- No dash and no colon as a connector between clauses, for emphasis, or ahead of a summary. A colon stands only before a quotation, a code block or a list whose items sit on their own lines.
- No trailing negative apposition, meaning the patterns "X, not Y" and "not X, but Y". The point is stated positively, and an excluded alternative gets its own sentence.
- No triadic figures as a stylistic device and no parallelism for its own sake. An antithesis stands only where it carries content.
- No paragraph built towards an aphorism and no closing platitude, including the balanced both-sides closer.

The article is English scholarly prose. The blog is German prose with English technical terms, addressed to practitioners, and it may carry code listings and validator output where a post explains a mechanism.

Citations appear as footnotes in both tracks. A footnote that reports a source-supported statement reads `Grounded in [[30_assertions/<slug>]]` and carries the bibliographic reference in the same note where the assertion rests on a publication. A footnote that reports the vault's own conclusion reads `Posit: <rationale>. Open evidence question: <question>`. In the German blog the wikilink stays unaliased, so the English assertion title appears verbatim in the footnote and no alias drift can arise between text and anchor.

Terminology follows [[knowledge/index]] without variation, so that grounding, evidence, provenance chain, assertion and posit keep one meaning across both tracks. The German blog uses the English terms unchanged rather than translating them.

## Settled decisions

- 2026-08-10: Vault instantiated from the Grounded Vault template (DigitalHumanitiesCraft/grounded-vault).
- 2026-08-10: Two output tracks off one assertion layer, blog first, article derived; a blog post is never a source.
- 2026-08-10: All three source types active, with documents carrying the instance histories, publications the related literature and data the counts taken from validator runs.
- 2026-08-10: Distillates, assertions and the article in English, blog prose in German, with footnote wikilinks unaliased.
- 2026-08-10: Claims fixed ahead of the source work, each with the evidence that would carry it, taken over from the earlier paper vault.
