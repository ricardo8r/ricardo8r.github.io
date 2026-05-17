---
title: "Non-Newtonian flow past a cylinder: parametric reduced-order modelling"
collection: portfolio
layout: single
date: 2020-01-03
---

This case shows a parametric ROM for flow past a cylinder with a power-law fluid, where both the Reynolds number and the power-law index n are parameters. The power-law index controls how strongly the viscosity varies: n < 1 gives a shear-thinning fluid (viscosity drops with strain rate), n > 1 gives a shear-thickening one.

The two images below show the apparent viscosity field for n = 1.8 (shear-thickening, left) and n = 0.4 (shear-thinning, right) at Re = 1000. The difference in flow structure is striking — the shear-thinning case develops a much more complex wake.

![Apparent viscosity — n=1.8 and n=0.4](/images/portfolio/nn_viscosity.png){: style="max-width: 100%; display: block; margin: 1em auto;"}
*Apparent viscosity field for n = 1.8 (left) and n = 0.4 (right) at Re = 1000.*

The ROM is built once from a set of full simulations sampling the parameter space, and then evaluated at any new combination of Re and n at a fraction of the cost.

**Publication:** R. Reyes, O. Ruz, C. Bayona-Roa, E. Castillo, A. Tello, *Reduced order modeling for parametrized generalized Newtonian fluid flows*, Journal of Computational Physics, 484 (2023). [DOI: 10.1016/j.jcp.2023.112086](https://doi.org/10.1016/j.jcp.2023.112086)
