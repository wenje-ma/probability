# Assignment 7

> **Theorem 1.7.2** (Fubini's Theorem)<br>If $f\ge 0$ or $\int\left|f\right|\,\mathrm{d}\left(\mu_{1}\times\mu_{2}\right)< \infty$, then $$\int_{X}\int_{Y}f\,\mu_{2}\left(\mathrm{d}y\right)\mu_{1}\left(\mathrm{d}x\right)=\int_{X\times Y}f\,\mathrm{d}\left(\mu_{1}\times\mu_{2}\right)=\int_{Y}\int_{X}f\,\mu_{1}\left(\mathrm{d}x\right)\mu_{2}\left(\mathrm{d}y\right).$$ In particular, in the nonnegative case the order of integration may be exchanged (Tonelli).

> **Definition 2.1.1** (Independent Events)<br>Events $A,B\in\mathcal F$ are independent if $P\left(A\cap B\right)=P\left(A\right)P\left(B\right)$. A sequence of events $A_{1},\dots,A_{n}$ is independent if for every $I\subset\left\{1,\dots,n\right\}$, $P\left(\cap_{i\in I}A_{i}\right)=\prod_{i\in I}P\left(A_{i}\right)$.

> **Definition 2.1.2** (Independent Random Variables)<br>Random variables $X_{1},\dots,X_{n}$ are independent if for all Borel sets $B_{1},\dots,B_{n}$, $$P\left(X_{1}\in B_{1},\dots,X_{n}\in B_{n}\right)=\prod_{i=1}^{n}P\left(X_{i}\in B_{i}\right).$$

> **Theorem 2.1.1** (Independence and $\sigma$-Algebras)
> 
> (1) If $X,Y$ are independent, then $\sigma\left(X\right)$ and $\sigma\left(Y\right)$ are independent;
> 
> (2) if $\mathcal A_{1},\dots,\mathcal A_{n}$ are independent, then $\sigma\left(\mathcal A_{1}\right),\dots,\sigma\left(\mathcal A_{n}\right)$ are independent (Theorem 2.1.7). Hence, to verify the independence of random variables, it suffices to check the generators.

### Problem 1

Let $\mu$ be a finite measure on $\mathbb R$, and $F\left(x\right)=\mu\left(\left(-\infty,x\right]\right)$. Prove that

$$
\int\left(F\left(x+c\right)-F\left(x\right)\right)\,\mathrm{d}x=c\mu\left(\mathbb R\right).
$$

### Solution to Problem 1

By the properties of distribution functions,

$$
F\left(x+c\right)-F\left(x\right)=\mu\left(\left(x,x+c\right]\right).
$$

Hence

$$
\int\left(F\left(x+c\right)-F\left(x\right)\right)\,\mathrm{d}x=\int\mu\left(\left(x,x+c\right]\right)\,\mathrm{d}x=\int\int\mathbf{1}_{\left(x,x+c\right]}\left(y\right)\,\mu\left(\mathrm{d}y\right)\,\mathrm{d}x.
$$

The integrand is nonnegative, so by Tonelli's theorem (**Theorem 1.7.2**) we exchange the order of integration:

$$
\int\int\mathbf{1}_{\left(x,x+c\right]}\left(y\right)\,\mu\left(\mathrm{d}y\right)\,\mathrm{d}x=\int\int\mathbf{1}_{y-c\le x< y}\,\mathrm{d}x\,\mu\left(\mathrm{d}y\right).
$$

For fixed $y$,

$$
\int\mathbf{1}_{y-c\le x< y}\,\mathrm{d}x
$$

is the Lebesgue measure of the interval $\left[y-c,y\right)$ of length $c$, which equals $c$. Hence

$$
\int\left(F\left(x+c\right)-F\left(x\right)\right)\,\mathrm{d}x=\int c\,\mu\left(\mathrm{d}y\right)=c\mu\left(\mathbb R\right).
$$

$\blacksquare$

### Problem 2

Prove directly from the definition: if $X$ and $Y$ are independent and $f,g$ are measurable functions, then $f\left(X\right)$ and $g\left(Y\right)$ are independent.

### Solution to Problem 2

For any Borel sets $A,B\in\mathcal R$, write

$$
\left\{f\left(X\right)\in A\right\}=\left\{X\in f^{-1}\left(A\right)\right\},;\left\{g\left(Y\right)\in B\right\}=\left\{Y\in g^{-1}\left(B\right)\right\}.
$$

Since $f,g$ are measurable, $f^{-1}\left(A\right),g^{-1}\left(B\right)\in\mathcal R$. By the definition of independence of $X,Y$ (**Definition 2.1.2**, which holds for all Borel sets),

$$
P\left(X\in f^{-1}\left(A\right),\,Y\in g^{-1}\left(B\right)\right)=P\left(X\in f^{-1}\left(A\right)\right)P\left(Y\in g^{-1}\left(B\right)\right).
$$

i.e.

$$
P\left(f\left(X\right)\in A,\,g\left(Y\right)\in B\right)=P\left(f\left(X\right)\in A\right)P\left(g\left(Y\right)\in B\right).
$$

Since $A,B$ were arbitrary, $f\left(X\right)$ and $g\left(Y\right)$ are independent. $\blacksquare$
