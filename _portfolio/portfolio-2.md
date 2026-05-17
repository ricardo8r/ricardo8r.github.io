---
title: "Thermally driven flow: differentially heated cavity"
excerpt: "Reduced-order model for buoyancy-driven flow, with adaptive mesh hyper-reduction cutting the mesh from 80,000 to ~10,000 elements."
collection: portfolio
layout: single
date: 2020-01-02
---


Buoyancy-driven flows appear in building energy systems, HVAC, electronics cooling, and many other applications. The Boussinesq approximation is the standard model for this class of problems — it couples fluid flow with a temperature equation where density differences drive the motion.

This case shows a ROM built for a differentially heated cavity: a tall enclosure with a hot wall on one side and a cold wall on the other. The full simulation uses 80,000 finite elements. The ROM captures the coupled velocity and temperature dynamics with 25 modes.

![Velocity field — FOM vs ROM](/images/portfolio/cavity_velocity.png){: style="max-width: 30%; transform: rotate(90deg); display: block; margin: 1em auto;"}
*Velocity field: full simulation (left) vs reduced-order model (right).*

![Temperature field — FOM vs ROM](/images/portfolio/cavity_temperature.png){: style="max-width: 30%; transform: rotate(90deg); display: block; margin: 1em auto;"}
*Temperature field: full simulation (left) vs reduced-order model (right).*

An adaptive mesh hyper-reduction was applied on top of the ROM. An error estimator identifies where the solution needs resolution — in this case near the hot and cold walls — and coarsens the mesh everywhere else. This reduces the active mesh from 80,000 to roughly 10,000 elements with controlled accuracy loss.

![Adaptive hyper-reduction mesh](/images/portfolio/cavity_amr.png){: style="max-width: 30%; transform: rotate(90deg); display: block; margin: 1em auto;"}
*Adaptive coarse mesh driven by an a posteriori error estimator. Finer cells concentrate near the walls where thermal gradients are steepest.*

**Publication:** R. Reyes, R. Codina, J. Baiges, S. Idelsohn, *Reduced order models for thermally coupled low Mach flows*, Advanced Modeling and Simulation in Engineering Sciences, 5:28 (2018). [DOI: 10.1186/s40323-018-0122-7](https://doi.org/10.1186/s40323-018-0122-7)
