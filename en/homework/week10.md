# Assignment 10

> **Theorem 1.6.4** (Chebyshev's Inequality)<br>If $\phi:\mathbb R\to\mathbb R$ is nonnegative and nondecreasing and $\phi\left(a\right)> 0$, then $P\left(X\ge a\right)\le E\phi\left(X\right)/\phi\left(a\right)$. Taking $\phi\left(x\right)=x^{2}$ gives $P\left(\left|X-EX\right|\ge a\right)\le\mathrm{var}\left(X\right)/a^{2}$; taking $\phi\left(y\right)=y$ gives Markov's inequality $P\left(Y> a\right)\le EY/a$.

> **Theorem 1.6.9** (Change of Variables)<br>If $X$ has density $f$ (on $\left[0,1\right]$) and $U_{1}$ follows the uniform distribution on $\left(0,1\right)$, then $Ef\left(U_{1}\right)=\int_{0}^{1}f\left(x\right)\,\mathrm{d}x$. More generally, $Ef\left(X\right)=\int f\left(y\right)\,\mu\left(\mathrm{d}y\right)$, where $\mu$ is the distribution of $X$.

> **Formula** (Tail Summation)<br>If $X\ge 0$ is integer-valued, then $X=\sum_{k\ge 1}\mathbf{1}_{\left\{X\ge k\right\}}$, and hence, by monotone convergence, $EX=\sum_{n\ge 1}P\left(X\ge n\right)$.

### Problem 1

Let $f$ be a measurable function on $\left[0,1\right]$ such that

$$
\int_{0}^{1}\left|f\left(x\right)\right|^{2}\,\mathrm{d}x< \infty.
$$

$U_{1},U_{2},\dots$ are independent and each follows the uniform distribution on $\left[0,1\right]$,

$$
I_{n}=n^{-1}\left(f\left(U_{1}\right)+\dots+f\left(U_{n}\right)\right),
$$

$$
I=\int_{0}^{1}f\left(x\right)\,\mathrm{d}x.
$$

Use Chebyshev's inequality to estimate $P\left(\left|I_{n}-I\right|> a/n^{1/2}\right)$.

### Solution to Problem 1

Since $U_{1}$ follows the uniform distribution on $\left(0,1\right)$, by **Theorem 1.6.9** (Change of Variables),

$$
\begin{aligned}&\;\;Ef\left(U_{1}\right)\\
&=\int_{0}^{1}f\left(x\right)\,\mathrm{d}x\\
&=I,
\end{aligned}
$$

so $EI_{n}=I$. Set

$$
\sigma^{2}=\int_{0}^{1}f\left(x\right)^{2}\,\mathrm{d}x< \infty,
$$

Since $U_{i}$ are independent and identically distributed,

$$
\begin{aligned}&\;\;\mathrm{var}\left(I_{n}\right)\\
&=\frac{1}{n}\mathrm{var}\left(f\left(U_{1}\right)\right)\\
&\le\frac{1}{n}Ef\left(U_{1}\right)^{2}\\
&=\frac{\sigma^{2}}{n},
\end{aligned}
$$

where

$$
\begin{aligned}&\;\;\mathrm{var}\left(Y\right)
&=EY^{2}-\left(EY\right)^{2}
&\le EY^{2}.
\end{aligned}
$$

By Chebyshev's inequality (**Theorem 1.6.4**, taking $\phi\left(x\right)=x^{2}$, with mean $I$),

$$
\begin{aligned}&\;\;P\left(\left|I_{n}-I\right|> a/n^{1/2}\right)\\
&\le\frac{\mathrm{var}\left(I_{n}\right)}{\left(a/n^{1/2}\right)^{2}}\\
&\le\frac{\sigma^{2}/n}{a^{2}/n}\\
&=\frac{\sigma^{2}}{a^{2}}.
\end{aligned}
$$

i.e.

$$
P\left(\left|I_{n}-I\right|> a/n^{1/2}\right)\le\frac{1}{a^{2}}\int_{0}^{1}f\left(x\right)^{2}\,\mathrm{d}x.
$$

$\blacksquare$

### Problem 2

Prove that if $X\ge 0$ is integer-valued, then $EX=\sum_{n\ge 1}P\left(X\ge n\right)$.

### Solution to Problem 2

For any $\omega$, write $X\left(\omega\right)=N$ (a nonnegative integer). Then $\mathbf{1}_{\left\{X\ge k\right\}}\left(\omega\right)=1$ if and only if $k\le N$, so

$$
\begin{aligned}&\;\;\sum_{k=1}^{\infty}\mathbf{1}_{\left\{X\ge k\right\}}\left(\omega\right)\\
&=\#\left\{k\ge 1:k\le N\right\}\\
&=N\\
&=X\left(\omega\right).
\end{aligned}
$$

i.e.

$$
X=\sum_{k=1}^{\infty}\mathbf{1}_{\left\{X\ge k\right\}}
$$

holds pointwise. Each term is nonnegative, so taking expectation by the monotone convergence theorem for expectations (**Theorem 1.5.7**):

$$
\begin{aligned}&\;\;EX\\
&=E\left[\sum_{k=1}^{\infty}\mathbf{1}_{\left\{X\ge k\right\}}\right]\\
&=\sum_{k=1}^{\infty}P\left(X\ge k\right),
\end{aligned}
$$

i.e. $EX=\sum_{n\ge 1}P\left(X\ge n\right)$. $\blacksquare$
