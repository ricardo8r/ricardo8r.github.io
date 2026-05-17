---
title: "Adaptive mesh hyper-reduction for ROMs"
excerpt: "A mesh-based hyper-reduction technique using adaptive coarsening driven by an a posteriori error estimator, applied to thermally coupled and high Reynolds number flows."
collection: portfolio
layout: single
---

Reduced-order models cut cost by reducing the number of unknowns. But for nonlinear problems, assembling the reduced system still requires visiting every element of the original mesh — which can dominate the total cost. Hyper-reduction addresses this by solving the ROM on a coarser mesh.

The approach here uses an adaptive mesh refinement (AMR) strategy driven by an a posteriori error estimator. Rather than uniformly coarsening the mesh, it identifies where the solution varies strongly and keeps resolution there, coarsening everywhere else. This gives controlled accuracy at minimal cost.

## Results

**Backward-facing step at Re = 20,000** — a challenging benchmark with flow separation and reattachment. The geometry is simple but the flow is complex: a shear layer develops at the step, breaks down into vortices, and reattaches further downstream. The full model uses ~62,000 elements. The three rows show FOM, ROM, and hyper-ROM results at t=50.

![Velocity — FOM, ROM, hyper-ROM](/images/portfolio/bstep_velocity.png){: style="max-width: 100%; display: block; margin: 1em auto;"}
*Velocity field: full simulation (top), ROM (middle), hyper-ROM (bottom).*

![Pressure — FOM, ROM, hyper-ROM](/images/portfolio/bstep_pressure.png){: style="max-width: 100%; display: block; margin: 1em auto;"}
*Pressure field: full simulation (top), ROM (middle), hyper-ROM (bottom).*

The ROM runs at 14% of the full simulation cost. The hyper-ROM drops this further to 8%.

**Differentially heated cavity** — thermally driven flow where the error estimator concentrates mesh resolution near the hot and cold walls where thermal gradients are steepest, coarsening the mesh from 80,000 to roughly 10,000 elements.

<table style="width:100%; border:none;">
  <tr>
    <td style="text-align:center; border:none;">
      <img src="/images/portfolio/cavity_velocity.png" style="height:400px;">
      <p><em>Velocity</em></p>
    </td>
    <td style="text-align:center; border:none;">
      <img src="/images/portfolio/cavity_temperature.png" style="height:400px;">
      <p><em>Temperature</em></p>
    </td>
    <td style="text-align:center; border:none;">
      <img src="/images/portfolio/cavity_amr.png" style="height:400px;">
      <p><em>Adaptive mesh</em></p>
    </td>
  </tr>
</table>
*Left to right: velocity field, temperature field, adaptive coarse mesh. Full simulation (left column in each) vs reduced-order model (right column).*

## Publications

R. Reyes, R. Codina, *Element boundary terms in reduced order models for flow problems: Domain decomposition and adaptive coarse mesh hyper-reduction*, Computer Methods in Applied Mechanics and Engineering, 368 (2020). [DOI: 10.1016/j.cma.2020.113159](https://doi.org/10.1016/j.cma.2020.113159)

R. Reyes, R. Codina, J. Baiges, S. Idelsohn, *Reduced order models for thermally coupled low Mach flows*, Advanced Modeling and Simulation in Engineering Sciences, 5:28 (2018). [DOI: 10.1186/s40323-018-0122-7](https://doi.org/10.1186/s40323-018-0122-7)
