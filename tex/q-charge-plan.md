### Quick-patch checklist

(Based on the decision to **fold the Coulomb $Q^{2}$ term into the single energy resource $R^{(E)}$** and drop the “charge-squared” entry everywhere.)

| File (name in `tex/sections/…`)                          | Why it needs a patch                                       | What to change                                                                                                                                                   |
| -------------------------------------------------------- | ---------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **03\_axiom.tex**                                        | Bullet list (example resources) still lists “$E,\,Q^{2}$”. | Replace with a single-resource example like `\(R^{(E)} = m + T + U_{\text{field}}\)`.<br>Add a footnote: “Electrostatic self-energy is absorbed into $R^{(E)}$.” |
| **05\_reos\_equation.tex**                               | Bullet “Charge–squared $R^{(Q)}$” in the potentials list.  | Delete that bullet (or rewrite to say it is folded into energy).                                                                                                 |
| **08\_info\_force.tex**                                  | Example 2 uses $R^{(2)} = Q^{2}$ and $\Lambda_{Q}$.        | Easiest: comment out Example 2.<br>Optional: replace with a one-liner noting that all energy terms share $\Lambda_{E}$.                                          |
| **09\_canonical.tex** (Tbl 9-1)                          | Row “Charge + energy”.                                     | Delete that row so the table now has “Thermo-pair”, “Vacuum 4-mom.”, “Entanglement”.                                                                             |
| **12\_multi\_clock.tex** (Tbl 12-1)                      | Line “$Q^{2}$ ↔ radius $r$”.                               | Remove the row **or** add a remark “usually absorbed into energy resource”.                                                                                      |
| **08\_info\_force.tex** (intro paragraph)                | It says “e.g. $R^{(E)},\,Q^{2}$”.                          | Change to “e.g. $R^{(E)}$ (total energy)”.                                                                                                                       |
| *Any cross-refs* (`\ref{sec:info_force}` text elsewhere) | They might mention separate charge resource.               | Search for “$Q^{2}$” and edit accordingly.                                                                                                                       |

---

### After patches

* **Boxed identities stay unchanged**—they never depended on a separate $Q^{2}$ variable.
* The Maxwell-style (§ 14) and Jacobson (§ 16) derivations already use the total-energy list, so no edits there.
* Section 2 (Kick units) and Appendix B remain correct; they treat charge as dimensionless $\sqrt{\alpha}$, which is fine.

Apply those six micro-edits and the document will be fully self-consistent with the “one energy resource” policy.
