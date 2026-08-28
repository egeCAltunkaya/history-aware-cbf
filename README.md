# History-Aware Control Barrier Functions with Nonsingular Fading-Memory Kernels

Companion repository for the manuscript  
**“History-Aware Control Barrier Functions with Nonsingular Fading-Memory Kernels.”**

The work develops a control-barrier-function framework for integer-order systems in which retained barrier history conditions the admissible control authority, while safety is certified with respect to the original state-defined physical safe set.

<p align="center">
  <a href="YOUR_CURRENT_WEBSITE_URL"><b>Project Website</b></a>
  &nbsp;&nbsp;•&nbsp;&nbsp;
  <b>arXiv — coming soon</b>
  &nbsp;&nbsp;•&nbsp;&nbsp;
  <a href="docs/History_Aware_Control_Barrier_Functions_with_Nonsingular_Fading_Memory_Kernels_Supplementary_Material.pdf"><b>Supplementary Material</b></a>
</p>

---

## Overview

Conventional state-only control barrier functions assign the same admissible control set whenever the current state is the same. This work considers safety policies for which the available control authority also depends on the retained history of the barrier.

The proposed framework introduces a nonsingular fading-memory operator into the barrier construction and establishes forward invariance of the original physical safe set through a Volterra-resolvent argument.

The resulting policy can therefore distinguish trajectories that reach the same current state with different histories.

### Main contributions

- A nonsingular fractional-memory CBF formulation for integer-order dynamical systems.
- A forward-invariance result linking the history-dependent auxiliary certificate to the original physical safe set.
- A formal history-conditioned safety policy that allows admissible control authority to vary with retained barrier history.
- Exact finite-dimensional realizations for exponential kernels, including the one-state Caputo–Fabrizio case.
- Numerical validation demonstrating the same mechanism for non-CF kernels, including bi-exponential and Gaussian fading memory.

---

## Numerical study

The method is evaluated on a high-incidence aircraft benchmark with redundant control effectors.

Three preparation trajectories reach the same activation state with different retained histories. The subsequent maneuver is identical in all cases.

For the CF realization, the normalized admissible-set volumes at engagement are

| History | Normalized admissible volume |
|---|---:|
| Adverse | 0.242 |
| Neutral | 0.616 |
| Favorable | 0.823 |
| History-blind policy-preserving CBF | 0.072 |

The stress-test study additionally shows:

- **36/36** high-demand cases are hard-safe under CF-FOCBF.
- **36/36** are policy-safe and feasible.
- CF-FOCBF improves tracking RMSE over the policy-preserving state-only CBF in **36/36** cases.
- Mean RMSE reduction: **30.9%**.
- In **18/18** low-demand negative-control cases, CF-FOCBF remains inactive, whereas the policy-preserving state-only CBF intervenes.

Full figures and extended validation are available on the **Project Website**.

---

## Beyond the Caputo–Fabrizio kernel

The theoretical construction is not restricted to the exponential CF kernel.

For a generic retained-memory term:

```math
q_{\kappa}(t)
=
\int_{t_0}^{t}
\kappa(t-\tau)\,\dot h(\tau)\,d\tau .
```

The supplementary study considers three realizations.

### Caputo–Fabrizio

```math
\kappa_{\mathrm{CF}}(s)
=
\kappa_0 e^{-\lambda s}.
```

This kernel admits the exact one-state realization

```math
\dot q
=
-\lambda q+\kappa_0\dot h .
```

### Bi-exponential kernel

```math
\kappa_{\mathrm{BE}}(s)
=
\kappa_0
\left[
a e^{-\lambda_1 s}
+
(1-a)e^{-\lambda_2 s}
\right].
```

An exact two-state realization is obtained from

```math
\dot q_1
=
-\lambda_1 q_1+\kappa_0\dot h,
\qquad
\dot q_2
=
-\lambda_2 q_2+\kappa_0\dot h,
```

with

```math
q
=
a q_1+(1-a)q_2 .
```

### Gaussian kernel

```math
\kappa_{\mathrm G}(s)
=
\kappa_0
\exp\!\left[
-\left(\frac{s}{\tau_G}\right)^2
\right].
```

The retained-memory term is evaluated directly from history:

```math
q_{\mathrm G}(t)
=
\int_{t_0}^{t}
\kappa_{\mathrm G}(t-\tau)\,\dot h(\tau)\,d\tau .
```

The purpose of these comparisons is to demonstrate that the history-conditioned authority mechanism is not specific to the one-state CF implementation; they are not intended as a cross-kernel performance ranking.

---

## Repository structure

```text
history-aware-cbf/
├── docs/                  # GitHub Pages project website
├── matlab/                # MATLAB implementation / validation scripts
├── figure_templates/      # Approved MATLAB figure templates
└── README.md
```

The public website is served from the `docs/` directory.

---

## Code and data availability

A cleaned and documented MATLAB implementation is being prepared for public release.

The numerical datasets underlying the reported figures and tables are available from the corresponding author upon reasonable request.

---

## Supplementary material

Extended numerical validation, stress tests, and the bi-exponential and Gaussian kernel studies are provided in the supplementary document:

**[Open the Supplementary Material](docs/History_Aware_Control_Barrier_Functions_with_Nonsingular_Fading_Memory_Kernels_Supplementary_Material.pdf)**

---

## Citation

If you use this work, please cite:

```bibtex
@article{altunkaya2026historyaware,
  title   = {History-Aware Control Barrier Functions with Nonsingular Fading-Memory Kernels},
  author  = {Altunkaya, Ege C. and Demir, Esra and {\"O}zkol, {\.I}brahim},
  year    = {2026},
  note    = {Preprint}
}
```

The citation entry will be updated when the final arXiv / publication metadata becomes available.

---

## Authors

**Ege C. Altunkaya** · **Esra Demir** · **İbrahim Özkol**  
Aviation Institute, Istanbul Technical University  
Istanbul, Türkiye

For questions regarding the work or numerical datasets, please contact the corresponding author.
