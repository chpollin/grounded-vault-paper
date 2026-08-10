---
title: Journal
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
related: [specification, state]
---

# Journal

Chronological decision history of the vault, append-only, newest entry last. Content documents carry only current state; the reasoning that led there lives here. An entry records a decision, a rejected alternative with the reason, or a calibration result of a check mechanism.

## Entry format

```markdown
## 2026-08-10 — <one-line subject>

<What was decided or found, why, and what it replaces. Link the affected
documents. Two to ten sentences.>
```

## 2026-08-10 — Vault instantiated

Instantiated from the Grounded Vault template (DigitalHumanitiesCraft/grounded-vault) into a repository of its own. Parameters recorded in [[knowledge/specification]]. The earlier attempt placed the paper vault in a `paper/` subdirectory of the template repository, where it duplicated `knowledge/` and `tools/` and would have drifted against the template; that state remains recoverable at commit `9fb8748` of the template. This instance therefore carries its own copies of the tooling and is validated on its own.

The template's `tools/build_docs.py` was left out, because it generates the template's project page from `README.md` and `docs/concept.md`, neither of which this instance holds. The remaining tools, `validate.py`, `inventory.py`, `review.py` and `migrate.py`, are the ones the test suite runs against, so `tests/` stays complete and green.

## 2026-08-10 — Two output tracks off one assertion layer

The blog is written first and the article is derived from it, and the derivation runs through the assertion layer rather than through the blog text. Treating a post as a source of the article would put agent-produced output into the source layer, which [[knowledge/schema]] rules out for the same reason it rules out a deep research report as a source. Both tracks therefore ground in the same assertions, `40_output/blog/` in German and `40_output/paper/` in English, and an assertion passes review and verification once for both. The alternative, a second vault whose sources are the blog posts, was rejected on that ground and because it would have doubled the checking work.

## 2026-08-10 — Two languages over one assertion layer

Distillates, assertions, the glossary and the article are English, the blog prose is German. The blog addresses the German-speaking practice, while the article and the source material are English, and translating the assertion layer for the blog would create a second wording of every statement that no check compares against the first. The cost is that a German sentence footnotes an English assertion title. Footnote wikilinks in the blog therefore stay unaliased, so the assertion title appears verbatim and `W-ALIAS` keeps its meaning; a German rendering of a title belongs in the running text.

## 2026-08-10 — Claims taken over from the earlier paper vault

The six claims, their evidence and its state were carried over unchanged from the instantiation at template commit `9fb8748`, together with the style sheet. Fixing the argument ahead of the source work keeps the acquisition directed, because a source enters for a named claim, and it keeps visible which claims currently have no source. Claim 2 carries its own negative finding, that the migration data shows enforceability while no controlled comparison exists that could show a quality gain in the finished text, and that limit stays in the claim rather than being softened during writing.
