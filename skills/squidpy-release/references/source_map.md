# squidpy source map: Release

Generated from source roots:
- `src`

Use this map only after exhausting the topic docs in `doc_map.md`.

## Fast source navigation
- `rg -n "sliding_window|var_by_distance|spatial_neighbors|visium|interactive" src/squidpy`
- `rg -n "^# Squidpy" docs/release/notes-*.md`

## Suggested source entry points
- `src/squidpy/__init__.py` | version metadata path (`__version__`) for release-window confirmation
- `pyproject.toml` | dependency and Python-floor changes referenced by release notes
- `src/squidpy/tl/_sliding_window.py` | release item in 1.6.2: `sliding_window` | behavior checks: `tests/tools/test_sliding_window.py`
- `src/squidpy/tl/_var_by_distance.py` | release items from 1.3.x and dev: `var_by_distance` behavior | behavior checks: `tests/tools/test_var_by_distance.py`
- `src/squidpy/pl/_var_by_distance.py` | release item in 1.6.1: plotting updates | behavior checks: `tests/plotting/test_var_by_distance_plot.py`
- `src/squidpy/read/_read.py` | reader fixes across releases: `visium`, `vizgen`, `nanostring` | behavior checks: `tests/read/test_visium.py`
- `src/squidpy/gr/_build.py` | graph changes across releases: `spatial_neighbors` | behavior checks: `tests/graph/test_spatial_neighbors.py`
- `src/squidpy/gr/_nhood.py` | neighborhood enrichment behavior changes: `nhood_enrichment` | behavior checks: `tests/graph/test_nhood.py`
- `src/squidpy/_compat.py` | compatibility shims for scanpy/anndata API moves

## Focused validation commands
- `python -c "import squidpy as sq; print(sq.__version__)"`
- `pytest -q tests/read/test_visium.py tests/graph/test_spatial_neighbors.py tests/graph/test_nhood.py`
- `pytest -q tests/tools/test_sliding_window.py tests/tools/test_var_by_distance.py tests/plotting/test_var_by_distance_plot.py`
