# Installation Guide

## Prerequisites

- **Python** - `MACH2` requires Python 3.7 or newer.
- **ILP solver** - `MACH2` requires an ILP solver installed to solve **PMH-TR**. Currently `MACH2` only supports `Gurobi optimizer`, but we are going to add support for more ILP solvers in the future. `MACH2` requires a valid Gurobi installation and license key. The location of Gurobi should be present in `LD_LIBRARY_PATH` (linux) and `DYLD_LIBRARY_PATH` (macOS) the license key should be saved in the environment variable `GRB_LICENSE_KEY`.

## Installing MACH2

MACH2 can be installed using the following command:

```bash
pip install mach2 && pip install mach2[jupyter]
```

## MACH2-Viz

MACH2-Viz can simply be opened with the following [link](https://elkebir-group.github.io/mach2-viz/#/). However, there is a Python package that allows for opening MACH2-Viz in localhost directly from a Python script or Jupyter Notebook.  
  
The package will be installed as a dependency when MACH2 is installed, but to install the Python package for MACH2-Viz alone, run:

```bash
pip install mach2-viz
```
