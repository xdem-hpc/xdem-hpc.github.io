---
layout: page
title: Software
permalink: /software/
---

## XDEM-HPC

XDEM-HPC is a Julia framework for high-performance simulation of thermochemical
particle systems coupled to CFD. It solves batches of implicit 1-D parabolic and
hyperbolic PDEs — one per particle — on CPU clusters and GPU accelerators.

The code is currently under active development and has not yet been released as
open source. Watch the [GitHub organisation](https://github.com/xdem-hpc) for
announcements.

---

## Architecture

| Layer | Description |
|---|---|
| **Particle physics** | 1-D and transient heat and mass transport with multi-component diffusion, heterogeneous reactions, phase change |
| **Linear solver** | Batched Thomas algorithm (pure tridiagonal) or structured sparse LU (tridiagonal + reaction coupling) |
| **CFD coupling** | Two-way MPMD-MPI coupling to OpenFOAM (ESI v2512 and Foundation) via W-matrix projection |
| **MPI** | Domain decomposition across ranks; W-matrix projection is rank-local (no all-to-all) |
| **GPU backends** | NVIDIA (CUDA.jl), AMD (AMDGPU.jl), Intel (oneAPI.jl), Apple (Metal.jl) via KernelAbstractions.jl |
| **Precision** | Float32 and Float64 selectable at runtime |

---

## Technology Stack

- **Language:** [Julia](https://julialang.org) — high-level productivity with C-level performance
- **GPU kernels:** [KernelAbstractions.jl](https://github.com/JuliaGPU/KernelAbstractions.jl) — single source, all backends
- **MPI:** [MPI.jl](https://github.com/JuliaParallel/MPI.jl)
- **Static arrays:** [StaticArrays.jl](https://github.com/JuliaArrays/StaticArrays.jl) — stack-allocated, isbits metadata in GPU kernels
- **Input format:** HDF5
- **Output format:** HDF5 and ASCII
- **CFD solver:** [OpenFOAM](https://www.openfoam.com) (via C++ shim and MPMD MPI)

---

## Capabilities

- Heat conduction inside particles with user-defined or phase-averaged conductivity
- Multi-component gas-phase diffusion (user-defined, Fuller–Schettler–Giddings, Hirschfelder–Bird–Spotz, Knudsen)
- Heterogeneous solid–gas and homogeneous reactions with enthalpy source terms
- Drying, devolatilisation, and combustion of biomass and solid fuels
- Robin and Neumann boundary conditions per phase (solid, liquid, gas)
- Heat and mass transfer correlations: Ranz–Marshall, Wakao, Gunn, Gnielinski, etc.
- Representative Particle Model (RPM) volume scaling for large particle numbers
