# Grounded Vault Research Blog and Paper

Human entry point of this vault. This vault produces a research blog on the Grounded Vault architecture and, from the same assertion layer, a scholarly article on it. Every load-bearing statement here is anchored to its source material, and the checking state of every statement is readable at the statement itself.

## The chain

```
00_sources → 10_markdown → 20_distillates → 30_assertions → 40_output
```

`00_sources/` holds the originals as they arrived and stays unchecked, because it is the material every layer above it is checked against. `10_markdown/` holds the Markdown representations with their block anchors, and every anchor above binds downward from there.

## Read the output

Two tracks rest on the same assertion layer. The blog is written first, the article is composed from the same checked stock; a blog post is never a source of the article.

- [[40_output/blog/]] — the research blog, German prose.
- [[40_output/paper/]] — the scholarly article, English prose.

Footnotes in both lead to assertions; click through to the supporting passages.

## Explore the knowledge

- [[30_assertions/MOC-Provenance]] — anchors, chains and what they guarantee.
- [[30_assertions/MOC-Verification]] — the three checking instances and the status ladder.
- [[30_assertions/MOC-Architecture]] — layers, source types and document schema.
- [[30_assertions/MOC-Agentic-Workflow]] — how agents produce and check the structure.
- [[30_assertions/MOC-Instances]] — what the real instances did and showed.
- [[glossary/]] — the project's terms.

## Understand the machine room

- `CLAUDE.md` — the instance parameters and the hard rules.
- The template repository <https://github.com/DigitalHumanitiesCraft/grounded-vault> — the architecture, its schema and its procedures. This instance keeps no governance layer of its own.

## How to read a status

`grounded` means an agent produced the anchor structure. `validated` means deterministic checks and an adversarial machine review passed. `verified` means the human expert confirmed it; only this is evidence. `contested` means sources conflict, which is itself information.
