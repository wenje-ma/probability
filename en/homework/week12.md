# Assignment 12

> **Definition 2.3.1** (Convergence in Probability)<br>$X_{n}\to X$ in probability means that for every $\varepsilon> 0$, $P\left(\left|X_{n}-X\right|> \varepsilon\right)\to 0$.

> **Theorem 1.6.4** (Chebyshev's Inequality)<br>If $\phi:\mathbb R\to\mathbb R$ is nonnegative and nondecreasing and $\phi\left(a\right)> 0$, then $P\left(X\ge a\right)\le E\phi\left(X\right)/\phi\left(a\right)$. Taking $\phi\left(y\right)=y$ gives Markov's inequality $P\left(Y> a\right)\le EY/a$.

> **Problem 1.4.1**<br>If $f\ge 0$ and $\int f\,\mathrm{d}\mu=0$, then $f=0$ almost everywhere.

> **Property** (The Function $g\left(t\right)=t/\left(1+t\right)$)<br>For $t\ge 0$, $g$ satisfies: $g\left(t\right)=0\iff t=0$; $g$ is strictly increasing and $g\le 1$; $g$ is subadditive: $g\left(a+b\right)\le g\left(a\right)+g\left(b\right)$.

### Problem 1

Prove that (a)

$$
d\left(X,Y\right)=E\left(\frac{\left|X-Y\right|}{1+\left|X-Y\right|}\right)
$$

defines a metric on the set of random variables, i.e. it satisfies:

(1) $d\left(X,Y\right)=0$ if and only if $X=Y$ almost everywhere;

(2) $d\left(X,Y\right)=d\left(Y,X\right)$;

(3) $d\left(X,Z\right)\le d\left(X,Y\right)+d\left(Y,Z\right)$;

(b) $d\left(X_{n},X\right)\to 0$ ($n\to\infty$) if and only if $X_{n}\to X$ in probability.

### Solution to Problem 1

Set $g\left(t\right)=t/\left(1+t\right)$ ($t\ge 0$).

(a)(1) Since $g\ge 0$ and $g\left(t\right)=0$ if and only if $t=0$, by **Problem 1.4.1** (a nonnegative function with zero integral is zero almost everywhere),

$$
\begin{aligned}&\;\;d\left(X,Y\right)\\
&=0\\
&\iff E\,g\left(\left|X-Y\right|\right)=0\\
&\iff g\left(\left|X-Y\right|\right)=0\ \text{几乎处处}\\
&\iff\left|X-Y\right|=0\ \text{几乎处处}\\
&\iff X=Y\ \text{几乎处处}
\end{aligned}
$$

(a)(2) Since $\left|X-Y\right|=\left|Y-X\right|$, we immediately get $d\left(X,Y\right)=d\left(Y,X\right)$.

(a)(3) $g$ is nondecreasing, so $\left|X-Z\right|\le\left|X-Y\right|+\left|Y-Z\right|$ implies

$$
g\left(\left|X-Z\right|\right)\le g\left(\left|X-Y\right|+\left|Y-Z\right|\right);
$$

Moreover, $g$ is subadditive, $g\left(a+b\right)\le g\left(a\right)+g\left(b\right)$, so

$$
g\left(\left|X-Z\right|\right)\le g\left(\left|X-Y\right|\right)+g\left(\left|Y-Z\right|\right).
$$

Taking expectation gives $d\left(X,Z\right)\le d\left(X,Y\right)+d\left(Y,Z\right)$. In summary, $d$ is a metric.

(b) We first prove "convergence in probability $\Rightarrow$ metric convergence". Suppose $X_{n}\to X$ in probability. For $\varepsilon> 0$, since $g\le 1$ and on $\left[0,\varepsilon\right]$ we have $g\le g\left(\varepsilon\right)$,

$$
\begin{aligned}&\;\;d\left(X_{n},X\right)\\
&=E\,g\left(\left|X_{n}-X\right|\right)\\
&\le g\left(\varepsilon\right)P\left(\left|X_{n}-X\right|\le\varepsilon\right)+P\left(\left|X_{n}-X\right|> \varepsilon\right)\\
&\le g\left(\varepsilon\right)+P\left(\left|X_{n}-X\right|> \varepsilon\right).
\end{aligned}
$$

Letting $n\to\infty$ gives

$$
\limsup_{n}d\left(X_{n},X\right)\le g\left(\varepsilon\right),
$$

then letting $\varepsilon\to 0$ gives $d\left(X_{n},X\right)\to 0$.

Next, we prove "metric convergence $\Rightarrow$ convergence in probability". Suppose $d\left(X_{n},X\right)\to 0$. Since $g$ is strictly increasing,

$$
\left\{\left|X_{n}-X\right|> \varepsilon\right\}=\left\{g\left(\left|X_{n}-X\right|\right)> g\left(\varepsilon\right)\right\},
$$

by Markov's inequality (**Theorem 1.6.4**),

$$
\begin{aligned}&\;\;P\left(\left|X_{n}-X\right|> \varepsilon\right)\\
&=P\left(g\left(\left|X_{n}-X\right|\right)> g\left(\varepsilon\right)\right)\\
&\le\frac{E\,g\left(\left|X_{n}-X\right|\right)}{g\left(\varepsilon\right)}\\
&=\frac{d\left(X_{n},X\right)}{g\left(\varepsilon\right)}\\
&\to 0.
\end{aligned}
$$

Hence $X_{n}\to X$ in probability (**Definition 2.3.1**). $\blacksquare$
