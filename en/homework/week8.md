# week8

> **Example 1.6.13 (Poisson Distribution)**<br>$Z$ has the Poisson distribution with parameter $\lambda$, written $Z\sim\mathrm{Poisson}\left(\lambda\right)$, meaning $P\left(Z=k\right)=e^{-\lambda}\lambda^{k}/k!$ for $k=0,1,2,\dots$.

> **Theorem 1.7.2 (Fubini's Theorem)**<br>If $f\ge 0$, then (Tonelli) the order of integration in a double integral may be interchanged; if $f$ is integrable, i.e. $\int\left|f\right|\,\mathrm{d}\left(\mu_{1}\times\mu_{2}\right)< \infty$, then the same interchange holds (Fubini).

> **Definition 2.1.2 (Independent Random Variables)**<br>Random variables $X_{1},\dots,X_{n}$ are independent if for any Borel sets $A_{1},\dots,A_{n}$, $P\left(\bigcap_{i}\left\{X_{i}\in A_{i}\right\}\right)=\prod_{i}P\left(X_{i}\in A_{i}\right)$.

> **Definition 2.1.3 (Uncorrelated)**<br>If $EX^{2},EY^{2}< \infty$ and $EXY=EX\cdot EY$, then $X,Y$ are uncorrelated. Independence implies uncorrelatedness, but uncorrelatedness does not imply independence.

> **Exercise 2.1.10 (Convolution Formula)**<br>If $X,Y$ are independent and integer-valued, then $P\left(X+Y=n\right)=\sum_{m}P\left(X=m\right)P\left(Y=n-m\right)$.

> **Theorem 2.1.13 (Expectation of a Product of Independent Variables)**<br>If $X_{1},\dots,X_{n}$ are independent and either (a) each $X_{i}\ge 0$, or (b) each $E\left|X_{i}\right|< \infty$, then

$$
E\left(\prod_{i=1}^{n}X_{i}\right)=\prod_{i=1}^{n}EX_{i}.
$$

> **Theorem 2.1.16 (Density and Independence)**<br>Let $X_{1},\dots,X_{n}$ have joint density $f$. If $f$ can be written as $f\left(x_{1},\dots,x_{n}\right)=g_{1}\left(x_{1}\right)\cdots g_{n}\left(x_{n}\right)$ ($g_{i}\ge 0$ measurable), then $X_{1},\dots,X_{n}$ are independent; conversely, if $X_{1},\dots,X_{n}$ are independent and each has a density, then the joint density is the product of the marginal densities.

---

## 1

Let $\left(X_{1},\dots,X_{n}\right)$ have density $f\left(x_{1},\dots,x_{n}\right)$, i.e.

$$
P\left(\left(X_{1},\dots,X_{n}\right)\in A\right)=\int_{A}f\left(x\right)\,\mathrm{d}x
$$

for $A\in\mathcal R^{n}$. If $f$ can be written as

$$
f\left(x\right)=g_{1}\left(x_{1}\right)\cdots g_{n}\left(x_{n}\right)
$$

($g_{m}\ge 0$ measurable, not necessarily probability densities), prove that $X_{1},\dots,X_{n}$ are independent.

### Solution 1

For any Borel sets $A_{1},\dots,A_{n}$, by the joint density and Tonelli's theorem (**Theorem 1.7.2 (Fubini's Theorem)**, the integrand is nonnegative and separable):

$$
P\left(X_{1}\in A_{1},\dots,X_{n}\in A_{n}\right)=\int_{A_{1}\times\cdots\times A_{n}}f\left(x\right)\,\mathrm{d}x=\prod_{i=1}^{n}\int_{A_{i}}g_{i}\left(x_{i}\right)\,\mathrm{d}x_{i}.
$$

On the other hand, substituting $A_{i}=\mathbb R$ and using that $f$ is a probability density ($\int f=1$),

$$
\prod_{i=1}^{n}\int_{\mathbb R}g_{i}\left(x_{i}\right)\,\mathrm{d}x_{i}=1.
$$

The marginal distribution of $X_{i}$ is

$$
P\left(X_{i}\in A_{i}\right)=\int_{\mathbb R^{n}}\mathbf{1}_{A_{i}}\left(x_{i}\right)g_{1}\left(x_{1}\right)\cdots g_{n}\left(x_{n}\right)\,\mathrm{d}x=\left(\int_{A_{i}}g_{i}\,\mathrm{d}x_{i}\right)\prod_{j\ne i}\int_{\mathbb R}g_{j}\,\mathrm{d}x_{j}.
$$

Hence

$$
\prod_{i=1}^{n}P\left(X_{i}\in A_{i}\right)=\left(\prod_{i=1}^{n}\int_{A_{i}}g_{i}\,\mathrm{d}x_{i}\right)\prod_{i=1}^{n}\prod_{j\ne i}\int_{\mathbb R}g_{j}\,\mathrm{d}x_{j}=\left(\prod_{i=1}^{n}\int_{A_{i}}g_{i}\,\mathrm{d}x_{i}\right)\left(\prod_{j=1}^{n}\int_{\mathbb R}g_{j}\,\mathrm{d}x_{j}\right)^{n-1}.
$$

