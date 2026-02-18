# squidpy source map: Build and Install

Generated from source roots:
- `src`

Use this map only after exhausting the topic docs in `doc_map.md`.

## Fast source navigation
- `rg -n "requires-python|dependencies|hatch" pyproject.toml`
- `rg -n "^(def|class) " src/squidpy/{read,gr,im}`

## Suggested source entry points
- `pyproject.toml` | build/runtime contract: `requires-python`, dependency pins, hatch scripts (`test`, `docs:build`)
- `src/squidpy/__init__.py` | import metadata path for `__version__` and module exports
- `src/squidpy/_compat.py` | compatibility shims for scanpy/anndata APIs
- `src/squidpy/read/_read.py` | runtime reader dependencies through `visium`, `vizgen`, `nanostring` | behavior checks: `tests/read/test_visium.py`
- `src/squidpy/gr/_build.py` | core compute dependency surface through `spatial_neighbors` | behavior checks: `tests/graph/test_spatial_neighbors.py`
- `src/squidpy/im/_process.py` | image processing dependency surface through `process` | behavior checks: `tests/image/test_processing.py`
- `src/squidpy/im/_segment.py` | segmentation dependency surface through `segment`, `SegmentationWatershed` | behavior checks: `tests/image/test_segmentation.py`

## Focused validation commands
- `python -c "import squidpy as sq; print(sq.__version__)"`
- `pytest -q tests/read/test_visium.py tests/graph/test_spatial_neighbors.py`
- `pytest -q tests/image/test_processing.py tests/image/test_segmentation.py`
