# week2

> **Definition 1.2.1 (Random Variable)**
> 
> Let $X$ be a real-valued function on $\left(\Omega,\mathcal{F},P\right)$. If for every Borel set $B\subset\mathbb{R}$ one has $X^{-1}\left(B\right)\in\mathcal{F}$, then $X$ is called a random variable (or $\mathcal{F}$-measurable).

> **Theorem 1.2.1 (Properties of a Distribution Function)**
> 
> Let $F\left(x\right)=P\left(X\le{x}\right)$. Then: (1) $F$ is nondecreasing; (2) $\lim_{x\to\infty}F\left(x\right)=1$, $\lim_{x\to-\infty}F\left(x\right)=0$; (3) $F$ is right-continuous, i.e. $\lim_{y\downarrow{x}}F\left(y\right)=F\left(x\right)$; (4) if $F\left(x-\right)=\lim_{y\uparrow{x}}F\left(y\right)$, then $F\left(x-\right)=P\left(X<{}x\right)$; (5) $P\left(X=x\right)=F\left(x\right)-F\left(x-\right)$.

> **Definition 1.2.2 (Distribution and Distribution Function)**
> 
> The probability measure $\mu\left(A\right)=P\left(X\in{A}\right)$ induced by $X$ on $\left(\mathbb{R},\mathcal{R}\right)$ is called the distribution of $X$; its distribution function is $F\left(x\right)=P\left(X\le{x}\right)$.

> **Theorem 1.2.2 (Inverse of a Distribution Function)**
> 
> Let $F$ be a distribution function. Define its inverse by $F^{-1}\left(y\right)=\sup\left\{x:F\left(x\right)<{}y\right\}$, $y\in\left(0,1\right)$. If $U$ is uniform on $\left(0,1\right\right)$, then $F^{-1}\left(U\right)$ has distribution function $F$. This construction is also the standard method for generating random variables on a computer.

> **Definition 1.3.1 (Measurable Map)**
> 
> Let $\left(\Omega,\mathcal{F}\right)$ and $\left(S,\mathcal{S}\right)$ be measurable spaces. If $X^{-1}\left(B\right)\in\mathcal{F}$ for every $B\in\mathcal{S}$, then $X:\Omega\to{S}$ is called a measurable map. When $S=\mathbb{R}^{d}$ with $\mathcal{S}=\mathcal{R}^{d}$ and $d>1$, $X$ is called a random vector; when $d=1$, a random variable.

> **Theorem 1.3.1 (Generator Criterion for Measurability)**
> 
> Let $\mathcal{A}$ generate $\mathcal{S}$ (i.e. $\mathcal{S}$ is the smallest $\sigma$-algebra containing $\mathcal{A}$). If $\left\{X\in{A}\right\}\in\mathcal{F}$ for every $A\in\mathcal{A}$, then $X$ is measurable.

> **Example 1.3.2 (Choice of Generators)**
> 
> On $\left(\mathbb{R},\mathcal{R}\right)$, one may take $\left\{\left(-\infty,x\right]:x\in\mathbb{R}\right\}$ or $\left\{\left(-\infty,x\right):x\in\mathbb{Q}\right\}$ as generators; on $\left(\mathbb{R}^{d},\mathcal{R}^{d}\right)$, one may take $\left\{\left(a_{1},b_{1}\right)\times\cdots\times\left(a_{d},b_{d}\right):a_{i}<{}b_{i}\right\}$ or the family of open sets.

> **Theorem 1.3.4 (Composition of Measurable Maps)**
> 
> If $X:\left(\Omega,\mathcal{F}\right)\to\left(S,\mathcal{S}\right)$ and $f:\left(S,\mathcal{S}\right)\to\left(T,\mathcal{T}\right)$ are both measurable, then $f\left(X\right)$ is a measurable map from $\left(\Omega,\mathcal{F}\right)$ to $\left(T,\mathcal{T}\right)$. In particular, $cX$, $X^{2}$, $\sin{X}$, etc. are all random variables.

## 1

Let $X,Y$ be random variables on $\left(\Omega,\mathcal{F},P\right)$, and $A\in\mathcal{F}$. If $Z\left(\omega\right)=X\left(\omega\right)$ when $\omega\in{A}$, and $Z\left(\omega\right)=Y\left(\omega\right)$ when $\omega\in{A}^{c}$, prove that $Z$ is a random variable.

### Solution to 1

For any Borel set $B\in\mathcal{R}$, by the definition of $Z$ (**Definition 1.2.1 (Random Variable)**),

$$
Z^{-1}\left(B\right)=\left(A\cap\left\{\omega:X\left(\omega\right)\in{B}\right\}\right)\cup\left(A^{c}\cap\left\{\omega:Y\left(\omega\right)\in{B}\right\}\right).
$$

Since $X,Y$ are random variables, $\left\{X\in{B}\right\},\left\{Y\in{B}\right\}\in\mathcal{F}$; also $A\in\mathcal{F}$ and $\mathcal{F}$ is a $\sigma$-algebra, so $A^{c}\in\mathcal{F}$, and hence $Z^{-1}\left(B\right)\in\mathcal{F}$. Since $B$ was arbitrary, $Z$ is a random variable. $\blacksquare$

