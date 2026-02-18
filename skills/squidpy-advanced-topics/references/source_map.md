# squidpy source map: Advanced Topics

Generated from source roots:
- `src`

Use this map only after exhausting the topic docs in `doc_map.md`.

## Topic query tokens
- `release`
- `notes`
- `references`
- `bibliography`
- `spelling`
- `wordlist`

## Fast source navigation
- `rg -n "inject_docs|__version__|var_by_distance|spatial_neighbors|visium" src/squidpy`
- `rg -n "^# Squidpy" docs/release/notes-*.md`

## Suggested source entry points
- `src/squidpy/_docs.py` | docs helper function: `inject_docs`
- `src/squidpy/__init__.py` | version metadata used in release context (`__version__`)
- `src/squidpy/read/_read.py` | release-relevant reader behavior: `visium`, `vizgen`, `nanostring` | behavior checks: `tests/read/test_visium.py`
- `src/squidpy/gr/_build.py` | release-relevant graph behavior: `spatial_neighbors` | behavior checks: `tests/graph/test_spatial_neighbors.py`
- `src/squidpy/tl/_var_by_distance.py` | release-relevant tool behavior: `var_by_distance` | behavior checks: `tests/tools/test_var_by_distance.py`
- `src/squidpy/pl/_var_by_distance.py` | release-relevant plotting behavior: `var_by_distance` | behavior checks: `tests/plotting/test_var_by_distance_plot.py`
