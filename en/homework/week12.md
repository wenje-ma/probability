# week12

> **Basic Knowledge: Properties of $g\left(t\right)=t/\left(1+t\right)$**<br>For $t\ge 0$, $g$ satisfies: $g\left(t\right)=0\iff t=0$; $g$ is strictly increasing and $g\le 1$; $g$ is subadditive: $g\left(a+b\right)\le g\left(a\right)+g\left(b\right)$.

> **Exercise 1.4.1 (Zero Integral Implies Zero Almost Everywhere)**<br>If $f\ge 0$ and $\int f\,\mathrm{d}\mu=0$, then $f=0$ almost everywhere.

> **Theorem 1.6.4 (Chebyshev's Inequality)**<br>If $\phi:\mathbb R\to\mathbb R$ is nonnegative and nondecreasing with $\phi\left(a\right)> 0$, then $P\left(X\ge a\right)\le E\phi\left(X\right)/\phi\left(a\right)$. Taking $\phi\left(y\right)=y$ gives Markov's inequality $P\left(Y> a\right)\le EY/a$.

> **Definition 2.3.1 (Convergence in Probability)**<br>$X_{n}\to X$ in probability means that for every $\varepsilon> 0$, $P\left(\left|X_{n}-X\right|> \varepsilon\right)\to 0$.

---

## 1

Prove (a) that

$$
d\left(X,Y\right)=E\left(\frac{\left|X-Y\right|}{1+\left|X-Y\right|}\right)
$$

defines a metric on the space of random variables, i.e. it satisfies:

(1) $d\left(X,Y\right)=0$ iff $X=Y$ almost everywhere;

(2) $d\left(X,Y\right)=d\left(Y,X\right)$;

(3) $d\left(X,Z\right)\le d\left(X,Y\right)+d\left(Y,Z\right)$;

(b) $d\left(X_{n},X\right)\to 0$ ($n\to\infty$) iff $X_{n}\to X$ in probability.

### Solution 1

Let $g\left(t\right)=t/\left(1+t\right)$ ($t\ge 0$).

(a)(1) Since $g\ge 0$ and $g\left(t\right)=0$ iff $t=0$, by **Exercise 1.4.1 (Zero Integral Implies Zero Almost Everywhere)**,

$$
d\left(X,Y\right)=0\iff E\,g\left(\left|X-Y\right|\right)=0\iff g\left(\left|X-Y\right|\right)=0\ \text{a.e.}\iff\left|X-Y\right|=0\ \text{a.e.}\iff X=Y\ \text{a.e.}
$$

(a)(2) Since $\left|X-Y\right|=\left|Y-X\right|$, immediately $d\left(X,Y\right)=d\left(Y,X\right)$.

(a)(3) Since $g$ is nondecreasing, $\left|X-Z\right|\le\left|X-Y\right|+\left|Y-Z\right|$ implies

$$
g\left(\left|X-Z\right|\right)\le g\left(\left|X-Y\right|+\left|Y-Z\right|\right).
$$

Since $g$ is subadditive, $g\left(a+b\right)\le g\left(a\right)+g\left(b\right)$,

$$
g\left(\left|X-Z\right|\right)\le g\left(\left|X-Y\right|\right)+g\left(\left|Y-Z\right|\right).
$$

Taking expectations gives $d\left(X,Z\right)\le d\left(X,Y\right)+d\left(Y,Z\right)$. Thus $d$ is a metric.

(b) First prove "convergence in probability $\Rightarrow$ metric convergence". Suppose $X_{n}\to X$ in probability. For $\varepsilon> 0$, since $g\le 1$ and $g\le g\left(\varepsilon\right)$ on $\left[0,\varepsilon\right]$,

$$
d\left(X_{n},X\right)=E\,g\left(\left|X_{n}-X\right|\right)\le g\left(\varepsilon\right)P\left(\left|X_{n}-X\right|\le\varepsilon\right)+P\left(\left|X_{n}-X\right|> \varepsilon\right)\le g\left(\varepsilon\right)+P\left(\left|X_{n}-X\right|> \varepsilon\right).
$$

Letting $n\to\infty$,

$$
\limsup_{n}d\left(X_{n},X\right)\le g\left(\varepsilon\right),
$$

and letting $\varepsilon\to 0$ gives $d\left(X_{n},X\right)\to 0$.

Now prove "metric convergence $\Rightarrow$ convergence in probability". Suppose $d\left(X_{n},X\right)\to 0$. Since $g$ is strictly increasing,

$$
\left\{\left|X_{n}-X\right|> \varepsilon\right\}=\left\{g\left(\left|X_{n}-X\right|\right)> g\left(\varepsilon\right)\right\}.
$$

By Markov's inequality (**Theorem 1.6.4 (Chebyshev's Inequality)**),

$$
P\left(\left|X_{n}-X\right|> \varepsilon\right)=P\left(g\left(\left|X_{n}-X\right|\right)> g\left(\varepsilon\right)\right)\le\frac{E\,g\left(\left|X_{n}-X\right|\right)}{g\left(\varepsilon\right)}=\frac{d\left(X_{n},X\right)}{g\left(\varepsilon\right)}\to 0.
$$

Thus $X_{n}\to X$ in probability (**Definition 2.3.1 (Convergence in Probability)**). $\blacksquare$
