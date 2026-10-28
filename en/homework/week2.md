# week2

> **Definition 1.2.1 (Random Variable)**<br>Let $X$ be a real-valued function on $\left(\Omega,\mathcal F,P\right)$. If for every Borel set $B\subset\mathbb R$ one has $X^{-1}\left(B\right)\in\mathcal F$, then $X$ is called a random variable (or $\mathcal F$-measurable).

> **Theorem 1.2.1 (Properties of a Distribution Function)**<br>Let $F\left(x\right)=P\left(X\le x\right)$. Then: (1) $F$ is nondecreasing; (2) $\lim_{x\to\infty}F\left(x\right)=1$, $\lim_{x\to-\infty}F\left(x\right)=0$; (3) $F$ is right-continuous, i.e. $\lim_{y\downarrow x}F\left(y\right)=F\left(x\right)$; (4) if $F\left(x-\right)=\lim_{y\uparrow x}F\left(y\right)$, then $F\left(x-\right)=P\left(X< x\right)$; (5) $P\left(X=x\right)=F\left(x\right)-F\left(x-\right)$.

> **Definition 1.2.2 (Distribution and Distribution Function)**<br>The probability measure $\mu\left(A\right)=P\left(X\in A\right)$ induced by $X$ on $\left(\mathbb R,\mathcal R\right)$ is called the distribution of $X$; its distribution function is $F\left(x\right)=P\left(X\le x\right)$.

> **Theorem 1.2.2 (Inverse of a Distribution Function)**<br>Let $F$ be a distribution function. Define its inverse by $F^{-1}\left(y\right)=\sup\left\{x:F\left(x\right)< y\right\}$, $y\in\left(0,1\right)$. If $U$ is uniform on $\left(0,1\right\right)$, then $F^{-1}\left(U\right)$ has distribution function $F$. This construction is also the standard method for generating random variables on a computer.

---

## 1

Let $X,Y$ be random variables on $\left(\Omega,\mathcal F,P\right)$, and $A\in\mathcal F$. If $Z\left(\omega\right)=X\left(\omega\right)$ when $\omega\in A$, and $Z\left(\omega\right)=Y\left(\omega\right)$ when $\omega\in A^{c}$, prove that $Z$ is a random variable.

### Solution 1

For any Borel set $B\in\mathcal R$, by the definition of $Z$ (**Definition 1.2.1 (Random Variable)**),

$$
Z^{-1}\left(B\right)=\left(A\cap\left\{\omega:X\left(\omega\right)\in B\right\}\right)\cup\left(A^{c}\cap\left\{\omega:Y\left(\omega\right)\in B\right\}\right).
$$

Since $X,Y$ are random variables, $\left\{X\in B\right\},\left\{Y\in B\right\}\in\mathcal F$; also $A\in\mathcal F$ and $\mathcal F$ is a $\sigma$-algebra, so $A^{c}\in\mathcal F$, and hence $Z^{-1}\left(B\right)\in\mathcal F$. Since $B$ was arbitrary, $Z$ is a random variable. $\blacksquare$

---

## 2

Let $F\left(x\right)=P\left(X\le x\right)$ be continuous. Prove that $Y=F\left(X\right)$ is uniform on $\left(0,1\right)$, i.e. $P\left(Y\le y\right)=y$ for $y\in\left[0,1\right]$.

### Solution 2

Since $F$ is nondecreasing and continuous, define the generalized inverse ($0< y< 1$):

$$
G\left(y\right)=\inf\left\{x:F\left(x\right)\ge y\right\}.
$$

Right-continuity of $F$ gives $F\left(G\left(y\right)\right)\ge y$; continuity of $F$ (hence left-continuity) gives $F\left(G\left(y\right)\right)=y$; and $F\left(x\right)< y$ iff $x< G\left(y\right)$ (continuity excludes jumps).

Consider three cases for $0\le y\le 1$:

(1) When $0< y< 1$, since $F\left(X\right)\le y$ is equivalent to $X\le G\left(y\right)$,

$$
P\left(Y\le y\right)=P\left(F\left(X\right)\le y\right)=P\left(X\le G\left(y\right)\right)=F\left(G\left(y\right)\right)=y;
$$

(2) When $y=0$,

$$
G\left(0\right)=\inf\left\{x:F\left(x\right)\ge 0\right\}=-\infty,
$$

so

$$
P\left(Y\le 0\right)=P\left(F\left(X\right)=0\right)=P\left(X\le G\left(0\right)\right)=0;
$$

(3) When $y=1$, $P\left(Y\le 1\right)=1$ trivially.

In summary, $P\left(Y\le y\right)=y$ for $y\in\left[0,1\right]$, i.e. $Y=F\left(X\right)$ is uniform on $\left(0,1\right)$. $\blacksquare$
