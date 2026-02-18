# squidpy source map: API and Scripting

Generated from source roots:
- `src`

Use this map only after exhausting the topic docs in `doc_map.md`.

## Fast source navigation
- `rg -n "<symbol_or_keyword>" src/squidpy`
- `rg -n "^(def|class) " src/squidpy/{read,gr,pl,im,tl,datasets}`

## Suggested source entry points
- `src/squidpy/read/_read.py` | reader functions: `visium`, `vizgen`, `nanostring` | behavior checks: `tests/read/test_visium.py`
- `src/squidpy/datasets/__init__.py` | public dataset entry points used in examples | behavior checks: `tests/datasets/test_dataset.py`
- `src/squidpy/gr/_build.py` | graph build functions: `spatial_neighbors`, `mask_graph` | behavior checks: `tests/graph/test_spatial_neighbors.py`
- `src/squidpy/gr/_nhood.py` | neighborhood functions: `nhood_enrichment`, `centrality_scores`, `interaction_matrix` | behavior checks: `tests/graph/test_nhood.py`
- `src/squidpy/pl/_spatial.py` | spatial plotting functions: `spatial_scatter`, `spatial_segment` | behavior checks: `tests/plotting/test_spatial_static.py`
- `src/squidpy/pl/_graph.py` | graph plotting functions: `nhood_enrichment`, `interaction_matrix`, `centrality_scores` | behavior checks: `tests/plotting/test_graph.py`
- `src/squidpy/im/_container.py` | image container behavior: `ImageContainer.from_adata`, `ImageContainer.generate_spot_crops`, `ImageContainer.show` | behavior checks: `tests/image/test_container.py`
- `src/squidpy/im/_process.py` | image processing function: `process` | behavior checks: `tests/image/test_processing.py`
- `src/squidpy/im/_segment.py` | segmentation classes/functions: `SegmentationWatershed`, `SegmentationCustom`, `segment` | behavior checks: `tests/image/test_segmentation.py`
- `src/squidpy/tl/_sliding_window.py` | tool function: `sliding_window` | behavior checks: `tests/tools/test_sliding_window.py`
- `src/squidpy/tl/_var_by_distance.py` | tool function: `var_by_distance` | behavior checks: `tests/tools/test_var_by_distance.py`
- `src/squidpy/pl/_var_by_distance.py` | plot function: `var_by_distance` | behavior checks: `tests/plotting/test_var_by_distance_plot.py`

## Focused validation commands
- `pytest -q tests/read/test_visium.py tests/graph/test_spatial_neighbors.py tests/graph/test_nhood.py`
- `pytest -q tests/plotting/test_spatial_static.py tests/plotting/test_graph.py`
- `pytest -q tests/image/test_container.py tests/image/test_processing.py tests/image/test_segmentation.py`
- `pytest -q tests/tools/test_sliding_window.py tests/tools/test_var_by_distance.py`
