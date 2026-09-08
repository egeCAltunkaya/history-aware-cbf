# History-Aware Control Barrier Functions with Nonsingular Fading-Memory Kernels

**Ege C. Altunkaya · Esra Demir · İbrahim Özkol**  
Aviation Institute, Istanbul Technical University

<p align="center">
  <a href="https://egecaltunkaya.github.io/history-aware-cbf/"><b>Project Website</b></a>
  &nbsp;&nbsp;•&nbsp;&nbsp;
  <a href="docs/supplementary.pdf"><b>Supplementary Material</b></a>
  &nbsp;&nbsp;•&nbsp;&nbsp;
  <b>arXiv — coming soon</b>
</p>

---

## Overview

This repository accompanies the manuscript **“History-Aware Control Barrier Functions with Nonsingular Fading-Memory Kernels.”**

The paper addresses a limitation of state-only safety filters: two trajectories can reach the **same current physical state** while carrying different recent safety-margin histories, yet a state-only CBF must assign them the same admissible control set.

We introduce a history-aware CBF framework for **integer-order, delay-free control-affine systems** in which a nonsingular fading-memory kernel retains signed safety-margin variation,

```math
q_{\kappa}(t)
=
\int_{t_0}^{t}
\kappa(t-\tau)\,\dot h(\tau)\,d\tau ,
```

and uses it to enforce a reserve policy on the current margin. The resulting admissible-control set depends on retained history while the certified physical safe set remains

```math
\mathcal C=\{x:h(x)\ge 0\}.
```

A positive Volterra-resolvent argument proves that nonnegativity of the auxiliary history-dependent barrier implies forward invariance of this original state-defined safe set. The result does **not** require the memory operator to admit a finite-dimensional realization.

---

## Main result

At the same current state, different compatible histories can produce different history-aware admissible sets,

```math
\mathcal U_H(x,\mathcal H_t)
=
\{u\in\mathcal U:Q_{\kappa}(x,\mathcal H_t,u)\ge 0\}.
```

A history-blind policy-preserving filter must instead remain inside the common intersection over all compatible histories. This creates a fundamental loss of available control authority whenever the intended reserve policy is history dependent.

The framework therefore separates three questions that a state-only hard-safety CBF does not:

- **Is the physical safe set preserved?**
- **Is the prescribed reserve policy preserved?**
- **How much control authority remains admissible for the retained history?**

---

## ADMIRE envelope-protection study

The manuscript evaluates the Caputo–Fabrizio specialization on a high-incidence ADMIRE benchmark with redundant control effectors.

Three preparation trajectories reach the same activation state to numerical tolerance but retain different fading-memory values. At that common checkpoint, the normalized admissible-control volumes are:

| Controller / history | Normalized volume |
|---|---:|
| CF-FOCBF — adverse | **0.242** |
| CF-FOCBF — neutral | **0.616** |
| CF-FOCBF — favorable | **0.823** |
| History-blind policy-preserving CBF | **0.072** |

With fixed gains over **36 high-demand cases**:

- CF-FOCBF preserves the physical incidence bound in **36/36** cases.
- CF-FOCBF preserves the reserve policy in **36/36** cases.
- No CF quadratic program is infeasible.
- CF-FOCBF reduces tracking RMSE relative to the history-blind policy-preserving CBF in **36/36** cases, by **30.9% on average**.
- A performance-optimal state-only CBF preserves the physical bound but violates the reserve policy in **36/36** cases.

These results distinguish **physical safety**, **policy compliance**, and **tracking performance** rather than treating them as interchangeable.

---

## Beyond the CF realization

The theorem is formulated directly for admissible nonsingular fading-memory kernels, not only for the exponential CF kernel.

The companion validation therefore includes:

### Caputo–Fabrizio

```math
\kappa_{\mathrm{CF}}(s)=\kappa_0 e^{-\lambda s},
```

with an exact **one-state** realization.

### Bi-exponential

```math
\kappa_{\mathrm{BE}}(s)
=
\kappa_0
\left[
a e^{-\lambda_1 s}
+
(1-a)e^{-\lambda_2 s}
\right],
```

with an exact **two-state** realization.

### Gaussian

```math
\kappa_{\mathrm G}(s)
=
\kappa_0
\exp\!\left[
-\left(\frac{s}{\tau_G}\right)^2
\right],
```

evaluated directly from retained history rather than replaced by a finite-dimensional exponential surrogate.

The alternative-kernel studies are intended to test the **general history-conditioned mechanism**, not to rank kernels by tracking performance.

---

## Project resources

- **Project website:** https://egecaltunkaya.github.io/history-aware-cbf/
- **Supplementary material:** [docs/supplementary.pdf](docs/supplementary.pdf)
- **MATLAB implementation:** a cleaned and documented release is being prepared.
- **Numerical datasets:** available from the corresponding author upon reasonable request.

---

## Citation

The bibliographic entry will be updated when the arXiv / final publication metadata becomes available.

```bibtex
@article{altunkaya2026historyaware,
  title   = {History-Aware Control Barrier Functions with Nonsingular Fading-Memory Kernels},
  author  = {Altunkaya, Ege C. and Demir, Esra and {\"O}zkol, {\.I}brahim},
  year    = {2026},
  note    = {Preprint}
}
```

---

## Contact

**Ege C. Altunkaya**  
Aviation Institute, Istanbul Technical University  
Corresponding author: [altunkaya16@itu.edu.tr](mailto:altunkaya16@itu.edu.tr)
