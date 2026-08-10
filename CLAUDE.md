# Grounded Vault Research Blog and Paper — Agent Action Layer

This vault is a Grounded Vault instance. Every substantive statement you produce here must carry a grounding anchor. This instance keeps no governance layer of its own; the rules are the invariant architecture and live in the template repository, locally at `../grounded-vault/knowledge/`, remotely at <https://github.com/DigitalHumanitiesCraft/grounded-vault>. Read them there and do not copy them into this repository.

## Session start

Read `../grounded-vault/knowledge/index.md` for the terminology, then the document your task routes to below.

## Task routing

Paths in the second column are relative to the template checkout.

| Task | Read first | Chain |
|---|---|---|
| Add a source | `knowledge/operations.md` § Acquire, Ingest | acquire → ingest |
| Distill a source | `knowledge/schema.md` § Distillate, `operations.md` § Distill | three-stage chain |
| Build or revise assertions | `knowledge/schema.md` § Assertion, `operations.md` § Build assertions | assertions |
| Write a blog post or an article chapter | `knowledge/schema.md` § Chapter, `operations.md` § Write chapters | chapters |
| Answer a question | `knowledge/operations.md` § Query | query |
| Check the vault | `knowledge/operations.md` § Check | validate → review |
| Record a run of this vault as data | `knowledge/schema.md` § Markdown representation (data), § Distillate | acquire → ingest → distill |

## Instance parameters

What the template leaves open, this instance decided.

- Controlled topic set: Provenance, Verification, Architecture, Agentic Workflow, Instances, one `MOC-<Topic>.md` each in `30_assertions/`.
- Active source types: document, publication, data. A data source carries its file and a schema description of the same slug in `10_markdown/data/`, and each of its statements is anchored to one script in `tools/analysis/` that takes no arguments, prints the stated result and nothing else, and is re-run by validation for a character-exact comparison.
- Licensing: the layers this project authors are CC BY 4.0, while every Markdown representation of a third-party work keeps the licence of that work in its metadata block. Before ingesting a source, check whether its licence permits an excerpted and anchored copy, and choose the publication type where it does not.
- Output in two tracks off one assertion layer, German blog posts in `40_output/blog/` and English article chapters in `40_output/paper/`. A blog post is never a source of the article; both tracks ground in the same assertions.
- Working language of content: English for distillates, assertions and glossary, German for the blog prose. This action layer stays English.
- Footnote wikilinks in the blog stay unaliased, so the English assertion title appears verbatim and no alias drift arises.
- Final texts of this instance (output prose, glossary, MOC leads) use no colons, no semicolons, and no dashes at all, beyond the operator's global style rules. Code, paths, and technical syntax are exempt.
- Verification role: the authoring role, digital humanities research at the University of Graz and at Digital Humanities Craft.
- Machine review: adversarial review under the template's review contract, executed by Claude Opus subagents (operator decision, 2026-08-10). This deviates from the template's cross-family recommendation and is a documented design decision of this instance; the shared-family risk is named in the output where the review is described. Anti-anchoring stays mandatory, the reviewer sees only the pair, never the producing agent's reasoning.

## Hard rules

- Anchors are minted only at their own layer; never invent a block or statement ID that does not exist.
- A converted Markdown representation is never edited after ingest, because its block anchors would move; a revised source enters as a new file with a date-suffixed slug. For a data source the anchor is a computation, so its data file may be corrected only where every anchored computation keeps its output character for character, and the correction is named in the commit.
- A status is set only after its check ran; record the date in `checked`. Never set `verified`; that is the human verification role's alone.
- Own conclusions become posits in the output, never assertions.
- Run `python tools/validate.py .` before reporting any production task as done. Zero errors alone is not the criterion; every warning is a finding to act on.
- Never write into `40_output/` from a source, and never let an output document enter `00_sources/`.

## Harness block (exchangeable)

This block is specific to Claude Code and may be replaced for another harness. The three skills `ingest-source`, `distill-source` and `build-assertions` live under `.claude/skills/` and route to the template's `knowledge/operations.md`, which stays the single place the rules are written down.

- Commit at milestones with concise English imperative messages; stage explicit paths.
- Run `python tools/validate.py .` and `python -m pytest tests` unasked; they only read.
- `python tools/inventory.py .` prints the source inventory. Its `--write` mode targets a governance register this instance does not keep, so do not run it with `--write`.
