# week6

> **Example 1.6.13 (Poisson Distribution)**
> 
> $Z$ has the Poisson distribution with parameter $\lambda$, written $Z\sim\mathrm{Poisson}\left(\lambda\right)$, meaning $P\left(Z=k\right)=e^{-\lambda}\lambda^{k}/k!$ for $k=0,1,2,\dots$.

> **Theorem 1.7.2 (Fubini's Theorem)**
> 
> If $f\ge 0$, then (Tonelli)

$$
\int_{X}\int_{Y}f\,\mu_{2}\left(\mathrm{d}y\right)\mu_{1}\left(\mathrm{d}x\right)=\int_{X\times Y}f\,\mathrm{d}\left(\mu_{1}\times\mu_{2}\right)=\int_{Y}\int_{X}f\,\mu_{1}\left(\mathrm{d}x\right)\mu_{2}\left(\mathrm{d}y\right).
$$
In particular, for nonnegative $f$ the order of integration may be exchanged (Tonelli).

> **Definition 2.1.1 (Independent Events)**
> 
> Events $A,B\in\mathcal F$ are independent if $P\left(A\cap B\right)=P\left(A\right)P\left(B\right)$. A sequence $A_{1},\dots,A_{n}$ is independent if for every $I\subset\left\{1,\dots,n\right\}$, $P\left(\cap_{i\in I}A_{i}\right)=\prod_{i\in I}P\left(A_{i}\right)$.

> **Theorem 2.1.1 (Independence and $\sigma$-algebras)**
> 
> (1) If $X,Y$ are independent, then $\sigma\left(X\right)$ and $\sigma\left(Y\right)$ are independent; (2) if $\mathcal A_{1},\dots,\mathcal A_{n}$ are independent, then $\sigma\left(\mathcal A_{1}\right),\dots,\sigma\left(\mathcal A_{n}\right)$ are independent. Hence to verify independence of random variables it suffices to check on generators.

> **Definition 2.1.2 (Independent Random Variables)**
> 
> Random variables $X_{1},\dots,X_{n}$ are independent if for all Borel sets $B_{1},\dots,B_{n}$,

$$
P\left(X_{1}\in B_{1},\dots,X_{n}\in B_{n}\right)=\prod_{i=1}^{n}P\left(X_{i}\in B_{i}\right).
$$

> **Definition 2.1.3 (Uncorrelated)**
> 
> If $EX^{2},EY^{2}< \infty$ and $EXY=EX\cdot EY$, then $X,Y$ are uncorrelated. Independence implies uncorrelatedness, but uncorrelatedness does not imply independence.

> **Exercise 2.1.10 (Convolution Formula)**
> 
> If $X,Y$ are independent and integer-valued, then $P\left(X+Y=n\right)=\sum_{m}P\left(X=m\right)P\left(Y=n-m\right)$.

> **Theorem 2.1.13 (Expectation of a Product of Independent Variables)**
> 
> If $X_{1},\dots,X_{n}$ are independent and either (a) each $X_{i}\ge 0$, or (b) each $E\left|X_{i}\right|< \infty$, then

$$
E\left(\prod_{i=1}^{n}X_{i}\right)=\prod_{i=1}^{n}EX_{i}.
$$

> **Theorem 2.1.16 (Density and Independence)**
> 
> Let $X_{1},\dots,X_{n}$ have joint density $f$. If $f$ can be written as $f\left(x_{1},\dots,x_{n}\right)=g_{1}\left(x_{1}\right)\cdots g_{n}\left(x_{n}\right)$ ($g_{i}\ge 0$ measurable), then $X_{1},\dots,X_{n}$ are independent; conversely, if $X_{1},\dots,X_{n}$ are independent and each has a density, then the joint density is the product of the marginal densities.

## 1

Let $\mu$ be a finite measure on $\mathbb R$, and let $F\left(x\right)=\mu\left(\left(-\infty,x\right]\right)$. Prove that

$$
\int\left(F\left(x+c\right)-F\left(x\right)\right)\,\mathrm{d}x=c\mu\left(\mathbb R\right).
$$

### Solution to 1

By properties of the distribution function,

$$
F\left(x+c\right)-F\left(x\right)=\mu\left(\left(x,x+c\right]\right).
$$

Hence

$$
\int\left(F\left(x+c\right)-F\left(x\right)\right)\,\mathrm{d}x=\int\mu\left(\left(x,x+c\right]\right)\,\mathrm{d}x=\int\int\mathbf{1}_{\left(x,x+c\right]}\left(y\right)\,\mu\left(\mathrm{d}y\right)\,\mathrm{d}x.
$$

The integrand is nonnegative, so by Tonelli's theorem (**Theorem 1.7.2 (Fubini's Theorem)**) exchange the order of integration:

$$
\int\int\mathbf{1}_{\left(x,x+c\right]}\left(y\right)\,\mu\left(\mathrm{d}y\right)\,\mathrm{d}x=\int\int\mathbf{1}_{y-c\le x< y}\,\mathrm{d}x\,\mu\left(\mathrm{d}y\right).
$$

For fixed $y$,

$$
\int\mathbf{1}_{y-c\le x< y}\,\mathrm{d}x
$$

is the Lebesgue measure of the interval $\left[y-c,y\right)$ of length $c$, which equals $c$. Therefore

$$
\int\left(F\left(x+c\right)-F\left(x\right)\right)\,\mathrm{d}x=\int c\,\mu\left(\mathrm{d}y\right)=c\mu\left(\mathbb R\right).
$$

$\blacksquare$

## 2

Prove directly from the definition: if $X$ and $Y$ are independent and $f,g$ are measurable functions, then $f\left(X\right)$ and $g\left(Y\right)$ are independent.

### Solution to 2

For any Borel sets $A,B\in\mathcal R$, write

$$
\left\{f\left(X\right)\in A\right\}=\left\{X\in f^{-1}\left(A\right)\right\},\qquad\left\{g\left(Y\right)\in B\right\}=\left\{Y\in g^{-1}\left(B\right)\right\}.
$$

Since $f,g$ are measurable, $f^{-1}\left(A\right),g^{-1}\left(B\right)\in\mathcal R$. By the definition of independence of $X,Y$ (**Definition 2.1.2 (Independent Random Variables)**, holding for all Borel sets),

$$
P\left(X\in f^{-1}\left(A\right),\,Y\in g^{-1}\left(B\right)\right)=P\left(X\in f^{-1}\left(A\right)\right)P\left(Y\in g^{-1}\left(B\right)\right).
$$

That is,

$$
P\left(f\left(X\right)\in A,\,g\left(Y\right)\in B\right)=P\left(f\left(X\right)\in A\right)P\left(g\left(Y\right)\in B\right).
$$

Since $A,B$ are arbitrary, $f\left(X\right)$ and $g\left(Y\right)$ are independent. $\blacksquare$

## 3

Let $\left(X_{1},\dots,X_{n}\right)$ have density $f\left(x_{1},\dots,x_{n}\right)$, i.e.

$$
P\left(\left(X_{1},\dots,X_{n}\right)\in A\right)=\int_{A}f\left(x\right)\,\mathrm{d}x
$$

for $A\in\mathcal R^{n}$. If $f$ can be written as

$$
f\left(x\right)=g_{1}\left(x_{1}\right)\cdots g_{n}\left(x_{n}\right)
$$

($g_{m}\ge 0$ measurable, not necessarily probability densities), prove that $X_{1},\dots,X_{n}$ are independent.

### Solution to 3

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
