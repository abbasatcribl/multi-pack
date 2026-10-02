# Multi-pack Git dependency fixture

This repository contains two independent Cribl packs for testing CRIBL-45838. Each pack has its own `package.json` and pipeline. The repository root intentionally has no package manifest.

| Pack | Package directory | Git dependency source |
| --- | --- | --- |
| Alpha | `packs/pack-alpha` | `git+ssh://git@github.com/abbasatcribl/multi-pack.git#path=packs/pack-alpha` |
| Bravo | `packs/pack-bravo` | `git+ssh://git@github.com/abbasatcribl/multi-pack.git#path=packs/pack-bravo` |

Use `main` as the branch spec. For HTTPS testing, replace the source before `#path=` with `git+https://github.com/abbasatcribl/multi-pack.git`.

After installation, Alpha should contain only `alpha_marker`, while Bravo should contain only `bravo_marker`. Installing the repository URL without `#path=` should fail because the root has no `package.json`.
