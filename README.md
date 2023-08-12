The CASM Python packages
========================

The `casm-python` Python packages provide a Python interface to the CASM libraries, implement wrappers to fitting methods and DFT software, and provide other tools for plotting and analysis.

This version of `casm-python` is compatible with  [CASM](https://prisms-center.github.io/CASMcode_docs/) >=1.2.

A basic online reference is located [here](https://prisms-center.github.io/CASMcode_pydocs/latest/index.html)


For a summary of changes, see [CHANGELOG.md](https://github.com/prisms-center/CASMpython/blob/1.X/CHANGELOG.md).

Local Changes
-------------
- enforce sh==1.14.2 in requirements.txt
- if err_types is not set, skip error checking in error.py
  - SubSpaceMatrixError() was set on by default originally
- if FreezeError is not requested, do not check in error.py