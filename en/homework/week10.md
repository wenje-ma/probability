# week10

> **Basic Knowledge: Tail Sum Formula**<br>If $X\ge 0$ is integer-valued, then $X=\sum_{k\ge 1}\mathbf{1}_{\left\{X\ge k\right\}}$, and by monotone convergence $EX=\sum_{n\ge 1}P\left(X\ge n\right)$.

> **Theorem 1.5.7 (Monotone Convergence Theorem)**<br>If $0\le f_{n}$ and $f_{n}\uparrow f$ pointwise, then $\int f_{n}\,\mathrm{d}\mu\uparrow\int f\,\mathrm{d}\mu$.

> **Theorem 1.6.4 (Chebyshev's Inequality)**<br>If $\phi:\mathbb R\to\mathbb R$ is nonnegative and nondecreasing with $\phi\left(a\right)> 0$, then $P\left(X\ge a\right)\le E\phi\left(X\right)/\phi\left(a\right)$. Taking $\phi\left(x\right)=x^{2}$ gives $P\left(\left|X-EX\right|\ge a\right)\le\mathrm{var}\left(X\right)/a^{2}$; taking $\phi\left(y\right)=y$ gives Markov's inequality $P\left(Y> a\right)\le EY/a$.

> **Theorem 1.6.9 (Change of Variables Formula)**<br>If $X$ has density $f$ (on $\left[0,1\right]$) and $U_{1}$ is uniform on $\left(0,1\right)$, then $Ef\left(U_{1}\right)=\int_{0}^{1}f\left(x\right)\,\mathrm{d}x$. More generally, $Ef\left(X\right)=\int f\left(y\right)\,\mu\left(\mathrm{d}y\right)$, where $\mu$ is the distribution of $X$.

---

## 1

Let $f$ be measurable on $\left[0,1\right]$ with

$$
\int_{0}^{1}\left|f\left(x\right)\right|^{2}\,\mathrm{d}x< \infty.
$$

Let $U_{1},U_{2},\dots$ be independent and uniform on $\left[0,1\right]$, set

$$
I_{n}=n^{-1}\left(f\left(U_{1}\right)+\dots+f\left(U_{n}\right)\right),
$$

and

$$
I=\int_{0}^{1}f\left(x\right)\,\mathrm{d}x.
$$

Use Chebyshev's inequality to estimate $P\left(\left|I_{n}-I\right|> a/n^{1/2}\right)$.

### Solution 1

Since $U_{1}$ is uniform on $\left(0,1\right)$, by **Theorem 1.6.9 (Change of Variables Formula)**,

$$
Ef\left(U_{1}\right)=\int_{0}^{1}f\left(x\right)\,\mathrm{d}x=I,
$$

so $EI_{n}=I$. Let

$$
\sigma^{2}=\int_{0}^{1}f\left(x\right)^{2}\,\mathrm{d}x< \infty.
$$

Since the $U_{i}$ are i.i.d.,

$$
\mathrm{var}\left(I_{n}\right)=\frac{1}{n}\mathrm{var}\left(f\left(U_{1}\right)\right)\le\frac{1}{n}Ef\left(U_{1}\right)^{2}=\frac{\sigma^{2}}{n},
$$

where

$$
\mathrm{var}\left(Y\right)=EY^{2}-\left(EY\right)^{2}\le EY^{2}.
$$

By Chebyshev's inequality (**Theorem 1.6.4 (Chebyshev's Inequality)**, taking $\phi\left(x\right)=x^{2}$ with mean $I$),

$$
P\left(\left|I_{n}-I\right|> a/n^{1/2}\right)\le\frac{\mathrm{var}\left(I_{n}\right)}{\left(a/n^{1/2}\right)^{2}}\le\frac{\sigma^{2}/n}{a^{2}/n}=\frac{\sigma^{2}}{a^{2}}.
$$

That is,

$$
P\left(\left|I_{n}-I\right|> a/n^{1/2}\right)\le\frac{1}{a^{2}}\int_{0}^{1}f\left(x\right)^{2}\,\mathrm{d}x.
$$

$\blacksquare$

---

## 2

Prove: if $X\ge 0$ is integer-valued, then $EX=\sum_{n\ge 1}P\left(X\ge n\right)$.

### Solution 2

For any $\omega$, write $X\left(\omega\right)=N$ (a nonnegative integer). Then $\mathbf{1}_{\left\{X\ge k\right\}}\left(\omega\right)=1$ iff $k\le N$, so

$$
\sum_{k=1}^{\infty}\mathbf{1}_{\left\{X\ge k\right\}}\left(\omega\right)=\#\left\{k\ge 1:k\le N\right\}=N=X\left(\omega\right).
$$

That is,

$$
X=\sum_{k=1}^{\infty}\mathbf{1}_{\left\{X\ge k\right\}}
$$

pointwise. Since each term is nonnegative, taking expectations by monotone convergence (**Theorem 1.5.7 (Monotone Convergence Theorem)**) gives

$$
EX=E\left[\sum_{k=1}^{\infty}\mathbf{1}_{\left\{X\ge k\right\}}\right]=\sum_{k=1}^{\infty}P\left(X\ge k\right),
$$

i.e. $EX=\sum_{n\ge 1}P\left(X\ge n\right)$. $\blacksquare$
