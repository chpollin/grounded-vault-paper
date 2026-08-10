# Grounded Vault Research Blog and Paper

A [Grounded Vault](https://github.com/DigitalHumanitiesCraft/grounded-vault) instance that produces a research blog on the Grounded Vault architecture and, from the same assertion layer, a scholarly article on it. Every substantive statement in either output carries a machine-resolvable anchor down to the material that supports it.

The construction is self-applying. The texts about the build form are written with the build form, so this repository is both the argument and its own case.

## Entry points

- `HOME.md` for human readers, best opened as an Obsidian vault.
- `CLAUDE.md` for agents; it routes into the rule documents and duplicates none of them.
- `knowledge/specification.md` for what this instance decided, including the claim list and the two output tracks.

## Quickstart

```
uv sync                        # or: pip install pyyaml pytest
python tools/validate.py .     # conformance check of the whole vault
python tools/inventory.py . --write   # regenerate the source inventory in knowledge/state.md
python -m pytest tests         # the validator's own test suite
```

A run without errors is not the whole criterion. Every warning is a finding, and a fresh instance carries `W-NO-OUTPUT` until the first chapter exists.

## Licence

Creative Commons Attribution 4.0 International (CC BY 4.0), see [LICENSE](LICENSE). Third-party research data is excluded; rights remain with their respective holders.
