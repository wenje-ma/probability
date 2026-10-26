# Assignment 13

> **Notation** ($A_{n}\ \text{无穷多次}$)<br>$A_{n}\ \text{无穷多次}$ (occurring infinitely often) means $\limsup_{n}A_{n}=\cap_{n}\cup_{m\ge n}A_{m}$.

> **Theorem 2.3.1** (Borel–Cantelli Lemma)<br>If $\sum_{n=1}^{\infty}P\left(A_{n}\right)< \infty$, then $P\left(A_{n}\ \text{无穷多次}\right)=0$. (Independence is not needed; from $EN=\sum P\left(A_{k}\right)< \infty$ we get $N=\sum\mathbf{1}_{A_{k}}< \infty$ almost everywhere.)

> **Theorem 2.3.7** (Second Borel–Cantelli Lemma)<br>If the $A_{n}$ are independent and $\sum_{n}P\left(A_{n}\right)=\infty$, then $P\left(A_{n}\ \text{无穷多次}\right)=1$. (Use $1-x\le e^{-x}$ to estimate $\prod\left(1-P\left(A_{n}\right)\right)$.)

### Problem 1

Let $A_{n}$ be a sequence of independent events with $P\left(A_{n}\right)< 1$ for all $n$. Prove that $P\left(\cup_{n}A_{n}\right)=1$ implies $\sum_{n}P\left(A_{n}\right)=\infty$, and hence $P\left(A_{n}\ \text{无穷多次}\right)=1$.

### Solution to Problem 1

From $P\left(\cup_{n}A_{n}\right)=1$ we get $P\left(\cap_{n}A_{n}^{c}\right)=0$. Since $A_{n}$ are independent, so are the $A_{n}^{c}$, i.e. for finitely many,

$$
P\left(\cap_{n=1}^{N}A_{n}^{c}\right)=\prod_{n=1}^{N}P\left(A_{n}^{c}\right).
$$

Hence for each $N$,

$$
P\left(\bigcap_{n=1}^{N}A_{n}^{c}\right)=\prod_{n=1}^{N}\left(1-P\left(A_{n}\right)\right).
$$

Letting $N\to\infty$ gives

$$
\prod_{n=1}^{\infty}\left(1-P\left(A_{n}\right)\right)=P\left(\cap_{n}A_{n}^{c}\right)=0.
$$

Suppose for contradiction that $\sum_{n}P\left(A_{n}\right)< \infty$. Since $P\left(A_{n}\right)< 1$ means $1-P\left(A_{n}\right)> 0$, and $\sum P\left(A_{n}\right)< \infty$ guarantees that

$$
\sum\log\left(1-P\left(A_{n}\right)\right)
$$

converges ($\log\left(1-x\right)\sim-x$), so

$$
\prod_{n=1}^{\infty}\left(1-P\left(A_{n}\right)\right)> 0,
$$

a contradiction. Hence $\sum_{n}P\left(A_{n}\right)=\infty$.

By **Theorem 2.3.7** (Second Borel–Cantelli, the $A_{n}$ are independent and $\sum P\left(A_{n}\right)=\infty$), $P\left(A_{n}\ \text{无穷多次}\right)=1$. $\blacksquare$

### Problem 2

Let $X_{1},X_{2},\dots$ be independent. Prove that $\sup_{n}X_{n}< \infty$ almost everywhere if and only if there exists $A$ such that $\sum_{n}P\left(X_{n}> A\right)< \infty$.

### Solution to Problem 2

$\left(\Leftarrow\right)$ Suppose there exists $A$ such that $\sum_{n}P\left(X_{n}> A\right)< \infty$. The events $\left\{X_{n}> A\right\}$ satisfy the conditions of **Theorem 2.3.1** (Borel–Cantelli), so $P\left(X_{n}> A\ \text{无穷多次}\right)=0$, i.e. almost surely only finitely many $X_{n}$ exceed $A$. Hence $\sup_{n}X_{n}\le A< \infty$ almost everywhere. (Note: this direction does not require independence.)

$\left(\Rightarrow\right)$ Suppose $\sup_{n}X_{n}< \infty$ almost everywhere. Then there exists $A$ such that $P\left(\sup_{n}X_{n}\le A\right)> 0$ (since $\sup_{n}X_{n}$ is finite almost everywhere, $\cup_{A}\left\{\sup\le A\right\}$ covers the whole space up to a null set). Hence

$$
\left\{X_{n}> A\ \text{无穷多次}\right\}\subset\left\{\sup_{n}X_{n}> A\right\}
$$

implies

$$
P\left(X_{n}> A\ \text{无穷多次}\right)\le P\left(\sup_{n}X_{n}> A\right)=1-P\left(\sup_{n}X_{n}\le A\right)< 1.
$$

Suppose for contradiction that $\sum_{n}P\left(X_{n}> A\right)=\infty$. Since $X_{n}$ are independent, **Theorem 2.3.7** (Second Borel–Cantelli) gives $P\left(X_{n}> A\ \text{无穷多次}\right)=1$, contradicting the above. Hence $\sum_{n}P\left(X_{n}> A\right)< \infty$. $\blacksquare$
