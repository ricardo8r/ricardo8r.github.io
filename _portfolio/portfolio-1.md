---
title: "Stabilized reduced-order models for incompressible flow"
excerpt: "VMS ROM for incompressible Navier-Stokes problems."
collection: portfolio
layout: single
---

Projection-based reduced-order models compress expensive finite element simulations into a small set of modes using Proper Orthogonal Decomposition (POD). The idea is straightforward — but standard Galerkin projection onto a reduced basis inherits the instabilities of the underlying equations. For convection-dominated flows, this means the ROM either blows up or produces garbage without proper stabilization.

This work develops a Variational Multi-Scale (VMS) stabilization for projection-based ROMs that mirrors the stabilization used in the full finite element model. The key ingredients are orthogonal subgrid scales and time-dependent subscales, which together provide stability without introducing excessive dissipation. The stabilization parameters are derived consistently from the full model — no empirical tuning required.

## Results

**Flow past a cylinder at Re = 1000** — a standard benchmark with unsteady vortex shedding. The ROM reproduces velocity and pressure fields accurately with fewer than 30 modes from a full model of ~90,000 degrees of freedom.

![Velocity field — FOM vs ROM](/images/portfolio/cylinder_velocity.png){: style="max-width: 80%; display: block; margin: 1em auto;"}
*Velocity field at t=50: full simulation (left) vs reduced-order model (right).*

**3D flow past a twisted torus at Re = 1000** — a fully three-dimensional geometry with complex wake structure. The full model uses 743,810 degrees of freedom. The ROM captures the flow with 55 modes.

![3D streamlines — twisted ring](/images/portfolio/twisted_ring.png){: style="max-width: 100%; display: block; margin: 1em auto;"}
*Streamlines coloured by velocity magnitude.*

## Publications

R. Reyes, R. Codina, *Projection-based reduced order models for flow problems: A variational multiscale approach*, Computer Methods in Applied Mechanics and Engineering, 363 (2020). [DOI: 10.1016/j.cma.2020.112844](https://doi.org/10.1016/j.cma.2020.112844)

R. Reyes, R. Codina, *Element boundary terms in reduced order models for flow problems: Domain decomposition and adaptive coarse mesh hyper-reduction*, Computer Methods in Applied Mechanics and Engineering, 368 (2020). [DOI: 10.1016/j.cma.2020.113159](https://doi.org/10.1016/j.cma.2020.113159)
