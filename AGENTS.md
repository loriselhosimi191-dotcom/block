naserdin
# Agent Instructions for `block`

## What this repository is

`block` is a small Python library for building block matrices across multiple backends.
It provides a unified `block(...)` API for numpy, PyTorch, and SciPy LinearOperator objects.
The package is centered on `block/block.py` and exposes `block` plus helper APIs like `block_diag`.

## Key files

- `block/block.py` - core implementation and backend handling
- `block/__init__.py` - public exports
- `test.py` - repository test runner
- `setup.py` - packaging metadata and install requirements
- `README.md` - usage examples and high-level overview

## Build / test commands

- Run unit tests: `nosetests test.py`
- Install in editable mode: `pip install -e .`
- Install production dependencies: `pip install .`

## Development guidance

- Keep the library Python 3 compatible and maintain the existing numpy-first API semantics.
- Preserve support for both numpy and optional PyTorch backends.
- `block(...)` must accept nested lists/tuples of blocks and infer row/column sizes from actual matrix inputs.
- The code also supports SciPy `LinearOperator` matrices via the `LinearOperatorBackend`.

## What to do when editing

- Read `block/block.py` first. Most logic lives in backend selection, shape inference, and block assembly.
- Avoid introducing dependencies beyond numpy, scipy, and optional torch unless the change is clearly justified.
- Use the existing tests in `test.py` to validate behavior before committing.

## Notes for AI agents

- The repository is a pure Python library, not a web app or service.
- The main goal is correct block matrix assembly and backend compatibility.
- Use `README.md` for high-level guidance, but rely on `block/block.py` for implementation details.
