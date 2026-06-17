---
layout: home
---

## What is XDEM-HPC?

XDEM-HPC is a Julia framework for high-performance Discrete Element Method (DEM)
simulations with full two-way coupling to Computational Fluid Dynamics (CFD) solvers.

It is the successor to the C++ XDEM platform, redesigned from the ground up for
modern HPC hardware: multi-core CPU clusters and GPU accelerators (NVIDIA CUDA,
AMD ROCm).

> **XDEM-HPC is currently under active development and has not yet been released
> as open source.**  We plan to make the code publicly available once a stable
> baseline is established.  Watch this page or the
> [GitHub organisation](https://github.com/xdem-hpc) for announcements.

---

## Planned features

- **GPU-native kernels** via [KernelAbstractions.jl](https://github.com/JuliaGPU/KernelAbstractions.jl) — single codebase runs on CPU and GPU
- **Two-way CFD-DEM coupling** to OpenFOAM (ESI v2512 and Foundation 9) via MPMD MPI
- **Float32 / Float64** selectable at runtime — maximise GPU throughput or precision as needed
- **Thermochemical particle physics** — heat conduction, drying, devolatilisation, combustion
- **Co-located MPI partitioning** — W-matrix projection is rank-local, no all-to-all communication

---

## Background

XDEM (eXtended Discrete Element Method) was originally developed at the
University of Luxembourg. XDEM-HPC continues this work with a focus on
scalable HPC and GPU computing.
