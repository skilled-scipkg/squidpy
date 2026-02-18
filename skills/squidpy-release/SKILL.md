---
name: squidpy-release
description: Use this skill for Squidpy upgrade planning, release-note interpretation, and regression triage across specific version windows.
---

# squidpy: Release

## Route conditions
- Use this skill for migration planning (`from -> to`), post-upgrade regressions, and mapping behavior to release notes.
- Route environment setup failures to `squidpy-build-and-install`.
- Route pure API design and usage questions to `squidpy-api-and-scripting` after version scope is clear.
- Route bibliography/references/spelling list tasks to `squidpy-advanced-topics`.

## Upgrade triage playbook
1. Capture current and target versions.
2. Start from `docs/release_notes.md`, then inspect note files for that version window via `references/doc_map.md`.
3. Map each relevant note item to code/test entry points in `references/source_map.md`.
4. Reproduce with a minimal simulation smoke run on the target environment.

## Minimal migration smoke run
```bash
python - <<'PY'
import squidpy as sq

print("version", sq.__version__)
adata = sq.datasets.visium_hne_adata_crop()
sq.gr.spatial_neighbors(adata)
sq.gr.nhood_enrichment(adata, cluster_key="cluster")
print("graph", "spatial_connectivities" in adata.obsp)
print("nhood", "cluster_nhood_enrichment" in adata.uns)
PY
```

## Focused regression checks
```bash
pytest -q tests/read/test_visium.py tests/graph/test_spatial_neighbors.py tests/graph/test_nhood.py
pytest -q tests/tools/test_sliding_window.py tests/tools/test_var_by_distance.py tests/plotting/test_var_by_distance_plot.py
```

## Validation checkpoints
- Installed `sq.__version__` matches the intended note window.
- Release-note claims map to concrete code paths and passing tests.
- Reader -> graph -> analysis workflow runs on target version.
- Workarounds are tied to a specific note file and code path.

## Primary documentation references
- `docs/release_notes.md`
- `docs/release/`
- `docs/index.md`

## Workflow
1. Start from `docs/release_notes.md` to locate note files.
2. Narrow to note files relevant to the requested version interval.
3. Use `references/source_map.md` for function-level confirmation and tests.
4. Cite exact note file paths in the response.
