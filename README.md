# HybridMC: Hybrid Monte Carlo Protein Folding
[![conda_publish_linux workflow status](https://github.com/margaritacolberg/hybridmc/actions/workflows/format.yml/badge.svg)](https://github.com/margaritacolberg/hybridmc/actions/workflows/format.yml?query=branch:main)

HybridMC simulates the event-driven dynamics of coarse-grained protein folding.
The entropy and mean first passage times (MFPT) of each bond forming or
breaking event are calculated, and the Markov transition rate matrix is
constructed. The average time needed to fold to the protein's native state,
starting from the unfolded state, is evaluated under two conditions.

This is the wang_landau plugin that is used within that program

For more information, see the [publication](https://doi.org/10.1063/5.0098612)
or the [preprint](https://arxiv.org/abs/2205.05799).

## Directories

See top level comment in each file for more details as to what each file does.
Some top level comments also contain examples of how to run each file, if
complicated.

  * `src`: C++ source code for HybridMC program

## C++ Program Details

### Prerequisite Software

  * C++17 compiler with support for C++20
    [bit library](https://en.cppreference.com/w/cpp/header/bit)

    see bit operations under C++20 [compiler
    support](https://en.cppreference.com/w/cpp/compiler_support/20)

    tested with GCC 9.3.0 on CentOS 7.9

  * Minimum CMake version is 3.13.1

  * [Ninja](https://ninja-build.org/)

  * HDF5 version 1.10 or later

  * Boost

### Commands for Compiling

To compile HybridMC Wang landau pybind11 plugin for development and testing:

```
pip install -e . -vv
```

### Input arguments
This is a python module:

It needs the input JSON configuration file and an optional input HDF5 file in case
this is not a layer 0 simulation.

### Testing
Run `conda install vignesh229::hybridmc`

Run examples from [hybridmc](https://github.com/Vigne-hub/hybridmc) as per instructions there.
