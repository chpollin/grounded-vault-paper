---
title: State
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
related: [operations, journal]
---

# State

Everything volatile in one place, so the rule documents stay stable. Update rows here as work proceeds; never record processing state anywhere else.

## Source inventory

One row per source. Processing status: `new` → `ingested` → `distilled`. This section is generated from the real file state by `python tools/inventory.py . --write` and is never edited by hand; everything between the two markers is overwritten on each run.

<!-- inventory:begin -->
| Source | Type | Channel | Markdown representation | Distillate | Status |
|---|---|---|---|---|---|
<!-- inventory:end -->

## Chapter register

One row per chapter of the output, both tracks in one register. Writing status mirrors the chapter's frontmatter once the file exists; `planned` marks a chapter that has no file yet. The register holds the intended shape of blog and article, and nothing has been written.

### Blog track

| Chapter | File | Status | Notes |
|---|---|---|---|
| 1. Das Problem | `40_output/blog/01-unauditable-output.md` | planned | Warum generierter Text in seiner Rohform nicht prüfbar ist und warum nachgereichte Zitate daran nichts ändern. Trägt Claim 1. |
| 2. Die Kette | `40_output/blog/02-layer-chain.md` | planned | Das Schichtenmodell und die beiden Regeln, die es zusammenhalten. Trägt Claim 1. |
| 3. Anker pro Quelltyp | `40_output/blog/03-anchors.md` | planned | Blockreferenz, wörtliches Zitat, deterministische Berechnung, und wofür die Quelltypologie entscheidet. Trägt Claim 3. |
| 4. Drei Prüfinstanzen | `40_output/blog/04-checking.md` | planned | Validierung, Machine Review, Verifikation, und die Statusleiter als Ehrlichkeitsmechanik. Trägt Claim 4. |
| 5. Was der Validator findet | `40_output/blog/05-findings.md` | planned | Der Findungskatalog an echten Läufen gelesen. Trägt Claims 2 und 5. |
| 6. Feldbericht | `40_output/blog/06-field-report.md` | planned | Was die realen Instanzen im Betrieb gezeigt haben, einschließlich der Werkzeuglücken. Trägt Claims 2 und 4. |
| 7. Grenzen | `40_output/blog/07-limits.md` | planned | Fehlender kontrollierter Vergleich, menschlicher Engpass, Reichweite eines Ankers. Trägt Claim 6. |

### Article track

| Chapter | File | Status | Notes |
|---|---|---|---|
| 1. Introduction | `40_output/paper/01-introduction.md` | planned | The problem of unauditable model output and the claim that provenance is enforceable structurally. Carries claim 1. |
| 2. Related work | `40_output/paper/02-related-work.md` | planned | Provenance models, scholarly editing practice, retrieval-augmented generation and agentic knowledge systems. Rests on the `publication` sources. |
| 3. Architecture | `40_output/paper/03-architecture.md` | planned | The layer chain, the anchor mechanics per source type, the three checking instances and the status ladder. Carries claims 4 and 6. |
| 4. The instances | `40_output/paper/04-instances.md` | planned | Case description of the real instances, their source situations and their migrations. Carries claim 3. |
| 5. Findings | `40_output/paper/05-findings.md` | planned | What the migrations and the review runs show, read off the `data` sources. Carries claims 2 and 5. |
| 6. Limitations | `40_output/paper/06-limitations.md` | planned | The missing controlled comparison, the human bottleneck, the retroactivity limit and the scope of what an anchor guarantees. Restates the negative half of claims 2, 4 and 6. |
| 7. Conclusion | `40_output/paper/07-conclusion.md` | planned | What the architecture settles and what it leaves open. |

## Open work

<!-- Short, current list; done items are deleted, decisions go to the journal. -->

- Acquire the histories of the real instances as `document` sources, meaning journals, commit logs and check reports.
- Assemble the validator run counts of the migrations into one `data` source with a deterministic computation over it.
- Locate the related literature for the article's chapter 2 and export it as CSL JSON into `references/`.
- Decide per claim whether it reaches an assertion or has to enter an output as a posit, once the sources are distilled.