Since $\prod_{j}\int_{\mathbb R}g_{j}=1$,

$$
\prod_{i}P\left(X_{i}\in A_{i}\right)=\prod_{i}\int_{A_{i}}g_{i}\,\mathrm{d}x_{i}=P\left(X_{1}\in A_{1},\dots,X_{n}\in A_{n}\right).
$$

Since the $A_{i}$ are arbitrary, $X_{1},\dots,X_{n}$ are independent (**Definition 2.1.2 (Independent Random Variables)**). $\blacksquare$

---

## 2

Let $\Omega=\left(0,1\right)$, $\mathcal F$ the Borel sets, and $P$ Lebesgue measure. Prove that $X_{n}\left(\omega\right)=\sin\left(2\pi n\omega\right)$ ($n=1,2,\dots$) are pairwise uncorrelated but not independent.

### Solution 2

First prove pairwise uncorrelatedness. For any positive integer $n$,

$$
EX_{n}=\int_{0}^{1}\sin\left(2\pi n\omega\right)\,\mathrm{d}\omega=0,
$$

(the integral of sine over a full period is zero). For $n\ne m$, by product-to-sum,

$$
\sin\left(2\pi n\omega\right)\sin\left(2\pi m\omega\right)=\frac{1}{2}\left(\cos\left(2\pi\left(n-m\right)\omega\right)-\cos\left(2\pi\left(n+m\right)\omega\right)\right).
$$

And

$$
\int_{0}^{1}\cos\left(2\pi k\omega\right)\,\mathrm{d}\omega=0
$$

for every integer $k\ne 0$ (when $n\ne m$, both $n-m\ne 0$ and $n+m\ne 0$), so

$$
EX_{n}X_{m}=\frac{1}{2}\int_{0}^{1}\left(\cos\left(2\pi\left(n-m\right)\omega\right)-\cos\left(2\pi\left(n+m\right)\omega\right)\right)\,\mathrm{d}\omega=0=EX_{n}EX_{m}.
$$

Thus the $X_{n}$ are pairwise uncorrelated (**Definition 2.1.3 (Uncorrelated)**).

Now prove non-independence. Take $A=\left\{x:x> 1/2\right\}$ and $B=\left\{x:x> \sqrt{3}/2\right\}$. From $\sin\left(2\pi\omega\right)> 1/2$,

$$
2\pi\omega\in\left(\pi/6,5\pi/6\right)\ \left(\mathrm{mod}\ 2\pi\right),
$$

i.e. $\omega\in\left(1/12,5/12\right)$, so $P\left(X_{1}> 1/2\right)=\lambda\left(1/12,5/12\right)=1/3> 0$. From $\sin\left(4\pi\omega\right)> \sqrt{3}/2$,

$$
P\left(X_{2}> \sqrt{3}/2\right)=\lambda\left(\left(1/12,1/6\right)\cup\left(7/12,2/3\right)\right)=1/6> 0.
$$

But when $\omega\in\left(1/12,5/12\right)$, the maximum of $\sin\left(4\pi\omega\right)$ is $\sqrt{3}/2$ (attained at the endpoint $\omega=1/12$), so $X_{1}> 1/2$ implies $X_{2}\le\sqrt{3}/2$, i.e.

$$
P\left(X_{1}> 1/2,\,X_{2}> \sqrt{3}/2\right)=0,
$$

whereas

$$
P\left(X_{1}> 1/2\right)P\left(X_{2}> \sqrt{3}/2\right)=1/3\cdot 1/6> 0.
$$

These are unequal, so $X_{1},X_{2}$ are not independent, and hence the whole sequence $X_{n}$ is not independent (**Definition 2.1.2 (Independent Random Variables)**). $\blacksquare$

---

## 3

Let $X\sim\mathrm{Poisson}\left(\lambda\right)$ and $Y\sim\mathrm{Poisson}\left(\mu\right)$ be independent. Use the convolution formula to prove that $X+Y\sim\mathrm{Poisson}\left(\lambda+\mu\right)$.

### Solution 3

$X,Y$ are independent and nonnegative integer-valued. By the convolution formula (**Exercise 2.1.10 (Convolution Formula)**), for $n\ge 0$,

$$
P\left(X+Y=n\right)=\sum_{m=0}^{n}P\left(X=m\right)P\left(Y=n-m\right)=\sum_{m=0}^{n}\frac{e^{-\lambda}\lambda^{m}}{m!}\cdot\frac{e^{-\mu}\mu^{n-m}}{\left(n-m\right)!}.
$$

Factor out the common term and apply the binomial theorem:

$$
P\left(X+Y=n\right)=\frac{e^{-\left(\lambda+\mu\right)}}{n!}\sum_{m=0}^{n}\frac{n!}{m!\left(n-m\right)!}\lambda^{m}\mu^{n-m}=\frac{e^{-\left(\lambda+\mu\right)}}{n!}\left(\lambda+\mu\right)^{n}.
$$

This is exactly the probability mass function of the Poisson distribution with parameter $\lambda+\mu$ (**Example 1.6.13 (Poisson Distribution)**), so $X+Y\sim\mathrm{Poisson}\left(\lambda+\mu\right)$. $\blacksquare$
