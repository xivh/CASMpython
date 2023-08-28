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
- always perform a convergence check, even if volume is fixed (ISIF = 0, 1, 2)
- allow exclude flag for SLURM. this may break PBS compatibility
  - this is not implemented very well: it may be better to pass all possible settings through as a dictionary (or just use ASE/Pymatgen) rather than hardcoding them one by one in `vaspwrapper/vasp_calculator_base.submit`. it is not clear if other settings, e.g. constraint, are being passed through from CASMPython to prisms_jobs (I do not think that they are)
- if ISIF = 0, 1, 2 and the first relaxation only took one ionic step, consider the job to be converged rather than always requiring two relaxations for convergence
  - requires ISIF to be set explicitly
- pass unused constraint flag through
- set --gpus flag (SLURM only). I did not update the run command for gpus, so this means that if you want to use gpus you have to pass the correct command yourself.