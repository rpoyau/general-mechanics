Here's a clean, copy‑pastable **README.md** tailored to your repo and current LaTeX layout. It reflects AF (Axiomatic Fundamentalism) discipline, the Kz unit convention, glossary/labels split, and your GitHub Actions workflow.

---

```markdown
# General Mechanics (AF‑Pure)

**Status:** Release Candidate  
**Build:** XeLaTeX via `latexmk` (local & CI)  
**Style:** Axiomatic Fundamentalism (AF)—no restatements, single‑label equations, neutral voice.

## Overview

This project develops **General Mechanics** as relational motifs read from a single geometric identity (generalized Stokes) on an informational manifold.  
Core premises:
1. **Relational primacy**
2. **Ternary counting (yes/no/unknown)**
3. **Stokes identity** \(d\,j^{(n)}=\Sigma\)
4. **Info–entropy identification** on boundaries \(j\equiv j_S,\ i\equiv s,\ q=\Tz\,j_S\) (Kz units)

The manuscript is written in **AF‑Pure** style: axioms are stated once, consequences are cited by label, and every displayed relation carries a unique anchor.

---

## Repository layout

```

tex/
main.tex                # Entry point
preamble.tex            # Packages, macros, AF helpers, Kz macros
sections/
01_introduction.tex
02_axioms.tex
03_wave.tex
...
corollaries/
_template_pure.tex    # AF template (Setup, Derivation, ...)
00_info-gas.tex
01_frame-boundary.tex
02_continuity.tex
03_external-drives.tex
04_time-info.tex
05_noise.tex
08_thermo-newton.tex
10_entropic-corrections.tex
...
appendices/
appA_kick.tex         # Kz units & one‑datum calibrations
appB_glossary.tex     # Glossary & Symbols (labels under app:glossary:…)
bibliography.bib        # (if applicable)
.github/workflows/
build-pdf.yml           # CI: builds PDF artifact with TinyTeX + XeLaTeX

````

---

## Build locally

### Requirements
- XeLaTeX (`xelatex`)
- `latexmk`

