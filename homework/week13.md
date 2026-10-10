# 作业 13

> **记号** ($A_{n}\ \text{无穷多次}$)<br>$A_{n}\ \text{无穷多次}$ (无穷多次发生) 指 $\limsup_{n}A_{n}=\cap_{n}\cup_{m\ge n}A_{m}$.

> **定理 2.3.1** (博雷尔-坎泰利引理)<br>若 $\sum_{n=1}^{\infty}P\left(A_{n}\right)<\infty$, 则 $P\left(A_{n}\ \text{无穷多次}\right)=0$. (不需独立性; 由 $EN=\sum P\left(A_{k}\right)<\infty$ 得 $N=\sum\mathbf{1}_{A_{k}}<\infty$ 几乎处处)

> **定理 2.3.7** (第二博雷尔-坎泰利引理)<br>若 $A_{n}$ 独立且 $\sum_{n}P\left(A_{n}\right)=\infty$, 则 $P\left(A_{n}\ \text{无穷多次}\right)=1$. (用 $1-x\le e^{-x}$ 估计 $\prod\left(1-P\left(A_{n}\right)\right)$.)

### 习题一

设 $A_{n}$ 是一列独立事件且对一切 $n$ 有 $P\left(A_{n}\right)<1$. 证明 $P\left(\cup_{n}A_{n}\right)=1$ 蕴含 $\sum_{n}P\left(A_{n}\right)=\infty$, 从而 $P\left(A_{n}\ \text{无穷多次}\right)=1$.

### 解答 习题一

由 $P\left(\cup_{n}A_{n}\right)=1$ 得 $P\left(\cap_{n}A_{n}^{c}\right)=0$. 因 $A_{n}$ 独立, $A_{n}^{c}$ 亦独立, 即对有限个:

$$
P\left(\cap_{n=1}^{N}A_{n}^{c}\right)=\prod_{n=1}^{N}P\left(A_{n}^{c}\right).
$$

故对每个 $N$,

$$
P\left(\bigcap_{n=1}^{N}A_{n}^{c}\right)=\prod_{n=1}^{N}\left(1-P\left(A_{n}\right)\right).
$$

令 $N\to\infty$ 得

$$
\begin{aligned}
&\quad\;\prod_{n=1}^{\infty}\left(1-P\left(A_{n}\right)\right)\\
&=P\left(\cap_{n}A_{n}^{c}\right)\\
&=0.
\end{aligned}
$$

反设 $\sum_{n}P\left(A_{n}\right)<\infty$. 因 $P\left(A_{n}\right)<1$ 即 $1-P\left(A_{n}\right)>0$, 且 $\sum P\left(A_{n}\right)<\infty$ 保证

$$
\sum\log\left(1-P\left(A_{n}\right)\right)
$$

收敛 ($\log\left(1-x\right)\sim-x$), 故

$$
\prod_{n=1}^{\infty}\left(1-P\left(A_{n}\right)\right)>0,
$$

矛盾. 所以 $\sum_{n}P\left(A_{n}\right)=\infty$.

由**定理 2.3.7** (第二博雷尔-坎泰利, $A_{n}$ 独立且 $\sum P\left(A_{n}\right)=\infty$), $P\left(A_{n}\ \text{无穷多次}\right)=1$. $\blacksquare$

### 习题二

设 $X_{1},X_{2},\dots$ 独立. 证明 $\sup_{n}X_{n}<\infty$ 几乎处处当且仅当存在 $A$ 使 $\sum_{n}P\left(X_{n}>A\right)<\infty$.

### 解答 习题二

$\left(\Leftarrow\right)$ 设存在 $A$ 使 $\sum_{n}P\left(X_{n}>A\right)<\infty$. 事件 $\left\{X_{n}>A\right\}$ 满足**定理 2.3.1** (博雷尔-坎泰利) 的条件, 故 $P\left(X_{n}>A\ \text{无穷多次}\right)=0$, 即几乎处处只有有限个 $X_{n}$ 超过 $A$. 因此 $\sup_{n}X_{n}\le A<\infty$ 几乎处处 (注: 此方向不需独立性).

$\left(\Rightarrow\right)$ 设 $\sup_{n}X_{n}<\infty$ 几乎处处. 则存在 $A$ 使 $P\left(\sup_{n}X_{n}\le A\right)>0$ (因 $\sup_{n}X_{n}$ 几乎处处有限, $\cup_{A}\left\{\sup\le A\right\}$ 覆盖几乎处处全空间). 于是

$$
\left\{X_{n}>A\ \text{无穷多次}\right\}\subset\left\{\sup_{n}X_{n}>A\right\}
$$

蕴含

$$
\begin{aligned}
&\quad\;P\left(X_{n}>A\ \text{无穷多次}\right)\\
&\le P\left(\sup_{n}X_{n}>A\right)\\
&=1-P\left(\sup_{n}X_{n}\le A\right)\\
&<1.
\end{aligned}
$$

反设 $\sum_{n}P\left(X_{n}>A\right)=\infty$. 因 $X_{n}$ 独立, 由**定理 2.3.7** (第二博雷尔-坎泰利) 得 $P\left(X_{n}>A\ \text{无穷多次}\right)=1$, 与上式矛盾. 故 $\sum_{n}P\left(X_{n}>A\right)<\infty$. $\blacksquare$