## 2

Let $F\left(x\right)=P\left(X\le{x}\right)$ be continuous. Prove that $Y=F\left(X\right)$ is uniform on $\left(0,1\right)$, i.e. $P\left(Y\le{y}\right)=y$ for $y\in\left[0,1\right]$.

### Solution to 2

Since $F$ is nondecreasing and continuous, define the generalized inverse ($0<{}y<1$):

$$
G\left(y\right)=\inf\left\{x:F\left(x\right)\ge{y}\right\}.
$$

Right-continuity of $F$ gives $F\left(G\left(y\right)\right)\ge{y}$; continuity of $F$ (hence left-continuity) gives $F\left(G\left(y\right)\right)=y$; and $F\left(x\right)<{}y$ iff $x<{}G\left(y\right)$ (continuity excludes jumps).

Consider three cases for $0\le{y}\le1$:

(1) When $0<{}y<1$, since $F\left(X\right)\le{y}$ is equivalent to $X\le{G}\left(y\right)$,

$$
P\left(Y\le{y}\right)=P\left(F\left(X\right)\le{y}\right)=P\left(X\le{G}\left(y\right)\right)=F\left(G\left(y\right)\right)=y;
$$

(2) When $y=0$,

$$
G\left(0\right)=\inf\left\{x:F\left(x\right)\ge0\right\}=-\infty,
$$

so

$$
P\left(Y\le0\right)=P\left(F\left(X\right)=0\right)=P\left(X\le{G}\left(0\right)\right)=0;
$$

(3) When $y=1$, $P\left(Y\le1\right)=1$ trivially.

In summary, $P\left(Y\le{y}\right)=y$ for $y\in\left[0,1\right]$, i.e. $Y=F\left(X\right)$ is uniform on $\left(0,1\right)$. $\blacksquare$

## 3

Prove: a continuous function from $\mathbb{R}^{d}$ to $\mathbb{R}$ is a measurable map from $\left(\mathbb{R}^{d},\mathcal{R}^{d}\right)$ to $\left(\mathbb{R},\mathcal{R}\right)$.

### Solution to 3

Let $f:\mathbb{R}^{d}\to\mathbb{R}$ be continuous. For any $a\in\mathbb{R}$, the set

$$
\left\{x:f\left(x\right)<{}a\right\}=f^{-1}\left(\left(-\infty,a\right)\right)
$$

is open, since $\left(-\infty,a\right)$ is open and $f$ is continuous. Every open set in $\mathbb{R}^{d}$ belongs to the Borel $\sigma$-algebra $\mathcal{R}^{d}$, so $\left\{x:f\left(x\right)<{}a\right\}\in\mathcal{R}^{d}$.

By **Theorem 1.3.1 (Generator Criterion for Measurability)**, take the generator family

$$
\mathcal{A}=\left\{\left(-\infty,a\right):a\in\mathbb{R}\right\}.
$$

By **Example 1.3.2 (Choice of Generators)**, $\mathcal{A}$ generates $\mathcal{R}$ (already $\left\{\left(-\infty,a\right):a\in\mathbb{Q}\right\}$ generates it); and since we have shown $\left\{f<{}a\right\}\in\mathcal{R}^{d}$ for all $a$, $f$ is measurable. $\blacksquare$

## 4

Prove: $\mathcal{R}^{d}$ is the smallest $\sigma$-algebra making all continuous functions measurable.

### Solution to 4

Let $\mathcal{G}$ be the smallest $\sigma$-algebra making all continuous functions $f:\mathbb{R}^{d}\to\mathbb{R}$ measurable, i.e. the smallest $\sigma$-algebra containing all sets $\left\{x:f\left(x\right)\in{B}\right\}$ ($f$ continuous, $B\in\mathcal{R}$).

On one hand, by Solution 1, every continuous function is measurable with respect to $\left(\mathbb{R}^{d},\mathcal{R}^{d}\right)$, so $\mathcal{R}^{d}$ is one of the $\sigma$-algebras making all continuous functions measurable, and hence $\mathcal{G}\subset\mathcal{R}^{d}$.

On the other hand, for any open set $U\subset\mathbb{R}^{d}$, let $g_{U}\left(x\right)=d\left(x,U^{c}\right)$ be the distance from $x$ to the closed set $U^{c}$. The function $g_{U}$ is continuous, and $g_{U}\left(x\right)>0$ iff $x\notin{U}^{c}$, i.e. $x\in{U}$. Hence

$$
U=\left\{x:g_{U}\left(x\right)>0\right\}=g_{U}^{-1}\left(\left(0,\infty\right)\right).
$$

Since $g_{U}$ is continuous, it is measurable with respect to $\mathcal{G}$ (**Definition 1.3.1 (Measurable Map)**), so $U\in\mathcal{G}$. All open sets $U$ generate $\mathcal{R}^{d}$, so $\mathcal{R}^{d}\subset\mathcal{G}$.

Combining both inclusions gives $\mathcal{G}=\mathcal{R}^{d}$. $\blacksquare$
