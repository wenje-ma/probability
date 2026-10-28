# week9

> **Theorem 1.6.4 (Chebyshev's Inequality)**<br>If $\phi:\mathbb R\to\mathbb R$ is nonnegative and nondecreasing with $\phi\left(a\right)> 0$, then $P\left(X\ge a\right)\le E\phi\left(X\right)/\phi\left(a\right)$. Taking $\phi\left(x\right)=x^{2}$ gives $P\left(\left|X-EX\right|\ge a\right)\le\mathrm{var}\left(X\right)/a^{2}$.

> **Theorem 2.2.1 (Additivity of Variance for Uncorrelated Variables)**<br>If $X_{1},\dots,X_{n}$ are square-integrable and pairwise uncorrelated, then $\mathrm{var}\left(X_{1}+\dots+X_{n}\right)=\mathrm{var}\left(X_{1}\right)+\dots+\mathrm{var}\left(X_{n}\right)$. For $c\in\mathbb R$, $\mathrm{var}\left(cY\right)=c^{2}\mathrm{var}\left(Y\right)$.

> **Lemma 2.2.2 ($L^{p}$ Convergence Implies Convergence in Probability)**<br>If $p> 0$ and $E\left|Z_{n}\right|^{p}\to 0$, then $Z_{n}\to 0$ in probability. This is a direct consequence of Chebyshev's inequality with $\phi\left(x\right)=x^{p}$.

> **Theorem 2.2.3 ($L^{2}$ Weak Law of Large Numbers)**<br>If $X_{1},X_{2},\dots$ are pairwise uncorrelated, $EX_{i}=\mu$, $\mathrm{var}\left(X_{i}\right)\le C< \infty$, and $S_{n}=X_{1}+\dots+X_{n}$, then as $n\to\infty$, $S_{n}/n\to\mu$ in $L^{2}$ and in probability.

---

## 1

Let $X_{1},X_{2},\dots$ be pairwise uncorrelated, $EX_{i}=\mu_{i}$, and $\mathrm{var}\left(X_{i}\right)/i\to 0$ as $i\to\infty$. Let $S_{n}=X_{1}+\dots+X_{n}$ and $\nu_{n}=ES_{n}/n$. Prove that as $n\to\infty$, $S_{n}/n-\nu_{n}\to 0$ in $L^{2}$ and in probability.

### Solution 1

By linearity of expectation, $E\left(S_{n}/n\right)=\nu_{n}$, so

$$
E\left(\frac{S_{n}}{n}-\nu_{n}\right)^{2}=\mathrm{var}\left(\frac{S_{n}}{n}\right)=\frac{1}{n^{2}}\mathrm{var}\left(S_{n}\right).
$$

Since the $X_{i}$ are pairwise uncorrelated, by **Theorem 2.2.1 (Additivity of Variance for Uncorrelated Variables)**,

$$
\mathrm{var}\left(S_{n}\right)=\sum_{i=1}^{n}\mathrm{var}\left(X_{i}\right).
$$

We now show that

$$
\frac{1}{n^{2}}\sum_{i=1}^{n}\mathrm{var}\left(X_{i}\right)\to 0.
$$

Since $\mathrm{var}\left(X_{i}\right)/i\to 0$, for any $\varepsilon> 0$ there exists $N$ such that $\mathrm{var}\left(X_{i}\right)< \varepsilon i$ for $i\ge N$. Hence

$$
\frac{1}{n^{2}}\sum_{i=1}^{n}\mathrm{var}\left(X_{i}\right)\le\frac{1}{n^{2}}\sum_{i< N}\mathrm{var}\left(X_{i}\right)+\frac{\varepsilon}{n^{2}}\sum_{i=N}^{n}i\le\frac{C}{n^{2}}+\frac{\varepsilon}{n^{2}}\cdot\frac{n\left(n+1\right)}{2},
$$

where

$$
C=\sum_{i< N}\mathrm{var}\left(X_{i}\right)
$$

is a constant. Letting $n\to\infty$,

$$
\limsup_{n}\frac{1}{n^{2}}\sum_{i=1}^{n}\mathrm{var}\left(X_{i}\right)\le\varepsilon/2,
$$

and letting $\varepsilon\to 0$ gives the limit $0$. Thus $S_{n}/n-\nu_{n}\to 0$ in $L^{2}$.

By **Lemma 2.2.2 ($L^{p}$ Convergence Implies Convergence in Probability)** (taking $p=2$ and $Z_{n}=S_{n}/n-\nu_{n}$), $L^{2}$ convergence implies convergence in probability, so $S_{n}/n-\nu_{n}\to 0$ in probability. $\blacksquare$

---

## 2

The $L^{2}$ weak law extends to certain dependent sequences. Suppose $EX_{n}=0$, and for $m\le n$, $EX_{n}X_{m}\le r\left(n-m\right)$ (without absolute value on the left!), where $r\left(k\right)\to 0$ as $k\to\infty$. Prove that $\left(X_{1}+\dots+X_{n}\right)/n\to 0$ in probability.

### Solution 2

Let $S_{n}=X_{1}+\dots+X_{n}$. Since $EX_{n}=0$, $E\left(S_{n}/n\right)=0$. Expand $E\left(S_{n}^{2}\right)$:

$$
E\left(S_{n}^{2}\right)=\sum_{i=1}^{n}EX_{i}^{2}+\sum_{i\ne j}E\left(X_{i}X_{j}\right).
$$

Taking $m=n=i$ in the hypothesis gives $EX_{i}^{2}\le r\left(0\right)$, so the diagonal terms satisfy

$$
\sum_{i}EX_{i}^{2}\le n\,r\left(0\right).
$$

For the cross terms, when $i\ne j$: if $i< j$, the hypothesis directly gives $E\left(X_{i}X_{j}\right)\le r\left(j-i\right)$; if $i> j$, using $E\left(X_{i}X_{j}\right)=E\left(X_{j}X_{i}\right)$ and $j< i$, the hypothesis gives $E\left(X_{j}X_{i}\right)\le r\left(i-j\right)$. Hence for all $i\ne j$, $E\left(X_{i}X_{j}\right)\le r\left(\left|i-j\right|\right)$, and therefore

$$
\sum_{i\ne j}E\left(X_{i}X_{j}\right)\le\sum_{i\ne j}r\left(\left|i-j\right|\right)=2\sum_{k=1}^{n-1}\left(n-k\right)r\left(k\right)\le 2n\sum_{k=1}^{n-1}r\left(k\right).
$$

Combining,

$$
E\left(\frac{S_{n}}{n}\right)^{2}=\frac{E\left(S_{n}^{2}\right)}{n^{2}}\le\frac{r\left(0\right)}{n}+\frac{2}{n}\sum_{k=1}^{n-1}r\left(k\right).
$$

Since $r\left(k\right)\to 0$, its Cesaro mean

$$
\frac{1}{n}\sum_{k=1}^{n-1}r\left(k\right)\to 0.
$$

Thus $E\left(S_{n}/n\right)^{2}\to 0$, i.e. $S_{n}/n\to 0$ in $L^{2}$, and by **Lemma 2.2.2 ($L^{p}$ Convergence Implies Convergence in Probability)**, $S_{n}/n\to 0$ in probability. $\blacksquare$
