---
name: squidpy-build-and-install
description: Use this skill for Squidpy environment setup, installation, dependency compatibility checks, and local validation commands for tests or docs builds.
---

# squidpy: Build and Install

## Route conditions
- Use this skill for package install mode selection, environment bootstrapping, dependency mismatches, and test/docs command failures.
- Route API behavior design questions to `squidpy-api-and-scripting`.
- Route version-to-version behavior changes to `squidpy-release`.
- Route bibliography/references/spelling list tasks to `squidpy-advanced-topics`.

## Setup playbook
1. Confirm Python requirement (`>=3.11`) and package manager (`hatch`, `uv`, or `pip`).
2. Install Squidpy in the chosen environment.
3. Run a simulation smoke check (dataset -> graph) in the same environment.
4. Run local quality gates (`pre-commit`, tests, docs build).

## Canonical commands
```bash
# user install smoke check
python -m venv .venv
source .venv/bin/activate
pip install squidpy
python -c "import squidpy as sq; print(sq.__version__)"
```

```bash
# contributor path (hatch)
hatch test
pre-commit install
hatch run docs:build
```

```bash
# contributor path (uv)
uv sync --all-extras
uv run pytest
uv run sphinx-build -M html docs docs/_build -W
```

## Simulation readiness check
```bash
python - <<'PY'
import squidpy as sq
adata = sq.datasets.visium_hne_adata_crop()
sq.gr.spatial_neighbors(adata)
print("ok", adata.obsp["spatial_connectivities"].shape)
PY
```

## Validation checkpoints
- `import squidpy` succeeds in the target environment.
- `sq.__version__` resolves without metadata/import errors.
- Neighbor graph build works on a bundled dataset (`spatial_connectivities` exists).
- `hatch test` or `uv run pytest` passes in the active environment.
- Docs build runs with warnings treated as errors.

## Primary documentation references
- `docs/installation.md`
- `docs/contributing.md`
- `docs/index.md`

## Workflow
1. Start from `docs/installation.md` for install mode and Python floor.
2. Use `docs/contributing.md` for hatch/uv/pip test and docs commands.
3. If docs are insufficient, inspect `references/doc_map.md`.
4. Use `references/source_map.md` for function-level compatibility checks tied to real tests.
