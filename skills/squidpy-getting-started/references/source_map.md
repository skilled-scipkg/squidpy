# squidpy source map: Getting Started

Generated from source roots:
- `src`

Use this map only after exhausting the topic docs in `doc_map.md`.

## Fast source navigation
- `rg -n "<symbol_or_keyword>" src`
- `rg -n "^(def|class) " src/squidpy/{datasets,read,gr,pl}`

## Suggested source entry points
- `src/squidpy/__init__.py` | startup metadata: `__version__`, exported modules | behavior checks: import smoke in quickstart command
- `src/squidpy/datasets/__init__.py` | exported dataset loaders: `visium_hne_adata_crop`, `visium_hne_adata`, `visium` | behavior checks: `tests/datasets/test_dataset.py`
- `src/squidpy/read/_read.py` | reader entry functions: `visium`, `vizgen`, `nanostring` | behavior checks: `tests/read/test_visium.py`
- `src/squidpy/gr/_build.py` | graph entry function: `spatial_neighbors` | behavior checks: `tests/graph/test_spatial_neighbors.py`
- `src/squidpy/gr/_nhood.py` | first analysis entry function: `nhood_enrichment` | behavior checks: `tests/graph/test_nhood.py`
- `src/squidpy/pl/_spatial.py` | first plotting entry function: `spatial_scatter` | behavior checks: `tests/plotting/test_spatial_static.py`
