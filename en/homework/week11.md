# week11

> **Theorem 1.5.7 (Monotone Convergence Theorem)**<br>If $0\le f_{n}$ and $f_{n}\uparrow f$ pointwise, then $\int f_{n}\,\mathrm{d}\mu\uparrow\int f\,\mathrm{d}\mu$.

> **Theorem 1.7.2 (Fubini/Tonelli Theorem)**<br>For a nonnegative measurable $h$ and any random variable $X$, if $H\left(x\right)=\int_{\left(-\infty,x\right]}h\left(y\right)\,\mathrm{d}y$, then by Tonelli's theorem

$$
EH\left(X\right)=\int_{-\infty}^{\infty}h\left(y\right)P\left(X\ge y\right)\,\mathrm{d}y.
$$

(The half-open interval includes the right endpoint, so the tail uses $X\ge y$; this generalizes Lemma 2.2.13, recovered by taking $h\left(y\right)=py^{p-1}\mathbf{1}_{\left\{y\ge 0\right\}}$.)

> **Lemma 2.2.13 (Tail Formula for Moments)**<br>If $Y\ge 0$ and $p> 0$, then

$$
E\left(Y^{p}\right)=\int_{0}^{\infty}py^{p-1}P\left(Y> y\right)\,\mathrm{d}y.
$$

This embodies the idea of "integrating layer by layer over the tail $P\left(Y> y\right)$".

---

## 1

If $X\ge 0$ is integer-valued, write down a similar expression for $EX^{2}$.

### Solution 1

Using the tail-sum notation,

$$
X=\sum_{k\ge 1}\mathbf{1}_{\left\{X\ge k\right\}}.
$$

Write $X^{2}$ as a double sum and regroup by $\max$: there are exactly $2n-1$ ordered pairs $\left(i,j\right)$ of positive integers with $\max\left(i,j\right)=n$, so

$$
X^{2}=\left(\sum_{i\ge 1}\mathbf{1}_{\left\{X\ge i\right\}}\right)\left(\sum_{j\ge 1}\mathbf{1}_{\left\{X\ge j\right\}}\right)=\sum_{i,j\ge 1}\mathbf{1}_{\left\{X\ge\max\left(i,j\right)\right\}}=\sum_{n\ge 1}\left(2n-1\right)\mathbf{1}_{\left\{X\ge n\right\}}.
$$

Each term is nonnegative, so taking expectations by monotone convergence (**Theorem 1.5.7 (Monotone Convergence Theorem)**) gives

$$
EX^{2}=\sum_{n\ge 1}\left(2n-1\right)P\left(X\ge n\right).
$$

This is the tail expression for $EX^{2}$. $\blacksquare$

---

## 2

Generalize **Lemma 2.2.13 (Tail Formula for Moments)** and prove: if

$$
H\left(x\right)=\int_{\left(-\infty,x\right]}h\left(y\right)\,\mathrm{d}y
$$

and $h\left(y\right)\ge 0$, then

$$
EH\left(X\right)=\int_{-\infty}^{\infty}h\left(y\right)P\left(X\ge y\right)\,\mathrm{d}y.
$$

Derive the corresponding conclusion for the special case $H\left(x\right)=\exp\left(\theta x\right)$ ($\theta> 0$).

### Solution 2

Write $H$ in indicator-tail form. Since

$$
H\left(x\right)=\int_{\left(-\infty,x\right]}h\left(y\right)\,\mathrm{d}y,
$$

substituting $X$ gives

$$
H\left(X\right)=\int_{\left(-\infty,X\right]}h\left(y\right)\,\mathrm{d}y=\int_{-\infty}^{\infty}h\left(y\right)\mathbf{1}_{\left\{y\le X\right\}}\,\mathrm{d}y=\int_{-\infty}^{\infty}h\left(y\right)\mathbf{1}_{\left\{X\ge y\right\}}\,\mathrm{d}y.
$$

The integrand is nonnegative, so by Tonelli's theorem (**Theorem 1.7.2 (Fubini/Tonelli Theorem)**) exchange expectation and integral:

$$
EH\left(X\right)=\int_{-\infty}^{\infty}h\left(y\right)E\left[\mathbf{1}_{\left\{X\ge y\right\}}\right]\,\mathrm{d}y=\int_{-\infty}^{\infty}h\left(y\right)P\left(X\ge y\right)\,\mathrm{d}y.
$$

For $H\left(x\right)=\exp\left(\theta x\right)$ with $\theta> 0$, we have $h\left(y\right)=H'\left(y\right)=\theta e^{\theta y}$, and substitution gives

$$
Ee^{\theta X}=\theta\int_{-\infty}^{\infty}e^{\theta y}P\left(X\ge y\right)\,\mathrm{d}y.
$$

$\blacksquare$
