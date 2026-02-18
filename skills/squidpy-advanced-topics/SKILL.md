---
name: squidpy-advanced-topics
description: Use this skill for lower-frequency Squidpy docs tasks: release-notes index routing, bibliography/reference maintenance, and spelling wordlist updates.
---

# squidpy: Advanced Topics

## Route conditions
- Use this skill for docs-only maintenance tasks around release-note indexing, references, and spelling dictionary updates.
- Route API behavior or simulation workflows to `squidpy-api-and-scripting`.
- Route install or environment tasks to `squidpy-build-and-install`.
- Route version-window and migration triage to `squidpy-release`.

## Primary documentation references
- `docs/release_notes.md`
- `docs/references.md`
- `docs/references.bib`
- `docs/spelling_wordlist.txt`

## Practical playbook
1. Start from the matching doc above.
2. Use `references/doc_map.md` to confirm the right file and headings.
3. If a doc claim implies runtime behavior, jump to `references/source_map.md` and verify the mapped function/test pair.
4. Keep edits narrow and path-cited.

## Quick version context check
```bash
python -c "import squidpy as sq; print(sq.__version__)"
```

## Source entry points for unresolved behavior tie-ins
- `src/squidpy/_docs.py`
- `src/squidpy/__init__.py`
- `src/squidpy/read/_read.py`
- `src/squidpy/gr/_build.py`
- `src/squidpy/tl/_var_by_distance.py`
- `src/squidpy/pl/_var_by_distance.py`
