---
title: "Vortex shedding: reduced-order modelling for incompressible flow"
collection: portfolio
layout: single
---

Simulating unsteady flows is expensive. For problems that require many evaluations — parametric studies, design optimization, real-time applications — running a full finite element simulation each time is not practical.

This case shows a reduced-order model (ROM) built for flow past a circular cylinder at Reynolds number 1000, a standard benchmark with unsteady vortex shedding. The full simulation uses around 90,000 degrees of freedom. The ROM reduces this to fewer than 30 modes while accurately reproducing the flow.

![Velocity field — FOM vs ROM](/images/portfolio/cylinder_velocity.png)
*Velocity field at t=50: full simulation (left) vs reduced-order model (right).*

![Pressure field — FOM vs ROM](/images/portfolio/cylinder_pressure.png)
*Pressure field at t=50: full simulation (left) vs reduced-order model (right).*

The ROM runs at roughly 6% of the cost of the full simulation. With mesh-based hyper-reduction applied on top, this drops further to around 1%.

![Computational time ratio](/images/portfolio/cylinder_speedup.png){: style="max-width: 70%; display: block; margin: 1em auto;"}
*Computation time of ROM and hyper-ROM relative to the full simulation.*

**Publication:** R. Reyes, R. Codina, *Projection-based reduced order models for flow problems: A variational multiscale approach*, Computer Methods in Applied Mechanics and Engineering, 363 (2020). [DOI: 10.1016/j.cma.2020.112844](https://doi.org/10.1016/j.cma.2020.112844)
