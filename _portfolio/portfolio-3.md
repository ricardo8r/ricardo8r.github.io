---
title: "Parametric reduced-order models for complex fluids"
excerpt: "ROM for parametrized fluid flow problems, including non-Newtonian fluids."
collection: portfolio
layout: single
---

Many engineering and biomedical flow problems depend on parameters — material properties, operating conditions, geometry — and require evaluating the solution across a range of these. Running a full finite element simulation for each combination is prohibitive. A parametric ROM is built once from a set of full simulations sampling the parameter space, then evaluated at any new parameter combination at a fraction of the cost.

This work extends parametric ROM to fluids with nonlinear viscosity — generalised Newtonian fluids, where viscosity depends on the local strain rate. This is the standard model for polymers, food products, biological fluids, and many industrial flows. The nonlinear viscosity makes the problem harder to reduce, requiring a Tucker decomposition on top of the standard POD to handle the parameter dependence efficiently.

## Results

**Non-Newtonian flow past a cylinder** — Reynolds number and power-law index n as parameters. The power-law index controls the viscosity behaviour: n < 1 gives a shear-thinning fluid (viscosity drops with strain rate), n > 1 gives a shear-thickening one. The two cases below show how dramatically the flow structure changes between the two regimes at Re = 1000.

![Apparent viscosity — n=1.8 and n=0.4](/images/portfolio/nn_viscosity.png){: style="max-width: 100%; display: block; margin: 1em auto;"}
*Apparent viscosity field for n = 1.8 (left) and n = 0.4 (right) at Re = 1000. The shear-thinning case develops a significantly more complex wake.*

The ROM is built from simulations at Re = {100, 120, 140} and n = {0.4, 0.6, 1.0, 1.4, 1.8}, and evaluated at any combination in that range.

## Publications

R. Reyes, O. Ruz, C. Bayona-Roa, E. Castillo, A. Tello, *Reduced order modeling for parametrized generalized Newtonian fluid flows*, Journal of Computational Physics, 484 (2023). [DOI: 10.1016/j.jcp.2023.112086](https://doi.org/10.1016/j.jcp.2023.112086)

C. Farías, C. Bayona-Roa, E. Castillo, R. Cabrales, R. Reyes, *Reduced order modeling of parametrized pulsatile blood flows: Hematocrit percentage and heart rate*, International Journal of Engineering Science, 193 (2023). [DOI: 10.1016/j.ijengsci.2023.103943](https://doi.org/10.1016/j.ijengsci.2023.103943)gg
