---
title: "Frequency Reduced-Basis method: ROM for time-dependent problems"
excerpt: "A reduced-basis method for time-dependent PDEs using the Laplace transform, with exponential accuracy guarantees and a fully parallelisable offline stage."
collection: portfolio
layout: single
date: 2026-05-08
---

Standard reduced-order models for time-dependent problems build a basis from snapshots of the solution at successive time steps. For oscillatory or wave-like problems, this requires dense sampling over long time intervals — expensive, and still often insufficient to capture the full dynamics.

The Frequency Reduced-Basis (FRB) method samples in the frequency domain instead. Applying the Laplace transform converts the time-dependent problem into a set of independent elliptic problems parametrized by complex frequency. These can be solved in parallel, and the resulting basis is provably accurate for the time-dependent problem via a norm equivalence between the time and frequency domains (Paley-Wiener theorem).

## Method

```
Offline stage (frequency domain):
  1. Apply Laplace transform to the PDE
       → elliptic problem: (s²M + A) û(s) = b̂(s) - su₀ - u₀'
  2. Sample frequencies: s_j = ζ + iλ cot(θ_j), θ_j ∈ (0,π)
  3. Solve each frequency problem independently (parallelisable)
  4. Build snapshot matrix S = {w_j û(s_j)}, w_j = 2λ/sin²(θ_j)
  5. Compute SVD of S → reduced basis Φ

Online stage (time domain):
  6. Project PDE onto span(Φ) → low-dimensional system
  7. Solve with any time integrator
```

Key properties:
- Frequency solves are independent — fully parallelisable offline stage
- Fewer samples needed for oscillatory problems than time-domain ROM
- Basis construction is decoupled from the time discretization
- Intrinsic stabilization for convection-dominated problems — no tuning required

## Results

**Wave equation in a polygonal domain** — highly oscillatory solution with wave interference. The solution changes dramatically between time steps with no predictable pattern, making time-domain sampling inefficient.

![Wave solution at three time steps](/images/portfolio/frb_wave.png){: style="max-width: 100%; display: block; margin: 1em auto;"}
*Solution at t = 23, 24, 25. The interference pattern is complex and unpredictable.*

**Wave equation in a multi-ring domain** — comparison of FRB against time-domain ROM with the same number of samples. The FRB accurately reproduces the solution; the time-domain ROM fails entirely.

![Topology comparison: FE, time ROM, FRB symplectic, FRB real](/images/portfolio/frb_topology.png){: style="max-width: 90%; display: block; margin: 1em auto;"}
*Top left: FE reference. Top right: time-domain ROM. Bottom left: FRB symplectic basis. Bottom right: FRB real basis.*

**Advection-dominated problem** — the FRB solution is free of spurious oscillations with no explicit stabilization applied, performing comparably to VMS-stabilized finite element methods.

![Advection stabilization comparison](/images/portfolio/frb_advection.png){: style="max-width: 90%; display: block; margin: 1em auto;"}
*Top left: unstabilized FE. Top right: VMS. Bottom left: SUPG. Bottom right: FRB — oscillation-free without any stabilization.*

## Publication

R. Reyes, *The Frequency Reduced-Basis method: reduced order models for time-dependent problems using the Laplace transform*, Computational Mechanics, 2026. [DOI: 10.1007/s00466-026-02795-6](https://doi.org/10.1007/s00466-026-02795-6)