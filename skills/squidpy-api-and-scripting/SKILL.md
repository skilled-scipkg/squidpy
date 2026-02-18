---
name: squidpy-api-and-scripting
description: Use this skill for Squidpy API usage, scripting workflows, and function-level behavior checks across readers, graph analysis, plotting, image processing, and tools.
---

# squidpy: API and Scripting

## Route conditions
- Use this skill for programmatic workflows across `sq.read`, `sq.datasets`, `sq.gr`, `sq.tl`, `sq.pl`, and `sq.im`.
- Route environment/install failures to `squidpy-build-and-install`.
- Route upgrade-window or regression questions to `squidpy-release`.
- Route bibliography/references/spelling list questions to `squidpy-advanced-topics`.

## Minimal simulation workflow
```bash
python - <<'PY'
import squidpy as sq

adata = sq.datasets.visium_hne_adata_crop()
sq.gr.spatial_neighbors(adata)
sq.gr.nhood_enrichment(adata, cluster_key="cluster")
sq.pl.spatial_scatter(adata, color="cluster", na_color="lightgrey")

print("graph_keys", [k for k in adata.obsp.keys() if "spatial" in k])
print("nhood_key", "cluster_nhood_enrichment" in adata.uns)
PY
```

## Reader input smoke examples
```bash
python - <<'PY'
from squidpy.read import visium

adata = visium("tests/_data", load_images=True)
print("spatial_uns", "spatial" in adata.uns)
print("spatial_obsm", "spatial" in adata.obsm)
PY
```

## Triage checklist
- Confirm data source and reader path (`visium`, `vizgen`, `nanostring`, or dataset loaders).
- Confirm spatial coordinates exist (`adata.obsm["spatial"]`).
- Confirm graph exists before graph-dependent analytics (`spatial_connectivities` in `adata.obsp`).
- Confirm required categorical key exists for neighborhood/interaction methods.
- For multi-library plots, set `library_key` and `library_id` explicitly.

## Validation checkpoints
- `sq.gr.spatial_neighbors` writes connectivities/distances keys to `adata.obsp`.
- `sq.gr.nhood_enrichment` writes the expected key to `adata.uns`.
- Plotting calls complete without key/type errors (`sq.pl.spatial_scatter`, `sq.pl.nhood_enrichment`).
- Reader output includes both `adata.uns["spatial"]` and `adata.obsm["spatial"]`.

## Primary documentation references
- `docs/api.md`
- `docs/classes.md`
- `docs/_templates/autosummary/class.rst`

## Workflow
1. Start from the API docs above for signature-level guidance.
2. Reproduce with the minimal simulation workflow.
3. If docs are insufficient, inspect `references/doc_map.md`.
4. For behavior-level ambiguities, use `references/source_map.md` and run the paired test files.
