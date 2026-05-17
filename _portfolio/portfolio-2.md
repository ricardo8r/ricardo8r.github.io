---
title: "Thermally driven flow: differentially heated cavity"
excerpt: "Reduced-order model for buoyancy-driven flow in a heated cavity, with adaptive mesh hyper-reduction cutting the computational mesh from 80,000 to ~10,000 elements."
collection: portfolio
layout: single
date: 2020-01-02
---

## Problem

Buoyancy-driven flows appear in many engineering applications — building energy systems, HVAC, electronics cooling, and geophysical flows. Simulating them with full finite element models is expensive, especially when many scenarios need to be evaluated.

## Approach

A stabilized reduced-order model (ROM) was built for the Boussinesq approximation — the standard model for thermally coupled incompressible flows where temperature differences drive fluid motion. The full-order model uses 80,000 finite elements. The ROM compresses this into 25 basis modes while preserving the coupled velocity and temperature dynamics.

An adaptive mesh hyper-reduction (AMR-ROM) was applied on top of the ROM, automatically coarsening the mesh in regions where the solution is smooth and refining where the error is large. This reduces the computational mesh from 80,000 to approximately 10,000 elements with controlled accuracy loss.

## Results

The ROM accurately reproduces both the velocity and temperature fields of the full simulation.

![Velocity field — FOM vs ROM](/images/portfolio/cavity_velocity.png)
*Velocity field: full simulation (left) vs reduced-order model (right).*

![Temperature field — FOM vs ROM](/images/portfolio/cavity_temperature.png)
*Temperature field: full simulation (left) vs reduced-order model (right).*

The adaptive hyper-reduction mesh shows where the solution requires more resolution — concentrated near the hot and cold walls where thermal gradients are steepest.

![Adaptive hyper-reduction mesh](/images/portfolio/cavity_amr.png)
*Adaptive coarse mesh used in the hyper-ROM, driven by an a posteriori error estimator.*

## Publication

Full details in: R. Reyes, R. Codina, J. Baiges, S. Idelsohn, *Reduced order models for thermally coupled low Mach flows*, Advanced Modeling and Simulation in Engineering Sciences, 5:28 (2018). [DOI: 10.1186/s40323-018-0122-7](https://doi.org/10.1186/s40323-018-0122-7)
