---
name: squidpy-index
description: Route Squidpy requests to the correct generated topic skill and provide a minimal startup path when the user needs to begin a real simulation workflow.
---

# squidpy Skills Index

## Route the request
- Use `squidpy-getting-started` for first-run workflows, quick simulation bootstraps, and high-level orientation.
- Use `squidpy-build-and-install` for environment setup, dependency issues, test/docs execution, and packaging checks.
- Use `squidpy-api-and-scripting` for reader/graph/plot/image/tool API behavior and scripting workflows.
- Use `squidpy-release` for upgrade windows, behavior regressions across versions, and release-note interpretation.
- Use `squidpy-advanced-topics` for release-note index routing, bibliography references, and spelling-wordlist maintenance.

## Fast start when user is unsure
```bash
python - <<'PY'
import squidpy as sq
adata = sq.datasets.visium_hne_adata_crop()
sq.gr.spatial_neighbors(adata)
print("version", sq.__version__)
print("n_obs", adata.n_obs)
print("has_graph", "spatial_connectivities" in adata.obsp)
PY
```

## Routing workflow
1. Open `references/doc_map.md` for top-level docs and topic boundaries.
2. Select one topic skill and follow its `SKILL.md` playbook.
3. If docs are insufficient, use that topic skill's `references/source_map.md` for function-level code/test entry points.
4. Keep path-cited responses and include concrete validation checkpoints.
