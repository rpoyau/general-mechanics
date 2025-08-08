# Generalized Stokes Theorem — Quick Reference

The **generalized Stokes theorem** unifies every “integral = boundary integral” result in analysis:

\[
\boxed{\displaystyle
\int_{M} d\omega \,=\, \int_{\partial M} \omega
}
\]

* **\(M\)** A smooth oriented \(k\)-dimensional manifold *with (possibly empty) boundary* \(\partial M\).  
* **\(\omega\)** A smooth differential \((k-1)\)-form on \(M\) that extends (or vanishes) to the boundary.  
* **\(d\)** The exterior derivative, sending \((k-1)\)-forms to \(k\)-forms and obeying \(d^{2}=0\).

---

## 1. How the classics fit inside

| Classical law | Manifold \(M\) | Form \(\omega\) | Resulting \(d\omega\) |
|---------------|----------------|--------------------|-------------------------|
| Fundamental theorem of calculus | Interval \([a,b]\) | \(f(x)\,dx\) | \(f'(x)\,dx^1\) |
| Green’s theorem | Planar region \(D\subset\mathbb R^{2}\) | \(P\,dx+Q\,dy\) | \(\bigl(Q_{x}-P_{y}\bigr)dx\wedge dy\) |
| Classical Stokes (curl) | Surface \(S\subset\mathbb R^{3}\) | \(\mathbf A\cdot d\mathbf r\) | \((\nabla\!	imes\!\mathbf A)\cdot d\mathbf S\) |
| Divergence / Gauss | Volume \(V\subset\mathbb R^{3}\) | \(\mathbf F\cdot d\mathbf S\) | \((\nabla\!\cdot\!\mathbf F)\,dV\) |

---

## 2. Wedge product cheat‑sheet

* **Bilinear & antisymmetric:** \(\alpha\wedge\beta = -\beta\wedge\alpha\), so duplicate directions collapse: \(dx\wedge dx = 0\).
* **Geometric meaning:** \(dx\wedge dy\) represents an oriented area element; wedging \(k\) 1‑forms gives an oriented \(k\)-volume element.
* **Cross‑product link (3‑D):** \(\star(u^{\flat}\wedge v^{\flat}) \leftrightarrow u\times v\).

---

## 3. Minimal proof outline

1. Cover \(M\) by charts; partition unity reduces the integral to Euclidean patches.  
2. In each patch, apply the fundamental theorem of calculus iteratively along one coordinate at a time.  
3. Antisymmetry of the wedge ensures boundary terms cancel except on \(\partial M\).  
4. Patching the local results yields the global statement, independent of chart choices.

---

## 4. Orientation bookkeeping

* Reversing orientation flips the sign on **both** sides of the theorem, so the equality is orientation‑consistent.  
* The induced orientation on \(\partial M\) is the “outward normal first” convention.

---

## 5. Quick physical reading

If \(\omega\) encodes a **flux density**, then \(d\omega\) is its **divergence** (production minus destruction).  
Stokes’ theorem reads:  

> *Total production inside \(M\) equals net flux through the boundary.*

This matches the information‑flux balance clause \(d\!\star\!\mathcal J = \sigma\) in the REOS axiom.

