# week10

> **Exercise 1.4.1 (Zero Integral Implies Zero Almost Everywhere)**
> 
> If $f\ge0$ and $\int{f}\,\mathrm{d}\mu=0$, then $f=0$ almost everywhere.

> **Theorem 1.5.7 (Monotone Convergence Theorem)**
> 
> If $0\le{f}_{n}$ and $f_{n}\uparrow{f}$ pointwise, then $\int{f}_{n}\,\mathrm{d}\mu\uparrow\int{f}\,\mathrm{d}\mu$.

> **Theorem 1.6.4 (Chebyshev's Inequality)**
> 
> If $\phi:\mathbb{R}\to\mathbb{R}$ is nonnegative and nondecreasing with $\phi\left(a\right)>0$, then $P\left(X\ge{a}\right)\le{E}\phi\left(X\right)/\phi\left(a\right)$. Taking $\phi\left(y\right)=y$ gives Markov's inequality $P\left(Y>{}a\right)\le{E}Y/a$.

> **Theorem 1.7.2 (Fubini/Tonelli Theorem)**
> 
> For a nonnegative measurable $h$ and any random variable $X$, if $H\left(x\right)=\int_{\left(-\infty,x\right]}h\left(y\right)\,\mathrm{d}y$, then by Tonelli's theorem

> **Lemma 2.2.13 (Tail Formula for Moments)**
> 
> If $Y\ge0$ and $p>0$, then

> **Definition 2.3.1 (Convergence in Probability)**
> 
> $X_{n}\to{X}$ in probability means that for every $\varepsilon>0$, $P\left(\left|X_{n}-X\right|>\varepsilon\right)\to0$.

## 1

Generalize **Lemma 2.2.13 (Tail Formula for Moments)** and prove: if

$$
H\left(x\right)=\int_{\left(-\infty,x\right]}h\left(y\right)\,\mathrm{d}y
$$

and $h\left(y\right)\ge0$, then

$$
EH\left(X\right)=\int_{-\infty}^{\infty}h\left(y\right)P\left(X\ge{y}\right)\,\mathrm{d}y.
$$

Derive the corresponding conclusion for the special case $H\left(x\right)=\exp\left(\theta{x}\right)$ ($\theta>0$).

### Solution to 1

Write $H$ in indicator-tail form. Since

$$
H\left(x\right)=\int_{\left(-\infty,x\right]}h\left(y\right)\,\mathrm{d}y,
$$

substituting $X$ gives

$$
H\left(X\right)=\int_{\left(-\infty,X\right]}h\left(y\right)\,\mathrm{d}y=\int_{-\infty}^{\infty}h\left(y\right)\mathbf{1}_{\left\{y\le{X}\right\}}\,\mathrm{d}y=\int_{-\infty}^{\infty}h\left(y\right)\mathbf{1}_{\left\{X\ge{y}\right\}}\,\mathrm{d}y.
$$

The integrand is nonnegative, so by Tonelli's theorem (**Theorem 1.7.2 (Fubini/Tonelli Theorem)**) exchange expectation and integral:

$$
EH\left(X\right)=\int_{-\infty}^{\infty}h\left(y\right)E\left[\mathbf{1}_{\left\{X\ge{y}\right\}}\right]\,\mathrm{d}y=\int_{-\infty}^{\infty}h\left(y\right)P\left(X\ge{y}\right)\,\mathrm{d}y.
$$

For $H\left(x\right)=\exp\left(\theta{x}\right)$ with $\theta>0$, we have $h\left(y\right)=H'\left(y\right)=\theta{e}^{\theta{y}}$, and substitution gives

$$
Ee^{\theta{X}}=\theta\int_{-\infty}^{\infty}e^{\theta{y}}P\left(X\ge{y}\right)\,\mathrm{d}y.
$$

$\blacksquare$

## 2

Prove (a) that

$$
d\left(X,Y\right)=E\left(\frac{\left|X-Y\right|}{1+\left|X-Y\right|}\right)
$$

defines a metric on the space of random variables, i.e. it satisfies:

(1) $d\left(X,Y\right)=0$ iff $X=Y$ almost everywhere;

(2) $d\left(X,Y\right)=d\left(Y,X\right)$;

(3) $d\left(X,Z\right)\le{d}\left(X,Y\right)+d\left(Y,Z\right)$;

(b) $d\left(X_{n},X\right)\to0$ ($n\to\infty$) iff $X_{n}\to{X}$ in probability.

### Solution to 2

Let $g\left(t\right)=t/\left(1+t\right)$ ($t\ge0$).

(a)(1) Since $g\ge0$ and $g\left(t\right)=0$ iff $t=0$, by **Exercise 1.4.1 (Zero Integral Implies Zero Almost Everywhere)**,

$$
d\left(X,Y\right)=0\Leftrightarrow{E}\,g\left(\left|X-Y\right|\right)=0\Leftrightarrow{g}\left(\left|X-Y\right|\right)=0\;\text{a.e.}\Leftrightarrow\left|X-Y\right|=0\;\text{a.e.}\Leftrightarrow{X}=Y\;\text{a.e.}
$$

(a)(2) Since $\left|X-Y\right|=\left|Y-X\right|$, immediately $d\left(X,Y\right)=d\left(Y,X\right)$.

(a)(3) Since $g$ is nondecreasing, $\left|X-Z\right|\le\left|X-Y\right|+\left|Y-Z\right|$ implies

$$
g\left(\left|X-Z\right|\right)\le{g}\left(\left|X-Y\right|+\left|Y-Z\right|\right).
$$

Since $g$ is subadditive, $g\left(a+b\right)\le{g}\left(a\right)+g\left(b\right)$,

$$
g\left(\left|X-Z\right|\right)\le{g}\left(\left|X-Y\right|\right)+g\left(\left|Y-Z\right|\right).
$$

Taking expectations gives $d\left(X,Z\right)\le{d}\left(X,Y\right)+d\left(Y,Z\right)$. Thus $d$ is a metric.

(b) First prove "convergence in probability $\Rightarrow$ metric convergence". Suppose $X_{n}\to{X}$ in probability. For $\varepsilon>0$, since $g\le1$ and $g\le{g}\left(\varepsilon\right)$ on $\left[0,\varepsilon\right]$,

$$
d\left(X_{n},X\right)=E\,g\left(\left|X_{n}-X\right|\right)\le{g}\left(\varepsilon\right)P\left(\left|X_{n}-X\right|\le\varepsilon\right)+P\left(\left|X_{n}-X\right|>\varepsilon\right)\le{g}\left(\varepsilon\right)+P\left(\left|X_{n}-X\right|>\varepsilon\right).
$$

Letting $n\to\infty$,

$$
\limsup_{n}d\left(X_{n},X\right)\le{g}\left(\varepsilon\right),
$$

and letting $\varepsilon\to0$ gives $d\left(X_{n},X\right)\to0$.

Now prove "metric convergence $\Rightarrow$ convergence in probability". Suppose $d\left(X_{n},X\right)\to0$. Since $g$ is strictly increasing,

$$
\left\{\left|X_{n}-X\right|>\varepsilon\right\}=\left\{g\left(\left|X_{n}-X\right|\right)>{}g\left(\varepsilon\right)\right\}.
$$

By Markov's inequality (**Theorem 1.6.4 (Chebyshev's Inequality)**),

$$
P\left(\left|X_{n}-X\right|>\varepsilon\right)=P\left(g\left(\left|X_{n}-X\right|\right)>{}g\left(\varepsilon\right)\right)\le\frac{E\,g\left(\left|X_{n}-X\right|\right)}{g\left(\varepsilon\right)}=\frac{d\left(X_{n},X\right)}{g\left(\varepsilon\right)}\to0.
$$

Thus $X_{n}\to{X}$ in probability (**Definition 2.3.1 (Convergence in Probability)**). $\blacksquare$
