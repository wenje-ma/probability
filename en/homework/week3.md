# week3

> **Definition 1.3.1 (Measurable Map)**<br>Let $\left(\Omega,\mathcal F\right)$ and $\left(S,\mathcal S\right)$ be measurable spaces. If $X^{-1}\left(B\right)\in\mathcal F$ for every $B\in\mathcal S$, then $X:\Omega\to S$ is called a measurable map. When $S=\mathbb R^{d}$ with $\mathcal S=\mathcal R^{d}$ and $d> 1$, $X$ is called a random vector; when $d=1$, a random variable.

> **Theorem 1.3.1 (Generator Criterion for Measurability)**<br>Let $\mathcal A$ generate $\mathcal S$ (i.e. $\mathcal S$ is the smallest $\sigma$-algebra containing $\mathcal A$). If $\left\{X\in A\right\}\in\mathcal F$ for every $A\in\mathcal A$, then $X$ is measurable.

> **Example 1.3.2 (Choice of Generators)**<br>On $\left(\mathbb R,\mathcal R\right)$, one may take $\left\{\left(-\infty,x\right]:x\in\mathbb R\right\}$ or $\left\{\left(-\infty,x\right):x\in\mathbb Q\right\}$ as generators; on $\left(\mathbb R^{d},\mathcal R^{d}\right)$, one may take $\left\{\left(a_{1},b_{1}\right)\times\cdots\times\left(a_{d},b_{d}\right):a_{i}< b_{i}\right\}$ or the family of open sets.

> **Theorem 1.3.4 (Composition of Measurable Maps)**<br>If $X:\left(\Omega,\mathcal F\right)\to\left(S,\mathcal S\right)$ and $f:\left(S,\mathcal S\right)\to\left(T,\mathcal T\right)$ are both measurable, then $f\left(X\right)$ is a measurable map from $\left(\Omega,\mathcal F\right)$ to $\left(T,\mathcal T\right)$. In particular, $cX$, $X^{2}$, $\sin X$, etc. are all random variables.

---

## 1

Prove: a continuous function from $\mathbb R^{d}$ to $\mathbb R$ is a measurable map from $\left(\mathbb R^{d},\mathcal R^{d}\right)$ to $\left(\mathbb R,\mathcal R\right)$.

### Solution 1

Let $f:\mathbb R^{d}\to\mathbb R$ be continuous. For any $a\in\mathbb R$, the set

$$
\left\{x:f\left(x\right)< a\right\}=f^{-1}\left(\left(-\infty,a\right)\right)
$$

is open, since $\left(-\infty,a\right)$ is open and $f$ is continuous. Every open set in $\mathbb R^{d}$ belongs to the Borel $\sigma$-algebra $\mathcal R^{d}$, so $\left\{x:f\left(x\right)< a\right\}\in\mathcal R^{d}$.

By **Theorem 1.3.1 (Generator Criterion for Measurability)**, take the generator family

$$
\mathcal A=\left\{\left(-\infty,a\right):a\in\mathbb R\right\}.
$$

By **Example 1.3.2 (Choice of Generators)**, $\mathcal A$ generates $\mathcal R$ (already $\left\{\left(-\infty,a\right):a\in\mathbb Q\right\}$ generates it); and since we have shown $\left\{f< a\right\}\in\mathcal R^{d}$ for all $a$, $f$ is measurable. $\blacksquare$

---

## 2

Prove: $\mathcal R^{d}$ is the smallest $\sigma$-algebra making all continuous functions measurable.

### Solution 2

Let $\mathcal G$ be the smallest $\sigma$-algebra making all continuous functions $f:\mathbb R^{d}\to\mathbb R$ measurable, i.e. the smallest $\sigma$-algebra containing all sets $\left\{x:f\left(x\right)\in B\right\}$ ($f$ continuous, $B\in\mathcal R$).

On one hand, by **Solution 1**, every continuous function is measurable with respect to $\left(\mathbb R^{d},\mathcal R^{d}\right)$, so $\mathcal R^{d}$ is one of the $\sigma$-algebras making all continuous functions measurable, and hence $\mathcal G\subset\mathcal R^{d}$.

On the other hand, for any open set $U\subset\mathbb R^{d}$, let $g_{U}\left(x\right)=d\left(x,U^{c}\right)$ be the distance from $x$ to the closed set $U^{c}$. The function $g_{U}$ is continuous, and $g_{U}\left(x\right)> 0$ iff $x\notin U^{c}$, i.e. $x\in U$. Hence

$$
U=\left\{x:g_{U}\left(x\right)> 0\right\}=g_{U}^{-1}\left(\left(0,\infty\right)\right).
$$

Since $g_{U}$ is continuous, it is measurable with respect to $\mathcal G$ (**Definition 1.3.1 (Measurable Map)**), so $U\in\mathcal G$. All open sets $U$ generate $\mathcal R^{d}$, so $\mathcal R^{d}\subset\mathcal G$.

Combining both inclusions gives $\mathcal G=\mathcal R^{d}$. $\blacksquare$
