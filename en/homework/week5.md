# week5

> **Theorem 1.1.1 (Properties of Probability Measures)**<br>Let $\mu$ be a probability measure. Then: (1) $\mu\left(\varnothing\right)=0$; (2) countable additivity: for pairwise disjoint $\left\{E_{n}\right\}$, $\mu\left(\bigcup_{n}E_{n}\right)=\sum_{n}\mu\left(E_{n}\right)$; (3) continuity from below: if $E_{n}\uparrow E$, then $\mu\left(E_{n}\right)\uparrow\mu\left(E\right)$.

> **Definition 1.4.1 (Four-Step Definition of the Integral)**<br>Let $\mu$ be a $\sigma$-finite measure on $\left(\Omega,\mathcal F\right)$. (1) For a simple function $\phi=\sum_{i}a_{i}\mathbf{1}_{A_{i}}$ ($A_{i}$ pairwise disjoint, $\mu\left(A_{i}\right)< \infty$), $\int\phi\,\mathrm{d}\mu=\sum_{i}a_{i}\mu\left(A_{i}\right)$; (2) for a nonnegative bounded $f$ vanishing outside a finite-measure set, $\int f\,\mathrm{d}\mu=\sup_{\phi\le f}\int\phi\,\mathrm{d}\mu$; (3) for a nonnegative measurable $f$, $\int f\,\mathrm{d}\mu=\sup\left\{\int h\,\mathrm{d}\mu:0\le h\le f,\ h\text{ bounded and }\mu\left(\left\{h> 0\right\}\right)< \infty\right\}$; (4) for a general measurable $f$, if $\int\left|f\right|\,\mathrm{d}\mu< \infty$ then $f$ is integrable, and $\int f\,\mathrm{d}\mu=\int f^{+}\,\mathrm{d}\mu-\int f^{-}\,\mathrm{d}\mu$, where $f^{+}=f\vee 0$ and $f^{-}=\left(-f\right)\vee 0$.

> **Theorem 1.4.7 (Basic Properties of the Integral)**<br>Let $f,g$ be integrable. Then: (1) if $f\ge 0$ almost everywhere, then $\int f\,\mathrm{d}\mu\ge 0$; (2) for $a\in\mathbb R$, $\int af\,\mathrm{d}\mu=a\int f\,\mathrm{d}\mu$; (3) $\int\left(f+g\right)\,\mathrm{d}\mu=\int f\,\mathrm{d}\mu+\int g\,\mathrm{d}\mu$; (4) if $g\le f$ almost everywhere, then $\int g\,\mathrm{d}\mu\le\int f\,\mathrm{d}\mu$.

> **Theorem 1.5.7 (Monotone Convergence Theorem)**<br>If $0\le f_{n}$ and $f_{n}\uparrow f$ pointwise, then $\int f_{n}\,\mathrm{d}\mu\uparrow\int f\,\mathrm{d}\mu$.

---

## 1

Prove: if $f\ge 0$ and $\int f\,\mathrm{d}\mu=0$, then $f=0$ almost everywhere.

### Solution 1

Let $E=\left\{x:f\left(x\right)> 0\right\}$. For each $n\ge 1$, set $E_{n}=\left\{x:f\left(x\right)\ge 1/n\right\}$; then $E_{n}\uparrow E$, so

$$
\mu\left(E\right)=\lim_{n}\mu\left(E_{n}\right)
$$

(continuity from below of the measure, **Theorem 1.1.1 (Properties of a Probability Measure)**, condition (3)).

Suppose for contradiction that $\mu\left(E\right)> 0$; then there exists $n$ such that $\mu\left(E_{n}\right)> 0$. Since $f\ge\left(1/n\right)\mathbf{1}_{E_{n}}$ and by monotonicity of the integral (**Theorem 1.4.7 (Basic Properties of the Integral)**, conditions (1) and (4)),

$$
\int f\,\mathrm{d}\mu\ge\int\frac{1}{n}\mathbf{1}_{E_{n}}\,\mathrm{d}\mu=\frac{1}{n}\mu\left(E_{n}\right)> 0,
$$

contradicting $\int f\,\mathrm{d}\mu=0$. Hence $\mu\left(E\right)=0$, i.e. $f=0$ almost everywhere. $\blacksquare$

---

## 2

Let $f\ge 0$ and

$$
E_{n,m}=\left\{x:m/2^{n}\le f\left(x\right)< \left(m+1\right)/2^{n}\right\}.
$$

Prove that as $n\uparrow\infty$,

$$
\sum_{m=1}^{\infty}\frac{m}{2^{n}}\mu\left(E_{n,m}\right)\uparrow\int f\,\mathrm{d}\mu.
$$

### Solution 2

For each $n$, define the simple function

$$
f_{n}\left(x\right)=\sum_{m=1}^{\infty}\frac{m}{2^{n}}\mathbf{1}_{E_{n,m}}\left(x\right).
$$

By the definition of $E_{n,m}$, at points where $f$ takes finite values,

$$
f_{n}\left(x\right)\le f\left(x\right)< f_{n}\left(x\right)+2^{-n},
$$

so $f_{n}\uparrow f$ pointwise (dyadic subdivision makes $f_{n}$ nondecreasing and approximate $f$). By the definition of the integral of a simple function (**Definition 1.4.1 (Four-Step Definition of the Integral)**, condition (1)),

$$
\int f_{n}\,\mathrm{d}\mu=\sum_{m=1}^{\infty}\frac{m}{2^{n}}\mu\left(E_{n,m}\right).
$$

By **Theorem 1.5.7 (Monotone Convergence Theorem)**, since $f_{n}\uparrow f$,

$$
\sum_{m=1}^{\infty}\frac{m}{2^{n}}\mu\left(E_{n,m}\right)=\int f_{n}\,\mathrm{d}\mu\uparrow\int f\,\mathrm{d}\mu.
$$

This is exactly the desired conclusion. $\blacksquare$
