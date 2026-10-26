# Assignment 14

> **Definition 3.3.1** (Characteristic Function)<br>The characteristic function of a random variable $X$ is $\phi_{X}\left(t\right)=Ee^{itX}=\int e^{itx}\,\mu\left(\mathrm{d}x\right)$, where $\mu$ is the distribution of $X$.

> **Theorem 3.3.1** (Properties of Characteristic Functions)
> 
> (1) $\phi\left(0\right)=1$;
> 
> (2) $\phi\left(-t\right)=\overline{\phi\left(t\right)}$;
> 
> (3) $\left|\phi\left(t\right)\right|\le 1$;
> 
> (4) $\left|\phi\left(t+h\right)-\phi\left(t\right)\right|\le E\left|e^{ihX}-1\right|$, so $\phi$ is uniformly continuous on $\mathbb R$;
> 
> (5) $Ee^{it\left(aX+b\right)}=e^{itb}\phi\left(at\right)$.

> **Theorem 3.3.2** (Characteristic Function of an Independent Sum)<br>If $X_{1},X_{2}$ are independent with characteristic functions $\phi_{1},\phi_{2}$, then the characteristic function of $X_{1}+X_{2}$ is $\phi_{1}\left(t\right)\phi_{2}\left(t\right)$.

> **Definition 3.2.1** (Convergence in Distribution)<br>$X_{n}\Rightarrow X_{\infty}$ (convergence in distribution) means that the distribution functions $F_{n}\left(x\right)\to F_{\infty}\left(x\right)$ at every point of continuity of $F_{\infty}$.

> **Theorem 3.2.8** (Skorokhod Representation)<br>If $X_{n}\Rightarrow X_{\infty}$, then there exist random variables $Y_{n}=_{d}X_{n}$ on the same probability space such that $Y_{n}\to Y_{\infty}=_{d}X_{\infty}$ almost surely.

> **Theorem 1.6.5** (Fatou's Lemma)<br>If $Z_{n}\ge 0$, then $E\liminf_{n}Z_{n}\le\liminf_{n}EZ_{n}$.

### Problem 1

Let $X\sim N\left(0,1\right)$, with density $\left(2\pi\right)^{-1/2}e^{-x^{2}/2}$. Complete the in-class calculation of its characteristic function (see **Example 3.3.5**), and prove that $\phi\left(t\right)=Ee^{itX}=e^{-t^{2}/2}$.

### Solution to Problem 1

The characteristic function is

$$
\phi\left(t\right)=\int_{-\infty}^{\infty}e^{itx}\left(2\pi\right)^{-1/2}e^{-x^{2}/2}\,\mathrm{d}x.
$$

Step one, remove the imaginary part. By Euler's formula $e^{itx}=\cos\left(tx\right)+i\sin\left(tx\right)$, while $\sin\left(tx\right)$ is odd in $x$ and $e^{-x^{2}/2}$ is even, so

$$
\int\sin\left(tx\right)e^{-x^{2}/2}\,\mathrm{d}x=0,
$$

leaving only

$$
\phi\left(t\right)=\int_{-\infty}^{\infty}\cos\left(tx\right)\left(2\pi\right)^{-1/2}e^{-x^{2}/2}\,\mathrm{d}x.
$$

Step two, differentiate with respect to $t$ (differentiating under the integral sign, the derivative of the integrand with respect to $t$ has an integrable dominating function):

$$
\phi'\left(t\right)=\int_{-\infty}^{\infty}\left(-x\right)\sin\left(tx\right)\left(2\pi\right)^{-1/2}e^{-x^{2}/2}\,\mathrm{d}x.
$$

Step three, integrate the above by parts. Let $u=\sin\left(tx\right)$ and $\mathrm{d}v=\left(-x\right)e^{-x^{2}/2}\,\mathrm{d}x$, so that $v=e^{-x^{2}/2}$. The boundary term

$$
\left[\sin\left(tx\right)e^{-x^{2}/2}\right]_{-\infty}^{\infty}=0,
$$

hence

$$
\phi'\left(t\right)=\int_{-\infty}^{\infty}\sin\left(tx\right)\frac{\mathrm{d}}{\mathrm{d}x}\left(e^{-x^{2}/2}\right)\,\mathrm{d}x=-\int_{-\infty}^{\infty}t\cos\left(tx\right)e^{-x^{2}/2}\,\mathrm{d}x=-t\phi\left(t\right).
$$

Step four, solve the differential equation $\phi'\left(t\right)=-t\phi\left(t\right)$. Let $\psi\left(t\right)=\phi\left(t\right)e^{t^{2}/2}$. Then

$$
\psi'\left(t\right)=e^{t^{2}/2}\left(\phi'\left(t\right)+t\phi\left(t\right)\right)=0.
$$

so $\psi$ is constant,

$$
\psi\left(t\right)=\psi\left(0\right)=\phi\left(0\right)e^{0}=1
$$

(since $\phi\left(0\right)=Ee^{0}=1$). Hence $\phi\left(t\right)e^{t^{2}/2}=1$, i.e.

$$
\phi\left(t\right)=e^{-t^{2}/2}.
$$

(Supplement: the analytic proof by complex shift gives a quick verification:

$$
\int e^{itx}\left(2\pi\right)^{-1/2}e^{-x^{2}/2}\,\mathrm{d}x=e^{-t^{2}/2}\int\left(2\pi\right)^{-1/2}e^{-\left(x-it\right)^{2}/2}\,\mathrm{d}x,
$$

the integral in parentheses is the integral of a normal density with mean $it$, which equals $1$.) $\blacksquare$

### Problem 2

Let $g\ge 0$ be continuous. If $X_{n}\Rightarrow X_{\infty}$, prove that

$$
\liminf_{n\to\infty}Eg\left(X_{n}\right)\ge Eg\left(X_{\infty}\right).
$$

### Solution to Problem 2

By **Theorem 3.2.8** (Skorokhod Representation), there exist random variables $Y_{n}=_{d}X_{n}$ and $Y_{\infty}=_{d}X_{\infty}$ on the same probability space such that $Y_{n}\to Y_{\infty}$ almost surely. Since $g$ is continuous, $g\left(Y_{n}\right)\to g\left(Y_{\infty}\right)$ almost surely.

Since $g\ge 0$ and $g\left(Y_{n}\right)\ge 0$, by **Theorem 1.6.5** (Fatou's Lemma):

$$
\liminf_{n\to\infty}E\,g\left(Y_{n}\right)\ge E\liminf_{n\to\infty}g\left(Y_{n}\right)=E\,g\left(Y_{\infty}\right).
$$

The last step uses $g\left(Y_{n}\right)\to g\left(Y_{\infty}\right)$ almost surely. Since $Y_{n}=_{d}X_{n}$ and $Y_{\infty}=_{d}X_{\infty}$, we have $E\,g\left(Y_{n}\right)=E\,g\left(X_{n}\right)$ and $E\,g\left(Y_{\infty}\right)=E\,g\left(X_{\infty}\right)$. Substituting gives

$$
\liminf_{n\to\infty}Eg\left(X_{n}\right)\ge Eg\left(X_{\infty}\right).
$$

$\blacksquare$
