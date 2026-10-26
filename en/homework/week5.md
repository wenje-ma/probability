# Assignment 5

> **Definition 1.4.1** (The Four-Step Definition of the Integral)
> 
> Let $\mu$ be a $\sigma$-finite measure on $\left(\Omega,\mathcal F\right)$.
> 
> (1) The integral of a simple function $\phi=\sum_{i}a_{i}\mathbf{1}_{A_{i}}$ ($A_{i}$ pairwise disjoint, $\mu\left(A_{i}\right)< \infty$) is $\int\phi\,\mathrm{d}\mu=\sum_{i}a_{i}\mu\left(A_{i}\right)$;
> 
> (2) the integral of a nonnegative bounded function $f$ vanishing outside a set of finite measure is $\int f\,\mathrm{d}\mu=\sup_{\phi\le f}\int\phi\,\mathrm{d}\mu$;
> 
> (3) the integral of a nonnegative measurable function $f$ is $\int f\,\mathrm{d}\mu=\sup\left\{\int h\,\mathrm{d}\mu:0\le h\le f,\ h\text{ 有界且 }\mu\left(\left\{h> 0\right\}\right)< \infty\right\}$;
> 
> (4) a general measurable function $f$ is called **integrable** if $\int\left|f\right|\,\mathrm{d}\mu< \infty$, and then $\int f\,\mathrm{d}\mu=\int f^{+}\,\mathrm{d}\mu-\int f^{-}\,\mathrm{d}\mu$, where $f^{+}=f\vee 0$, $f^{-}=\left(-f\right)\vee 0$.

> **Theorem 1.4.7** (Basic Properties of the Integral)
> 
> Let $f,g$ be integrable. Then:
> 
> (1) if $f\ge 0$ almost everywhere, then $\int f\,\mathrm{d}\mu\ge 0$;
> 
> (2) for $a\in\mathbb R$, $\int af\,\mathrm{d}\mu=a\int f\,\mathrm{d}\mu$;
> 
> (3) $\int\left(f+g\right)\,\mathrm{d}\mu=\int f\,\mathrm{d}\mu+\int g\,\mathrm{d}\mu$;
> 
> (4) if $g\le f$ almost everywhere, then $\int g\,\mathrm{d}\mu\le\int f\,\mathrm{d}\mu$.

> **Theorem 1.5.7** (Monotone Convergence Theorem)<br>If $0\le f_{n}$ and $f_{n}\uparrow f$ pointwise, then $\int f_{n}\,\mathrm{d}\mu\uparrow\int f\,\mathrm{d}\mu$.

### Problem 1

Prove that if $f\ge 0$ and $\int f\,\mathrm{d}\mu=0$, then $f=0$ almost everywhere.

### Solution to Problem 1

Let $E=\left\{x:f\left(x\right)> 0\right\}$. For each $n\ge 1$, set $E_{n}=\left\{x:f\left(x\right)\ge 1/n\right\}$. Then $E_{n}\uparrow E$, so

$$
\mu\left(E\right)=\lim_{n}\mu\left(E_{n}\right)
$$

(continuity from below of measures, **Theorem 1.1.1** (3)).

Suppose for contradiction that $\mu\left(E\right)> 0$. Then there exists some $n$ such that $\mu\left(E_{n}\right)> 0$. Since $f\ge\left(1/n\right)\mathbf{1}_{E_{n}}$ and by monotonicity of the integral (**Theorem 1.4.7** (1)(4)),

$$
\int f\,\mathrm{d}\mu\ge\int\frac{1}{n}\mathbf{1}_{E_{n}}\,\mathrm{d}\mu=\frac{1}{n}\mu\left(E_{n}\right)> 0,
$$

which contradicts $\int f\,\mathrm{d}\mu=0$. Hence $\mu\left(E\right)=0$, i.e. $f=0$ almost everywhere. $\blacksquare$

### Problem 2

Let $f\ge 0$,

$$
E_{n,m}=\left\{x:m/2^{n}\le f\left(x\right)< \left(m+1\right)/2^{n}\right\}.
$$

Prove that as $n\uparrow\infty$,

$$
\sum_{m=1}^{\infty}\frac{m}{2^{n}}\mu\left(E_{n,m}\right)\uparrow\int f\,\mathrm{d}\mu.
$$

### Solution to Problem 2

For each $n$, define the simple function

$$
f_{n}\left(x\right)=\sum_{m=1}^{\infty}\frac{m}{2^{n}}\mathbf{1}_{E_{n,m}}\left(x\right).
$$

By the definition of $E_{n,m}$, wherever $f$ takes finite values,

$$
f_{n}\left(x\right)\le f\left(x\right)< f_{n}\left(x\right)+2^{-n},
$$

so $f_{n}\uparrow f$ pointwise (the dyadic refinement makes $f_{n}$ nondecreasing and approximate $f$). By the definition of the integral of a simple function (**Definition 1.4.1** (1)),

$$
\int f_{n}\,\mathrm{d}\mu=\sum_{m=1}^{\infty}\frac{m}{2^{n}}\mu\left(E_{n,m}\right).
$$

By **Theorem 1.5.7** (Monotone Convergence Theorem), from $f_{n}\uparrow f$ we get

$$
\sum_{m=1}^{\infty}\frac{m}{2^{n}}\mu\left(E_{n,m}\right)=\int f_{n}\,\mathrm{d}\mu\uparrow\int f\,\mathrm{d}\mu.
$$

This is exactly the conclusion to be proved. $\blacksquare$
