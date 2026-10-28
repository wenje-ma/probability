# week13

> **Basic Knowledge: Notation $A_{n}$ infinitely often**<br>$A_{n}$ infinitely often (i.o.) means $\limsup_{n}A_{n}=\cap_{n}\cup_{m\ge n}A_{m}$.

> **Theorem 2.3.1 (Borel-Cantelli Lemma)**<br>If $\sum_{n=1}^{\infty}P\left(A_{n}\right)< \infty$, then $P\left(A_{n}\ \text{i.o.}\right)=0$. (No independence needed; from $EN=\sum P\left(A_{k}\right)< \infty$ it follows that $N=\sum\mathbf{1}_{A_{k}}< \infty$ almost everywhere.)

> **Theorem 2.3.7 (Second Borel-Cantelli Lemma)**<br>If the $A_{n}$ are independent and $\sum_{n}P\left(A_{n}\right)=\infty$, then $P\left(A_{n}\ \text{i.o.}\right)=1$. (Estimate $\prod\left(1-P\left(A_{n}\right)\right)$ using $1-x\le e^{-x}$.)

---

## 1

Let $A_{n}$ be a sequence of independent events with $P\left(A_{n}\right)< 1$ for all $n$. Prove that $P\left(\cup_{n}A_{n}\right)=1$ implies $\sum_{n}P\left(A_{n}\right)=\infty$, and hence $P\left(A_{n}\ \text{i.o.}\right)=1$.

### Solution 1

From $P\left(\cup_{n}A_{n}\right)=1$ we get $P\left(\cap_{n}A_{n}^{c}\right)=0$. Since the $A_{n}$ are independent, the $A_{n}^{c}$ are also independent, i.e. for finitely many,

$$
P\left(\cap_{n=1}^{N}A_{n}^{c}\right)=\prod_{n=1}^{N}P\left(A_{n}^{c}\right).
$$

Thus for each $N$,

$$
P\left(\bigcap_{n=1}^{N}A_{n}^{c}\right)=\prod_{n=1}^{N}\left(1-P\left(A_{n}\right)\right).
$$

Letting $N\to\infty$,

$$
\prod_{n=1}^{\infty}\left(1-P\left(A_{n}\right)\right)=P\left(\cap_{n}A_{n}^{c}\right)=0.
$$

Suppose for contradiction that $\sum_{n}P\left(A_{n}\right)< \infty$. Since $P\left(A_{n}\right)< 1$ means $1-P\left(A_{n}\right)> 0$, and $\sum P\left(A_{n}\right)< \infty$ ensures that

$$
\sum\log\left(1-P\left(A_{n}\right)\right)
$$

converges ($\log\left(1-x\right)\sim-x$), we have

$$
\prod_{n=1}^{\infty}\left(1-P\left(A_{n}\right)\right)> 0,
$$

a contradiction. Hence $\sum_{n}P\left(A_{n}\right)=\infty$.

By **Theorem 2.3.7 (Second Borel-Cantelli Lemma)** (the $A_{n}$ are independent and $\sum P\left(A_{n}\right)=\infty$), $P\left(A_{n}\ \text{i.o.}\right)=1$. $\blacksquare$

---

## 2

Let $X_{1},X_{2},\dots$ be independent. Prove that $\sup_{n}X_{n}< \infty$ almost everywhere iff there exists $A$ such that $\sum_{n}P\left(X_{n}> A\right)< \infty$.

### Solution 2

$\left(\Leftarrow\right)$ Suppose there exists $A$ with $\sum_{n}P\left(X_{n}> A\right)< \infty$. The events $\left\{X_{n}> A\right\}$ satisfy the hypothesis of **Theorem 2.3.1 (Borel-Cantelli Lemma)**, so $P\left(X_{n}> A\ \text{i.o.}\right)=0$, i.e. almost everywhere only finitely many $X_{n}$ exceed $A$. Hence $\sup_{n}X_{n}\le A< \infty$ almost everywhere (note: this direction does not require independence).

$\left(\Rightarrow\right)$ Suppose $\sup_{n}X_{n}< \infty$ almost everywhere. Then there exists $A$ with $P\left(\sup_{n}X_{n}\le A\right)> 0$ (since $\sup_{n}X_{n}$ is finite a.e., $\cup_{A}\left\{\sup\le A\right\}$ covers the whole space a.e.). Therefore

$$
\left\{X_{n}> A\ \text{i.o.}\right\}\subset\left\{\sup_{n}X_{n}> A\right\}
$$

implies

$$
P\left(X_{n}> A\ \text{i.o.}\right)\le P\left(\sup_{n}X_{n}> A\right)=1-P\left(\sup_{n}X_{n}\le A\right)< 1.
$$

Suppose for contradiction that $\sum_{n}P\left(X_{n}> A\right)=\infty$. Since the $X_{n}$ are independent, by **Theorem 2.3.7 (Second Borel-Cantelli Lemma)**, $P\left(X_{n}> A\ \text{i.o.}\right)=1$, contradicting the above. Hence $\sum_{n}P\left(X_{n}> A\right)< \infty$. $\blacksquare$
