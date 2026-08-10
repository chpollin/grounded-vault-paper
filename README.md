# Grounded Vault Research Blog and Paper

A [Grounded Vault](https://github.com/DigitalHumanitiesCraft/grounded-vault) instance that produces a research blog on the Grounded Vault architecture and, from the same assertion layer, a scholarly article on it. Every substantive statement in either output carries a machine-resolvable anchor down to the material that supports it.

The construction is self-applying. The texts about the build form are written with the build form, so this repository is both the argument and its own case.

## Entry points

- `HOME.md` for human readers, best opened as an Obsidian vault.
- `CLAUDE.md` for agents; it routes into the rule documents and duplicates none of them.
- The template repository <https://github.com/DigitalHumanitiesCraft/grounded-vault> for the architecture, its schema and its procedures; this instance keeps no governance layer of its own.

## Quickstart

```
uv sync                        # or: pip install pyyaml pytest
python tools/validate.py .     # conformance check of the whole vault
python tools/inventory.py .    # print the source inventory
python -m pytest tests         # the validator's own test suite
```

A run without errors is not the whole criterion. Every warning is a finding, and a fresh instance carries `W-EMPTY` and `W-NO-OUTPUT` until the first source and the first chapter exist.

Note that `validate.py` executes the analysis scripts in `tools/analysis/`, because a statement about a data source is anchored to a computation and the check re-runs that computation and compares its output character for character. Read those scripts before running the validator on a vault you did not write.

## Licence

The layers this project authors are licensed under Creative Commons Attribution 4.0 International (CC BY 4.0), see [LICENSE](LICENSE). This covers `20_distillates/`, `30_assertions/`, `40_output/`, `glossary/`, `tools/`, the datasets in `10_markdown/data/` and the documentation in the repository root.

The Markdown representations in `10_markdown/documents/` are derived from third-party works and each keeps the licence of the work it represents, recorded in the `license` field of its metadata block. The repository licence does not extend to them, and the terms below govern reuse.

| Licence of the represented work | Representations |
|---|---|
| CC BY 4.0 | Gao et al. 2023, Liu et al. 2023, Liu et al. 2024, Walters and Wilder 2023, Peters and Chin-Yee 2025, Panickssery et al. 2024, Schmidt 2018, the Promptotyping specification, the Grounded Vault template |
| CC BY-NC 4.0 | Magesh et al. 2025. The non-commercial condition of the source applies and is not lifted by the repository licence. |
| CC BY 3.0 or BSD-2-Clause | TEI P5 Guidelines, chapter Critical Apparatus |
| Open Government Licence v3.0 | The National Archives guidance note, DPC Digital Preservation Handbook chapter |
| Public domain | Library of Congress Recommended Formats Statement, as a work of the U.S. Government |
| W3C Document License | PROV-DM and PROV-CONSTRAINTS. See the note below. |

Two cases need naming rather than a table row. The representations of the two W3C Recommendations are excerpts carrying added block identifiers, which makes them modified copies, and the W3C document use rules grant no permission for modified copies. They are held here as scholarly excerpts for citation, and anyone redistributing them should work from the W3C originals instead. The chapter of the operator's dissertation is the operator's own work and is released here under CC BY 4.0 by the author.

Original files in `00_sources/` are not versioned, because some of them may neither be redistributed nor made public.
