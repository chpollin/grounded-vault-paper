# Grounded Vault Research Blog and Paper — Agent Action Layer

This vault is a Grounded Vault instance. Every substantive statement you produce here must carry a grounding anchor; the rules live in `knowledge/`, and this file only routes you there. Do not duplicate rules here.

## Session start

Read in this order: `knowledge/index.md` (terminology), `knowledge/state.md` (where work stands), then the document your task routes to below.

## Task routing

| Task | Read first | Chain |
|---|---|---|
| Add a source | `knowledge/operations.md` § Acquire, Ingest | acquire → ingest |
| Distill a source | `knowledge/schema.md` § Distillate, `operations.md` § Distill | three-stage chain |
| Build or revise assertions | `schema.md` § Assertion, `operations.md` § Build assertions | assertions |
| Write a blog post or an article chapter | `schema.md` § Chapter, `operations.md` § Write chapters, `specification.md` § The two output tracks | chapters |
| Answer a question | `operations.md` § Query | query |
| Check the vault | `operations.md` § Check | validate → review |

## Hard rules

- Anchors are minted only at their own layer; never invent a block or statement ID that does not exist.
- A Markdown representation is never edited after ingest; a revised source enters as a new file with a date-suffixed slug.
- A status is set only after its check ran; record the date in `checked`. Never set `verified`; that is the human verification role's alone.
- Own conclusions become posits in the output, never assertions.
- Run `python tools/validate.py .` before reporting any production task as done. Zero errors alone is not the criterion; every warning is a finding to act on.
- Volatile state goes to `knowledge/state.md`, decisions to `knowledge/journal.md` (append-only).
- Working language of content: English for distillates, assertions, glossary and the article; German for the blog prose in `40_output/blog/`. This action layer and `knowledge/` stay English.

## Harness block (exchangeable)

This block is specific to Claude Code and may be replaced for another harness. For Claude Code the three skills `ingest-source`, `distill-source` and `build-assertions` live under `.claude/skills/` and route to the corresponding sections of `knowledge/operations.md`, which stays the single place the rules are written down.

- Commit at milestones with concise English imperative messages; stage explicit paths.
- Run `python tools/validate.py .`, `python tools/inventory.py . --write` and `python -m pytest tests` unasked; they only read or regenerate generated blocks.
- Never write into `40_output/` from a source, and never let an output document enter `00_sources/`; the two tracks compose the assertion layer and nothing else.
