# fake_spconv

A minimal shim package that provides the `spconv` import name, re-exporting everything from [`spconv-triton`](https://pypi.org/project/spconv-triton/).

Useful when a tool or library hard-requires `import spconv` / `import spconv.pytorch` (e.g. 3D detection repos like OpenPCDet or mmdet3d) but you want to back it with the Triton-based implementation instead of the CUDA builds.

## Install

```bash
pip install .
```

## Usage

```python
import spconv.pytorch as spconv  # actually spconv-triton
```

## Note

This package contains no code of its own — it only aliases `spconv_triton.pytorch`. Do not install alongside the official `spconv` builds (e.g. `spconv-cu120`), as the import name will collide.
