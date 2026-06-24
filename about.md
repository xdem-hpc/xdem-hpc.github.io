---
layout: page
title: About
permalink: /about/
---

## The Team

XDEM-HPC is developed at **Vilnius Gediminas Technical University (VILNIUS TECH)**,
Lithuania. The project is led by Prof. Bernhard Peters, whose research focuses on
thermochemical conversion of granular materials — chemistry such as reduction, pyrolysis 
and  gasification, phase change e.g. drying, melting or coating of packed beds and 
moving granular systems.

## Scientific Mission

Granular materials play a central role in energy conversion, chemical engineering,
and environmental technology. Simulating the coupled thermal, chemical, and mechanical
behaviour of millions of individual particles at engineering scale requires both a
physically rigorous model and a software architecture that can exploit modern
high-performance computing hardware.

XDEM-HPC addresses this by combining:

- **The Extended Discrete Element Method (XDEM)** — each particle is resolved
  individually with its own 1-D internal spatial grid, capturing temperature
  gradients, species transport, phase changes, and heterogeneous reactions inside
  the particle.
- **Two-way CFD-DEM coupling** — particles exchange heat, mass, and momentum with
  a surrounding fluid phase solved by OpenFOAM satisfying conservation of exchanged 
  properties and  enabling packed-bed and fluidised-bed simulations at industrial scale.
- **HPC and GPU computing** — the solver is written in Julia and targets CPU
  clusters via MPI as well as GPU accelerators (NVIDIA CUDA, AMD ROCm) through
  a single backend-agnostic codebase.

## History

The XDEM concept was originally conceived at the Research Centre Karlsruhe, now
the Karlsruhe Institute of Technology (KIT) where pioneering work was carried out 
by Bernhard Peters. Further development was undertaken at the University of Luxembourg
by Bernhard Peters. However, that codebase is currently no longer maintained or accessible. 
XDEM-HPC is a full redesign from the ground up, retaining the scientific foundation 
while replacing the C++ implementation with a modern Julia framework built for 
scalable HPC and GPU computing.
