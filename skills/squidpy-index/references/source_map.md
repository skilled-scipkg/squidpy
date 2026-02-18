# squidpy source map: Index

Generated from source roots:
- `src`

Use this map only when a request spans multiple topic skills.

## Fast source navigation
- `rg -n "<symbol_or_keyword>" src`
- `rg -n "^(def|class) " src/squidpy`

## Cross-topic source entry points
- `src/squidpy/read/_read.py` | entry functions: `visium`, `vizgen`, `nanostring` | route: `squidpy-api-and-scripting` | behavior checks: `tests/read/test_visium.py`
- `src/squidpy/gr/_build.py` | entry function: `spatial_neighbors` | route: `squidpy-api-and-scripting` and `squidpy-release` | behavior checks: `tests/graph/test_spatial_neighbors.py`
- `src/squidpy/gr/_nhood.py` | entry functions: `nhood_enrichment`, `centrality_scores`, `interaction_matrix` | route: `squidpy-api-and-scripting` and `squidpy-release` | behavior checks: `tests/graph/test_nhood.py`
- `src/squidpy/pl/_spatial.py` | entry functions: `spatial_scatter`, `spatial_segment` | route: `squidpy-api-and-scripting` | behavior checks: `tests/plotting/test_spatial_static.py`
- `src/squidpy/im/_process.py` | entry function: `process` | route: `squidpy-api-and-scripting` and `squidpy-build-and-install` | behavior checks: `tests/image/test_processing.py`
- `src/squidpy/im/_segment.py` | entry classes/functions: `SegmentationWatershed`, `SegmentationCustom`, `segment` | route: `squidpy-api-and-scripting` and `squidpy-build-and-install` | behavior checks: `tests/image/test_segmentation.py`
- `src/squidpy/tl/_sliding_window.py` | entry function: `sliding_window` | route: `squidpy-api-and-scripting` and `squidpy-release` | behavior checks: `tests/tools/test_sliding_window.py`
- `src/squidpy/tl/_var_by_distance.py` | entry function: `var_by_distance` | route: `squidpy-api-and-scripting` and `squidpy-release` | behavior checks: `tests/tools/test_var_by_distance.py`
- `src/squidpy/pl/_var_by_distance.py` | entry function: `var_by_distance` | route: `squidpy-api-and-scripting` and `squidpy-release` | behavior checks: `tests/plotting/test_var_by_distance_plot.py`
- `pyproject.toml` | entry fields: `requires-python`, optional dependencies, hatch scripts | route: `squidpy-build-and-install` and `squidpy-release`
- `src/squidpy/__init__.py` | entry variables: `__version__`, exported modules | route: `squidpy-release` and `squidpy-advanced-topics`
- `src/squidpy/_docs.py` | entry function: `inject_docs` | route: `squidpy-advanced-topics`
