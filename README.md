# General Mechanics

[![Paper DOI](https://zenodo.org/badge/1033567016.svg)](https://doi.org/10.5281/zenodo.17561404)
[![Repository DOI](https://img.shields.io/badge/DOI-10.5281%2Fzenodo.17561648-blue.svg)](https://doi.org/10.5281/zenodo.17561648)
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![ORCID](https://img.shields.io/badge/ORCID-0009--0007--8303--8627-green.svg)](https://orcid.org/0009-0007-8303-8627)
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/rpoyau/general-mechanics-tests/blob/main/notebooks/GM-1.0-tests.ipynb)

*Axiomatic, manifold-first mechanics together with public SI-2019 temporal comparison notebooks across Solar, Hydrogen, and Galactic/GR windows.*

---

## Abstract

This repository has two public layers.

The **theory layer** presents **General Mechanics (GM)** as familiar mechanics read from the **generalized Stokes identity on an informational manifold**. The **comparison layer** provides public notebooks written in **SI-2019 temporal form** for Solar, Hydrogen, and Galactic/GR windows.

The notebook statements are organized as scope-tight **corollaries** with declared modelling choices and explicit falsification hooks. The package is release-facing: it contains the public theory text, citation metadata, and the public comparison notebooks.

---

## Framework Layers

GM is **relational** and **axiomatic**. Distinctions generate relations; geometry is used as a tool for reading boundary structure, not as an imported law. In the public comparison layer, AFC bookkeeping is treated as **finite, discrete, and ternary** (`yes / no / unknown`). Smooth differential expressions appear as derived tools or numerical comparison layers, not as foundational primitives.

This repository therefore combines three layers:

1. **GM theory:** generalized Stokes on an informational manifold.
2. **AF structure:** axioms, consequences, modelling choices, corollaries, and falsification hooks.
3. **AFC bookkeeping:** discrete Stokes balance and ternary counting used to keep the derivations traceable.

---

## Comparative Units and Hidden Temporal Dependency

The main methodological claim tested in this repository is universal:

If a reported quantity is written as
\[
Q(t)=q(t)\,u(t),
\]
where \(q(t)\) is the numerical value and \(u(t)\) is the reporting unit, then
\[
\frac{dQ}{dt}
=
u(t)\frac{dq}{dt}
+
q(t)\frac{du}{dt}.
\]

If \(u(t)\) is treated as constant when it is not, the second term is dropped.  
That omission is the **chain-rule defect**.

This does not depend on one particular unit system. Any **comparative unit with hidden temporal dependency** is unsafe as a primitive variable in calculus with respect to time.

In this repository, the practical cases of interest are:

- distance handled as **causal duration**,
- mass handled through its **rest-energy rate [Hz]**.

Comparative units remain acceptable as reporting forms, but not as primitive variables when their temporal dependence remains implicit.

## SI-2019 Temporal Form

The public numerical layer is written in **SI-2019 temporal form**.

- The **second** is the operational clock unit.
- The **metre** is treated through the fixed light speed \(c\), so spatial length is handled as a causal light-travel duration.
- The **kilogram** is treated through the fixed Planck constant \(h\) together with \(c\) and the second, so mass enters the numerical layer through its rest-energy rate.

In the GM notation used here, **Kz** is the **Hz-rate label** attached to that SI-temporal rewrite. When a distinct **Kick** label is needed, it is written **Kk**. No separate natural-unit reduction is used in the public tests.

The Hz-rate rewrite used throughout the repository, written with the **Kz** label in GM notation, is

\[
E_{\mathrm{Kz}} = \frac{E}{h},
\qquad
m_{\mathrm{Kz}} = \frac{m c^2}{h},
\qquad
T_{\mathrm{Kz}} = \frac{k_B T}{h},
\qquad
P_{\mathrm{Kz}} = \frac{P}{h}.
\]

For catalog masses,

\[
f_{\mathrm{Kz}}(M) \equiv f_{\mathrm{Hz}}(M) = \frac{M c^2}{h},
\]

so a mass given in kilograms is represented as a **Hz-rate** through its rest-energy relation. Speeds are handled through the dimensionless ratio

\[
\beta = \frac{v}{c} \in [0,1].
\]

The public notebook therefore stays in **SI-2019 temporal form** rather than introducing a second unit system.

## Verification Scope

### Solar tests

The Solar window works in a small-gradient regime and checks the leading GM consequences against catalog benchmarks using a single numerical source scale \(\mu\):

- **Corollary I:** Mercury perihelion advance.
- **Corollary II:** Solar-limb light deflection.
- **Corollary IIb:** Entropic versus geometric off-limb shape comparison.
- **Corollary III:** Solar surface redshift.

These tests are treated as **first-order consistency checks** in the shared small-gradient regime.

### Hydrogen tests

The Hydrogen window evaluates a bandwidth-limited confinement regime:

- **Corollary IV:** Electron rest-energy rate [Hz] from the SI-2019 mass-to-rate rewrite.
- **Corollary V:** Hydrogen shell radii from time-information plus least-action closure, compared to the \(r_n = n^2 a_0\) scaling.

### Galactic / GR comparison

The extended macro window compares three summaries outside the core radius:

- classical Keplerian falloff,
- a GR-style SI-temporal comparison layer that keeps the relevant unit-derivative term,
- the GM dimensional-flow summary.

The purpose of this section is a **GM update with a GR comparison**, still written in SI-2019 temporal form.

---

## Public Repository Contents

This public release package is limited to the theory texts, citation metadata, and the public comparison notebooks.

- `notebooks/` — public numerical comparison notebooks for the Solar, Hydrogen, and Galactic / GR comparison windows.
- `preamble.tex` — shared notation and Kz macros.
- `CITATION.cff` — citation metadata for repository and manuscript references.
- manuscript sources / exports for the main **General Mechanics** text and related AF / AFC support material.

---

## Relationship to the Theory Texts

This repository operationalizes consequences derived in the main **General Mechanics** manuscript and follows the AF writing discipline set by **Axiomatic Fundamentalism**. It also uses **AFC** as a bookkeeping layer for finite distinctions, discrete Stokes balance, and ternary counting.

### Primary references

- Reginald, P. (2025). *General Mechanics*. Zenodo.  
  <https://doi.org/10.5281/zenodo.17561404>

- Reginald, P. (2025). *Axiomatic Fundamentalism (AF): A Logical Protocol for Traceable Research*. Zenodo.  
  <https://doi.org/10.5281/zenodo.17561186>

- Reginald, P. (2025). *Axiomatic Fundamentalism Calculus (AFC): The Hidden Form of Stokes*. Zenodo.  
  <https://doi.org/10.5281/zenodo.17807779>

- BIPM. *The International System of Units (SI): defining constants*.  
  <https://www.bipm.org/en/measurement-units/si-defining-constants>

- BIPM. *SI base unit: kilogram (kg).*  
  <https://www.bipm.org/en/si-base-units/kilogram>

- NIST. *Unit Conversion: kg to Hz*.  
  <https://physics.nist.gov/cgi-bin/cuu/Convert?exp=0&num=1&From=kg&To=hz&Action=Convert+value+and+show+factor>

---

## AF / AFC Public Structure

The verification notebooks keep the same public AF ordering used in the texts:

1. state axioms once,
2. derive consequences mathematically,
3. declare modelling choices explicitly,
4. extract corollaries,
5. attach falsification hooks,
6. keep notation and units fixed within scope.

Nothing is imported mid-derivation as an external law. Demonstrations instantiate the previously declared structure.

---

## Usage

### Clone the repository

```bash
git clone https://github.com/rpoyau/general-mechanics.git
cd general-mechanics
```

### Open the notebook locally

```bash
jupyter lab
```

Then open the notebook in `notebooks/` corresponding to the verification window of interest.

### Open the verification notebook in Colab

Use the badge at the top of this page to launch the current public notebook snapshot.

---

## Notes on Interpretation

- The theory layer is **manifold-first and relational**.
- The bookkeeping layer is **discrete and ternary**.
- The numerical layer is written in **SI-2019 temporal form** for comparison with catalog data.
- Comparative units are treated as reporting forms, not as temporally independent primitives in time calculus.
- Agreement in a shared weak-field or small-gradient regime is treated as a **consistency result**, not by itself as a unique discriminator.

---

## Citation

If this repository is used in research, please cite the Zenodo record for the repository together with the primary *General Mechanics* manuscript DOI listed above.

---

## License

Released under the MIT License. See `LICENSE`.
