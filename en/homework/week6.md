# Assignment 6

> **Theorem 1.6.9** (Change of Variables)<br>Let $X$ be a random element taking values in $\left(S,\mathcal S\right)$ with distribution $\mu$ (i.e. $\mu\left(A\right)=P\left(X\in A\right)$). If $f:\left(S,\mathcal S\right)\to\left(\mathbb R,\mathcal R\right)$ is measurable and $f\ge 0$ or $E\left|f\left(X\right)\right|<\infty$, then $$Ef\left(X\right)=\int_{S}f\left(y\right)\,\mu\left(\mathrm{d}y\right).$$ The proof uses the four-step method: indicator functions, simple functions, nonnegative functions, general functions.

> **Theorem 1.7.2** (Fubini's Theorem)<br>If $f\ge 0$, then (Tonelli) $$\int_{X}\int_{Y}f\,\mu_{2}\left(\mathrm{d}y\right)\mu_{1}\left(\mathrm{d}x\right)=\int_{X\times Y}f\,\mathrm{d}\left(\mu_{1}\times\mu_{2}\right)=\int_{Y}\int_{X}f\,\mu_{1}\left(\mathrm{d}x\right)\mu_{2}\left(\mathrm{d}y\right).$$ If $f$ is integrable, i.e. $\int\left|f\right|\,\mathrm{d}\left(\mu_{1}\times\mu_{2}\right)<\infty$, then the same triple equality holds (Fubini).

### Problem 1

Let the probability measure $\mu$ satisfy

$$
\mu\left(A\right)=\int_{A}f\left(x\right)\,\mathrm{d}x
$$

for all $A\in\mathcal R$. Following the step-by-step proof of **Theorem 1.6.9**, prove that for any $g$ satisfying $g\ge 0$ or

$$
\int\left|g\left(x\right)\right|\,\mu\left(\mathrm{d}x\right)<\infty
$$

we have

$$
\int g\left(x\right)\,\mu\left(\mathrm{d}x\right)=\int g\left(x\right)f\left(x\right)\,\mathrm{d}x.
$$

### Solution to Problem 1

We verify class by class using the four-step method of **Theorem 1.6.9**.

(1) Indicator functions. Let $g=\mathbf{1}_{B}$ ($B\in\mathcal R$). Then by the assumption,

$$
\begin{aligned}&\;\;\int\mathbf{1}_{B}\left(x\right)\,\mu\left(\mathrm{d}x\right)\\
&=\mu\left(B\right)\\
&=\int_{B}f\left(x\right)\,\mathrm{d}x\\
&=\int\mathbf{1}_{B}\left(x\right)f\left(x\right)\,\mathrm{d}x.
\end{aligned}
$$

(2) Simple functions. Let $g=\sum_{m}c_{m}\mathbf{1}_{B_{m}}$ ($c_{m}\in\mathbb R$, $B_{m}\in\mathcal R$). By linearity of the integral and of expectation (**Theorem 1.4.7**),

$$
\begin{aligned}&\;\;\int g\,\mathrm{d}\mu\\
&=\sum_{m}c_{m}\int\mathbf{1}_{B_{m}}\,\mathrm{d}\mu\\
&=\sum_{m}c_{m}\int\mathbf{1}_{B_{m}}f\,\mathrm{d}x\\
&=\int gf\,\mathrm{d}x.
\end{aligned}
$$

(3) Nonnegative functions. Let $g\ge 0$, and take $g_{n}=\left(\left[2^{n}g\right]/2^{n}\right)\wedge n$; then $g_{n}$ is a simple function and $g_{n}\uparrow g$. By (2) and **Theorem 1.5.7** (monotone convergence),

$$
\begin{aligned}&\;\;\int g\,\mathrm{d}\mu\\
&=\lim_{n}\int g_{n}\,\mathrm{d}\mu\\
&=\lim_{n}\int g_{n}f\,\mathrm{d}x\\
&=\int gf\,\mathrm{d}x.
\end{aligned}
$$

(4) General integrable functions. Suppose

$$
\int\left|g\right|\,\mathrm{d}\mu<\infty,
$$

Decompose $g=g^{+}-g^{-}$ with $g^{\pm}\ge 0$. Applying (3) to $g^{+},g^{-}$ gives

$$
\int g^{\pm}\,\mathrm{d}\mu=\int g^{\pm}f\,\mathrm{d}x,
$$

Subtracting gives

$$
\begin{aligned}&\;\;\int g\,\mathrm{d}\mu\\
&=\int g^{+}\,\mathrm{d}\mu-\int g^{-}\,\mathrm{d}\mu\\
&=\int g^{+}f\,\mathrm{d}x-\int g^{-}f\,\mathrm{d}x\\
&=\int gf\,\mathrm{d}x.
\end{aligned}
$$

Combining the four steps gives the conclusion. $\blacksquare$

### Problem 2

If

$$
\int_{X}\int_{Y}\left|f\left(x,y\right)\right|\,\mu_{2}\left(\mathrm{d}y\right)\mu_{1}\left(\mathrm{d}x\right)<\infty,
$$

prove that

$$
\begin{aligned}&\;\;\int_{X}\int_{Y}f\left(x,y\right)\,\mu_{2}\left(\mathrm{d}y\right)\mu_{1}\left(\mathrm{d}x\right)\\
&=\int_{X\times Y}f\,\mathrm{d}\left(\mu_{1}\times\mu_{2}\right)\\
&=\int_{Y}\int_{X}f\left(x,y\right)\,\mu_{1}\left(\mathrm{d}x\right)\mu_{2}\left(\mathrm{d}y\right).
\end{aligned}
$$

### Solution to Problem 2

Let $\nu=\mu_{1}\times\mu_{2}$ be the product measure. By Tonelli's theorem (**Theorem 1.7.2**, the $f\ge 0$ case),

$$
\int_{X\times Y}\left|f\right|\,\mathrm{d}\nu=\int_{X}\int_{Y}\left|f\left(x,y\right)\right|\,\mu_{2}\left(\mathrm{d}y\right)\mu_{1}\left(\mathrm{d}x\right)<\infty,
$$

so $f$ is integrable with respect to $\nu$. By **Theorem 1.7.2** (Fubini), the integrable function $f$ satisfies

$$
\begin{aligned}&\;\;\int_{X}\int_{Y}f\,\mu_{2}\left(\mathrm{d}y\right)\mu_{1}\left(\mathrm{d}x\right)\\
&=\int_{X\times Y}f\,\mathrm{d}\nu\\
&=\int_{Y}\int_{X}f\,\mu_{1}\left(\mathrm{d}x\right)\mu_{2}\left(\mathrm{d}y\right),
\end{aligned}
$$

This is exactly the conclusion to be proved. $\blacksquare$