**macOS (Homebrew)**
```bash
brew install --cask mactex-no-gui
sudo tlmgr update --self && sudo tlmgr install latexmk
````

**Ubuntu / Debian**

```bash
sudo apt-get update
sudo apt-get install -y texlive-xetex latexmk
```

**TinyTeX (cross‑platform, minimal)**

```bash
# one-liner from Yihui
wget -qO- "https://yihui.org/tinytex/install-bin-unix.sh" | sh
~/bin/tlmgr install latex-bin xetex collection-fontsrecommended latexmk
```

### Compile

```bash
cd tex
latexmk -xelatex -interaction=nonstopmode -halt-on-error main.tex
# Output: tex/main.pdf
```

### Clean

```bash
latexmk -C
```

---

## Continuous Integration (GitHub Actions)

Workflow: `.github/workflows/build-pdf.yml`

* Triggers: `push` to `main` (paths: `tex/**`) and PRs touching `tex/**`.
* Installs TinyTeX, compiles `tex/main.tex`, uploads `main.pdf` with a datestamped name.

**Troubleshooting “Repository not found” (checkout step):**

* Ensure the repository actually exists at `owner/repo` used by GitHub (log shows `rpoyau/general-mechanics`).
* If the repo was renamed or is under a different org, update the remote on GitHub rather than in the workflow.
* For **private** repos, the default `GITHUB_TOKEN` must have `contents: read` (default). If you still see the error, make sure Actions are enabled in repo settings and that the default branch is `main` (not `master`).
* For PRs from forks, you may need to enable “Allow GitHub Actions to run for fork pull requests” in repository settings.

---

## AF discipline (authoring rules)

* **Do not restate** axioms; **cite by label** (e.g., `\eqref{axioms:stokes:identity:eq}`).
* **One equation → one label** (primary/specialization/calibration).
* **No range cites** like “§§a–b”; cite precise labels only.
* **Appendix B** hosts definitions and symbols; **do not** reuse the `axioms:` namespace there.

  * Glossary labels: `app:glossary:window`, `app:glossary:frame`, `app:glossary:worldtube`, `app:glossary:directional-split`, etc.

---

## Units (Kz) & macros

Kz units divide SI quantities by Planck’s constant (h). Key macros (see `preamble.tex`):

* `\Kz` → unit symbol (s⁻¹)
* `\Tz` and `\Pz` → **preferred** Kz temperature (k_B T/h) and power (P/h) (ensure these are defined or aliased)
* Back‑compat (if present): `\Tkz`, `\Pkz`. Prefer `\Tz`, `\Pz` in new text.
* **Boundary heat**: (q=\Tz,j_S). (Used in the body and indexed in App. A eq. `\eqref{app:kick:eq:kz-map}`.)

**Important disambiguation**

* (P) (plain `P`) in Section 4.7/08 is the **canonical momentum** in the Poincaré–Cartan form.
* `\Pz` is the **Kz power budget** used in time–information/erasure bounds.
  Add a comment when both appear in the same subsection (Appendix B already flags this).

If you introduced `\Tz`/`\Pz` recently, verify that `preamble.tex` defines:

```tex
\newcommand{\Tz}{\Tkz} % or explicit k_B T / h if you prefer
\newcommand{\Pz}{\Pkz}
```

so legacy content (`\Tkz`, `\Pkz`) and new content (`\Tz`, `\Pz`) are consistent.

---

## Adding a corollary (template)

Use `corollaries/_template_pure.tex` and keep the AF paragraphs:

* **Setup.** (declarative)
* **Derivation.** (labels only, no restatement)
* **Specialization.** (optional)
* **Calibration.** (optional, cite one‑datum scale from App. A)
* **Falsification.** (operational hook)
* **Provenance.** (internal labels only)
* **Literature note.** (concise, external)

Example anchor pattern:

```tex
\begin{equation}
\label{corollary:[LABEL]:eq:primary}
\end{equation}
```

---

## Label namespaces

* **Axioms:** `axioms:...`
* **Corollaries:** `corollary:[name]:...`
* **Appendix A:** `app:kick:eq:...`
* **Appendix B (Glossary/Symbols):** `app:glossary:...`
  *Do not use* `axioms:` in Appendix B to avoid collision/ambiguity.

---

## Quality checklist (pre‑release)

* [ ] `latexmk` finishes **without** “multiply defined” or “undefined reference” warnings.
* [ ] All Kz references use `\Tz` / `\Pz` and cite App. A mapping: `\eqref{app:kick:eq:kz-map}` where needed.
* [ ] Appendix B glossary links (e.g., `app:glossary:directional-split`) resolve from the body.
* [ ] No restated axioms in corollaries; only label citations.
* [ ] Canonical momentum (P) vs. Kz power `\Pz` disambiguated in text where both appear.

---

## Contributing

* Branch names: `feat/...`, `fix/...`, `refactor/...`, `doc/...`
* Commit messages: imperative present (“Add AF calibration…”, “Fix duplicate label…”)
* Open a PR; the CI will attach the compiled PDF as an artifact
* Keep **no‑figure** directive unless explicitly lifted; use boxes/frames sparingly and only where AF helps readability.

---

## License & citation

> *(Fill in your preferred license—MIT/BSD/CC BY‑SA—or remove this section.)*

If you use or extend this framework, please cite the `general-mechanics` manuscript (latest datestamped PDF artifact) and the AF template.

---

## Acknowledgments

AF discipline, Kz mapping (`App. A`), and the glossary split (`App. B`) substantially improved structure and reproducibility.

```

---

If you want, I can also generate a minimal **CONTRIBUTING.md** and a one‑page **AF authoring cheat‑sheet** to live next to this README.
```
