---
name: squidpy-getting-started
description: Use this skill for first-run Squidpy onboarding, quick simulation startup, and core concept orientation before diving into deeper API or release-specific debugging.
---

# squidpy: Getting Started

## Route conditions
- Use this skill for first execution, quick orientation, and "how do I start" requests.
- Route install or dependency failures to `squidpy-build-and-install`.
- Route deep API behavior questions to `squidpy-api-and-scripting`.
- Route version-difference and migration questions to `squidpy-release`.

## Quick simulation startup
```bash
python - <<'PY'
import squidpy as sq

adata = sq.datasets.visium_hne_adata_crop()
sq.gr.spatial_neighbors(adata)
sq.gr.nhood_enrichment(adata, cluster_key="cluster")

print("version", sq.__version__)
print("n_obs", adata.n_obs)
print("has_spatial", "spatial" in adata.obsm)
print("has_graph", "spatial_connectivities" in adata.obsp)
print("has_nhood", "cluster_nhood_enrichment" in adata.uns)
PY
```

## Reader input smoke check
```bash
python - <<'PY'
from squidpy.read import visium

adata = visium("tests/_data", load_images=True)
print("spatial_uns", "spatial" in adata.uns)
print("spatial_obsm", "spatial" in adata.obsm)
PY
```

## Validation checkpoints
- Dataset load succeeds and returns non-empty `AnnData`.
- `sq.gr.spatial_neighbors` writes `spatial_connectivities` and `spatial_distances` to `adata.obsp`.
- `sq.gr.nhood_enrichment` writes `cluster_nhood_enrichment` to `adata.uns`.
- Reader outputs contain both `adata.uns["spatial"]` and `adata.obsm["spatial"]`.

## Primary documentation references
- `docs/index.md`
- `docs/installation.md`
- `docs/api.md`

## Workflow
1. Start from `docs/index.md` for terminology and module orientation.
2. Confirm runnable baseline from the quick simulation startup block above.
3. If docs are insufficient, open `references/doc_map.md`.
4. If behavior remains unclear, inspect `references/source_map.md` for function-level code and matching tests.
