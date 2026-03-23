# General Mechanics

[![Paper DOI](https://zenodo.org/badge/1033567016.svg)](https://doi.org/10.5281/zenodo.17561404)
[![Repository DOI](https://img.shields.io/badge/DOI-10.5281%2Fzenodo.17561648-blue.svg)](https://doi.org/10.5281/zenodo.17561648)
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![ORCID](https://img.shields.io/badge/ORCID-0009--0007--8303--8627-green.svg)](https://orcid.org/0009-0007-8303-8627)
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/rpoyau/general-mechanics/blob/main/notebooks/gm-tests.ipynb)

*Axiomatic, manifold-first mechanics in which laws emerge as relational motifs from a single geometric identity (generalized Stokes), together with AF/AFC-compliant numerical tests in Solar, Hydrogen, and Galactic/GR windows.*

---

## Abstract

This repository presents **General Mechanics (GM)** as a framework derived from a single principle: the **generalized Stokes identity on an informational manifold**. By combining that geometric bookkeeping with thermodynamic and information-theoretic constraints, the framework reconstructs canonical rate equations, inverse-area boundary-field scaling, and wave-like transport laws. A constant-free, one-datum calibration maps the informational field to measured sectors while keeping the core derivation manifold-theoretic.

In addition to the theory text, this repository includes an **AF-compliant numerical verification layer** for selected GM corollaries. The current test set covers:

- **Macro (Solar window):** Mercury perihelion advance, Solar-limb light deflection, Solar surface redshift, and an off-limb shape comparison.
- **Micro (Hydrogen window):** Electron Kz frequency and hydrogen shell radii derived from time-information and least-action constraints.
- **Macro (Galactic / GR comparison window):** Flat-rotation comparison between classical Keplerian falloff, a rigorous weak-field unit-derivative comparison layer, and the GM dimensional-flow summary.

Each test is written as a scope-tight **corollary**, with declared modelling choices, explicit provenance, and a concrete falsification hook.

---

## Conceptual Stance

GM is **relational** and **axiomatic**. Distinctions generate relations; geometry is used as a tool for reading boundary structure, not as an imported law. In the verification layer, AFC bookkeeping is treated as **finite, discrete, and ternary** (`yes / no / unknown`). Smooth differential expressions appear as derived tools or numerical comparison layers, not as foundational primitives.

This repository therefore combines three layers:

1. **GM theory:** generalized Stokes on an informational manifold.
2. **AF protocol:** axioms, consequences, modelling choices, corollaries, and falsification hooks.
3. **AFC bookkeeping:** discrete Stokes balance and ternary counting used to keep the derivations traceable.

---

## Temporal Kz Convention

GM uses **Kz units** as an explicit temporal convention. Quantities are not obtained by setting `h = 1`. Instead, measured quantities are mapped into Kz form by explicit division by Planck's constant:

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
f_{\mathrm{Kz}}(M) \equiv m_{\mathrm{Kz}}(M) = \frac{M c^2}{h},
\]

so a mass given in kilograms is represented in **Kz / Hz** through its rest-energy rate. Speeds are handled through the dimensionless ratio

\[
\beta = \frac{v}{c} \in [0,1].
\]

For numerical comparisons, the tests use an SI-2018 dictionary layer while leaving the GM corollaries written in Kz form.

---

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

- **Corollary IV:** Electron Kz frequency from the Sunit dictionary.
- **Corollary V:** Hydrogen shell radii from time-information plus least-action closure, compared to the \(r_n = n^2 a_0\) scaling.

### Galactic / GR comparison

The extended macro window compares three summaries outside the core radius:

- classical Keplerian falloff,
- a rigorous weak-field comparison layer that keeps the relevant unit-derivative term,
- the GM dimensional-flow summary.

The purpose of this section is a **GM update with a GR comparison**.

---

## Repository Contents

- `notebooks/` — numerical verification notebooks for the Solar, Hydrogen, and Galactic / GR comparison windows.
- `preamble.tex` — shared notation and Kz macros.
- `CITATION.cff` — citation metadata for repository and manuscript references.
- manuscript sources / exports for the main **General Mechanics** text and related AF / AFC support material.

---

## Relationship to the Theory Texts

This repository operationalizes consequences derived in the main **General Mechanics** manuscript and follows the author/reviewer discipline set by **Axiomatic Fundamentalism**. It also uses **AFC** as a bookkeeping layer for finite distinctions, discrete Stokes balance, and ternary counting.

### Primary references

- Reginald, P. (2025). *General Mechanics*. Zenodo.  
  <https://doi.org/10.5281/zenodo.17561404>

- Reginald, P. (2025). *Axiomatic Fundamentalism (AF): A Logical Protocol for Traceable Research*. Zenodo.  
  <https://doi.org/10.5281/zenodo.17561186>

- Reginald, P. (2025). *Axiomatic Fundamentalism Calculus (AFC): The Hidden Form of Stokes*. Zenodo.  
  <https://doi.org/10.5281/zenodo.17807779>

- NIST. *Unit Conversion: kg to Hz*.  
  <https://physics.nist.gov/cgi-bin/cuu/Convert?exp=0&num=1&From=kg&To=hz&Action=Convert+value+and+show+factor>

---

## AF / AFC Writing Discipline

The verification notebooks follow the same author/reviewer structure used in the texts:

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
- The numerical layer embeds the model into **SI-2018** for comparison with catalog data.
- Agreement in a shared weak-field or small-gradient regime is treated as a **consistency result**, not by itself as a unique discriminator.

---

## Citation

If this repository is used in research, please cite the Zenodo record for the repository together with the primary *General Mechanics* manuscript DOI listed above.

---

## License

Released under the MIT License. See `LICENSE`.
