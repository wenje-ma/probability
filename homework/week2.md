# 作业 2

> **定义 1.2.1** (随机变量)<br>设 $X$ 是 $\left(\Omega,\mathcal F,P\right)$ 上的实值函数, 若对每个博雷尔集 $B\subset\mathbb R$ 有 $X^{-1}\left(B\right)\in\mathcal F$, 则称 $X$ 为**随机变量** (或称 $\mathcal F$-可测).

> **定义 1.2.2** (分布与分布函数)<br>$X$ 在 $\left(\mathbb R,\mathcal R\right)$ 上诱导的概率测度 $\mu\left(A\right)=P\left(X\in A\right)$ 称为 $X$ 的**分布**; 其**分布函数**为 $F\left(x\right)=P\left(X\le x\right)$.

> **定理 1.2.1** (分布函数的性质)<br>设 $F\left(x\right)=P\left(X\le x\right)$, 则:<br>(1) $F$ 非降;<br>(2) $\lim_{x\to\infty}F\left(x\right)=1$, $\lim_{x\to-\infty}F\left(x\right)=0$;<br>(3) $F$ 右连续, 即 $\lim_{y\downarrow x}F\left(y\right)=F\left(x\right)$;<br>(4) 若 $F\left(x-\right)=\lim_{y\uparrow x}F\left(y\right)$, 则 $F\left(x-\right)=P\left(X<x\right)$;<br>(5) $P\left(X=x\right)=F\left(x\right)-F\left(x-\right)$.

> **定理 1.2.2** (分布函数的逆)<br>设 $F$ 是分布函数. 定义其逆 $F^{-1}\left(y\right)=\sup\left\{x:F\left(x\right)<y\right\}$, $y\in\left(0,1\right)$. 若 $U$ 服从 $\left(0,1\right)$ 上的均匀分布, 则 $F^{-1}\left(U\right)$ 以 $F$ 为分布函数. 该构造也是计算机生成随机变量的标准方法.

### 习题一

设 $X,Y$ 是 $\left(\Omega,\mathcal F,P\right)$ 上的随机变量, $A\in\mathcal F$. 若 $Z\left(\omega\right)=X\left(\omega\right)$ (当 $\omega\in A$), $Z\left(\omega\right)=Y\left(\omega\right)$ (当 $\omega\in A^{c}$), 证明 $Z$ 是随机变量.

### 解答 习题一

对任意博雷尔集 $B\in\mathcal R$, 由 $Z$ 的定义 (**定义 1.2.1**),

$$
Z^{-1}\left(B\right)=\left(A\cap\left\{\omega:X\left(\omega\right)\in B\right\}\right)\cup\left(A^{c}\cap\left\{\omega:Y\left(\omega\right)\in B\right\}\right).
$$

因 $X,Y$ 是随机变量, $\left\{X\in B\right\},\left\{Y\in B\right\}\in\mathcal F$; 又 $A\in\mathcal F$ 且 $\mathcal F$ 是 $\sigma$-代数, 故 $A^{c}\in\mathcal F$, 进而 $Z^{-1}\left(B\right)\in\mathcal F$. 由 $B$ 任意, $Z$ 是随机变量. $\blacksquare$

### 习题二

设 $F\left(x\right)=P\left(X\le x\right)$ 连续, 证明 $Y=F\left(X\right)$ 在 $\left(0,1\right)$ 上均匀分布, 即对 $y\in\left[0,1\right]$ 有 $P\left(Y\le y\right)=y$.

### 解答 习题二

因 $F$ 非降且连续, 定义广义逆 ($0<y<1$):

$$
G\left(y\right)=\inf\left\{x:F\left(x\right)\ge y\right\}.
$$

由 $F$ 右连续有 $F\left(G\left(y\right)\right)\ge y$; 由 $F$ 连续 (从而左连续) 有 $F\left(G\left(y\right)\right)=y$; 且 $F\left(x\right)<y$ 当且仅当 $x<G\left(y\right)$ (连续性排除了跳跃).

对 $0\le y\le 1$ 分三种情形:

(1) 当 $0<y<1$ 时, 由 $F\left(X\right)\le y$ 与 $X\le G\left(y\right)$ 等价,

$$
\begin{aligned}
&\quad\;P\left(Y\le y\right)\\
&=P\left(F\left(X\right)\le y\right)\\
&=P\left(X\le G\left(y\right)\right)\\
&=F\left(G\left(y\right)\right)\\
&=y;
\end{aligned}
$$

(2) 当 $y=0$ 时,

$$
\begin{aligned}
&\quad\;G\left(0\right)\\
&=\inf\left\{x:F\left(x\right)\ge 0\right\}\\
&=-\infty,
\end{aligned}
$$

故

$$
\begin{aligned}
&\quad\;P\left(Y\le 0\right)\\
&=P\left(F\left(X\right)=0\right)\\
&=P\left(X\le G\left(0\right)\right)\\
&=0;
\end{aligned}
$$

(3) 当 $y=1$ 时, $P\left(Y\le 1\right)=1$ 恒成立.

综上对 $y\in\left[0,1\right]$ 有 $P\left(Y\le y\right)=y$, 即 $Y=F\left(X\right)$ 服从 $\left(0,1\right)$ 上的均匀分布. $\blacksquare$
