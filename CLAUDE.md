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

## Instance parameters

What the template leaves open, this instance decided.

- Controlled topic set: Provenance, Verification, Architecture, Agentic Workflow, Instances, one `MOC-<Topic>.md` each in `30_assertions/`.
- Active source types: document, publication, data.
- Output in two tracks off one assertion layer, German blog posts in `40_output/blog/` and English article chapters in `40_output/paper/`. A blog post is never a source of the article; both tracks ground in the same assertions.
- Working language of content: English for distillates, assertions and glossary, German for the blog prose. This action layer stays English.
- Footnote wikilinks in the blog stay unaliased, so the English assertion title appears verbatim and no alias drift arises.
- Verification role: the authoring role, digital humanities research at the University of Graz and at Digital Humanities Craft.
- Machine review: `tools/review.py` with a reviewer model from a different model family than the producing agent.

## Hard rules

- Anchors are minted only at their own layer; never invent a block or statement ID that does not exist.
- A Markdown representation is never edited after ingest; a revised source enters as a new file with a date-suffixed slug.
- A status is set only after its check ran; record the date in `checked`. Never set `verified`; that is the human verification role's alone.
- Own conclusions become posits in the output, never assertions.
- Run `python tools/validate.py .` before reporting any production task as done. Zero errors alone is not the criterion; every warning is a finding to act on.
- Never write into `40_output/` from a source, and never let an output document enter `00_sources/`.

## Harness block (exchangeable)

This block is specific to Claude Code and may be replaced for another harness. The three skills `ingest-source`, `distill-source` and `build-assertions` live under `.claude/skills/` and route to the template's `knowledge/operations.md`, which stays the single place the rules are written down.

- Commit at milestones with concise English imperative messages; stage explicit paths.
- Run `python tools/validate.py .` and `python -m pytest tests` unasked; they only read.
- `python tools/inventory.py .` prints the source inventory. Its `--write` mode targets a governance register this instance does not keep, so do not run it with `--write`.
