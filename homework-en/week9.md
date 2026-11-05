# week9

> **Theorem 1.5.7 (Monotone Convergence Theorem)**
> 
> If $0\le{f}_{n}$ and $f_{n}\uparrow{f}$ pointwise, then $\int{f}_{n}\,\mathrm{d}\mu\uparrow\int{f}\,\mathrm{d}\mu$.

> **Theorem 1.6.4 (Chebyshev's Inequality)**
> 
> If $\phi:\mathbb{R}\to\mathbb{R}$ is nonnegative and nondecreasing with $\phi\left(a\right)>0$, then $P\left(X\ge{a}\right)\le{E}\phi\left(X\right)/\phi\left(a\right)$. Taking $\phi\left(y\right)=y$ gives Markov's inequality $P\left(Y>{}a\right)\le{E}Y/a$.

> **Theorem 1.6.9 (Change of Variables Formula)**
> 
> If $X$ has density $f$ (on $\left[0,1\right]$) and $U_{1}$ is uniform on $\left(0,1\right)$, then $Ef\left(U_{1}\right)=\int_{0}^{1}f\left(x\right)\,\mathrm{d}x$. More generally, $Ef\left(X\right)=\int{f}\left(y\right)\,\mu\left(\mathrm{d}y\right)$, where $\mu$ is the distribution of $X$.

> **Theorem 1.7.2 (Fubini/Tonelli Theorem)**
> 
> For a nonnegative measurable $h$ and any random variable $X$, if $H\left(x\right)=\int_{\left(-\infty,x\right]}h\left(y\right)\,\mathrm{d}y$, then by Tonelli's theorem

$$
EH\left(X\right)=\int_{-\infty}^{\infty}h\left(y\right)P\left(X\ge{y}\right)\,\mathrm{d}y.
$$
(The half-open interval includes the right endpoint, so the tail uses $X\ge{y}$; this generalizes Lemma 2.2.13, recovered by taking $h\left(y\right)=py^{p-1}\mathbf{1}_{\left\{y\ge0\right\}}$.)

> **Lemma 2.2.13 (Tail Formula for Moments)**
> 
> If $Y\ge0$ and $p>0$, then

$$
E\left(Y^{p}\right)=\int_{0}^{\infty}py^{p-1}P\left(Y>{}y\right)\,\mathrm{d}y.
$$
This embodies the idea of "integrating layer by layer over the tail $P\left(Y>{}y\right)$".

## 1

Let $f$ be measurable on $\left[0,1\right]$ with

$$
\int_{0}^{1}\left|f\left(x\right)\right|^{2}\,\mathrm{d}x<\infty.
$$

Let $U_{1},U_{2},\dots$ be independent and uniform on $\left[0,1\right]$, set

$$
I_{n}=n^{-1}\left(f\left(U_{1}\right)+\dots+f\left(U_{n}\right)\right),
$$

and

$$
I=\int_{0}^{1}f\left(x\right)\,\mathrm{d}x.
$$

Use Chebyshev's inequality to estimate $P\left(\left|I_{n}-I\right|>{}a/n^{1/2}\right)$.

### Solution to 1

Since $U_{1}$ is uniform on $\left(0,1\right)$, by **Theorem 1.6.9 (Change of Variables Formula)**,

$$
Ef\left(U_{1}\right)=\int_{0}^{1}f\left(x\right)\,\mathrm{d}x=I,
$$

so $EI_{n}=I$. Let

$$
\sigma^{2}=\int_{0}^{1}f\left(x\right)^{2}\,\mathrm{d}x<\infty.
$$

Since the $U_{i}$ are i.i.d.,

$$
\mathrm{var}\left(I_{n}\right)=\frac{1}{n}\mathrm{var}\left(f\left(U_{1}\right)\right)\le\frac{1}{n}Ef\left(U_{1}\right)^{2}=\frac{\sigma^{2}}{n},
$$

where

$$
\mathrm{var}\left(Y\right)=EY^{2}-\left(EY\right)^{2}\le{E}Y^{2}.
$$

By Chebyshev's inequality (**Theorem 1.6.4 (Chebyshev's Inequality)**, taking $\phi\left(x\right)=x^{2}$ with mean $I$),

$$
P\left(\left|I_{n}-I\right|>{}a/n^{1/2}\right)\le\frac{\mathrm{var}\left(I_{n}\right)}{\left(a/n^{1/2}\right)^{2}}\le\frac{\sigma^{2}/n}{a^{2}/n}=\frac{\sigma^{2}}{a^{2}}.
$$

That is,

$$
P\left(\left|I_{n}-I\right|>{}a/n^{1/2}\right)\le\frac{1}{a^{2}}\int_{0}^{1}f\left(x\right)^{2}\,\mathrm{d}x.
$$

$\blacksquare$

## 2

Prove: if $X\ge0$ is integer-valued, then $EX=\sum_{n\ge1}P\left(X\ge{n}\right)$.

### Solution to 2

For any $\omega$, write $X\left(\omega\right)=N$ (a nonnegative integer). Then $\mathbf{1}_{\left\{X\ge{k}\right\}}\left(\omega\right)=1$ iff $k\le{N}$, so

$$
\sum_{k=1}^{\infty}\mathbf{1}_{\left\{X\ge{k}\right\}}\left(\omega\right)=\#\left\{k\ge1:k\le{N}\right\}=N=X\left(\omega\right).
$$

That is,

$$
X=\sum_{k=1}^{\infty}\mathbf{1}_{\left\{X\ge{k}\right\}}
$$

pointwise. Since each term is nonnegative, taking expectations by monotone convergence (**Theorem 1.5.7 (Monotone Convergence Theorem)**) gives

$$
EX=E\left[\sum_{k=1}^{\infty}\mathbf{1}_{\left\{X\ge{k}\right\}}\right]=\sum_{k=1}^{\infty}P\left(X\ge{k}\right),
$$

i.e. $EX=\sum_{n\ge1}P\left(X\ge{n}\right)$. $\blacksquare$

## 3

If $X\ge0$ is integer-valued, write down a similar expression for $EX^{2}$.

### Solution to 3

Using the tail-sum notation,

$$
X=\sum_{k\ge1}\mathbf{1}_{\left\{X\ge{k}\right\}}.
$$

Write $X^{2}$ as a double sum and regroup by $\max$: there are exactly $2n-1$ ordered pairs $\left(i,j\right)$ of positive integers with $\max\left(i,j\right)=n$, so

$$
X^{2}=\left(\sum_{i\ge1}\mathbf{1}_{\left\{X\ge{i}\right\}}\right)\left(\sum_{j\ge1}\mathbf{1}_{\left\{X\ge{j}\right\}}\right)=\sum_{i,j\ge1}\mathbf{1}_{\left\{X\ge\max\left(i,j\right)\right\}}=\sum_{n\ge1}\left(2n-1\right)\mathbf{1}_{\left\{X\ge{n}\right\}}.
$$

Each term is nonnegative, so taking expectations by monotone convergence (**Theorem 1.5.7 (Monotone Convergence Theorem)**) gives

$$
EX^{2}=\sum_{n\ge1}\left(2n-1\right)P\left(X\ge{n}\right).
$$

This is the tail expression for $EX^{2}$. $\blacksquare$
