# 作业 4

> **定义 1.3.3** (简单函数)<br>函数 $\phi:\Omega\to\mathbb R$ 称为**简单函数**, 若 $\phi\left(\omega\right)=\sum_{m=1}^{n}c_{m}\mathbf{1}_{A_{m}}\left(\omega\right)$, 其中 $c_{m}\in\mathbb R$, $A_{m}\in\mathcal F$.

> **定理 1.3.7** (随机变量的极限运算)<br>若 $X_{1},X_{2},\dots$ 是随机变量, 则 $\inf_{n}X_{n}$、$\sup_{n}X_{n}$、$\limsup_{n}X_{n}$、$\liminf_{n}X_{n}$ 都是随机变量. 故 $\left\{\omega:\lim_{n}X_{n}\text{ 存在}\right\}=\left\{\omega:\limsup_{n}X_{n}-\liminf_{n}X_{n}=0\right\}$ 是可测集.

> **公式 1.3.1** (由 $X$ 生成的 $\sigma$-代数)<br>$\sigma\left(X\right)=\left\{\left\{X\in B\right\}:B\in\mathcal S\right\}$ 是使 $X$ 可测的最小 $\sigma$-代数.

### 习题一

设

$$
\phi\left(\omega\right)=\sum_{m=1}^{n}c_{m}\mathbf{1}_{A_{m}}\left(\omega\right),
$$

其中 $c_{m}\in\mathbb R$, $A_{m}\in\mathcal F$. 证明: $\mathcal F$-可测函数类是最小的包含所有简单函数且对逐点极限封闭的类.

### 解答 习题一

设 $\mathcal M$ 是包含所有简单函数且对逐点极限封闭的最小函数类.

先证 $\mathcal M$ 中的函数都可测. 简单函数显然可测 (**定义 1.3.3**); 可测函数类对逐点极限封闭 (依据**定理 1.3.7**, $\lim_{n}f_{n}=\limsup_{n}f_{n}$ 可测), 故由 $\mathcal M$ 的最小性知 $\mathcal M\subset\left\{\text{可测函数}\right\}$.

再证每个可测函数 $f$ 属于 $\mathcal M$. 分解 $f=f^{+}-f^{-}$, 其中 $f^{+}=f\vee 0$, $f^{-}=\left(-f\right)\vee 0$. 对非负可测函数 $g$, 构造

$$
g_{n}\left(x\right)=\frac{\left[2^{n}g\left(x\right)\right]}{2^{n}}\wedge n,
$$

其中 $\left[x\right]$ 为不超过 $x$ 的最大整数. $g_{n}$ 是取有限值的阶梯简单函数, 且 $g_{n}\uparrow g$ 逐点. 于是取

$$
\begin{aligned}f_{n}&=f_{n}^{+}-f_{n}^{-},\\
f_{n}^{\pm}&=\frac{\left[2^{n}f^{\pm}\right]}{2^{n}}\wedge n.
\end{aligned}
$$

$f_{n}$ 是两个简单函数之差, 仍是简单函数, 故 $f_{n}\in\mathcal M$; 又 $f_{n}\to f$ 逐点 (因 $f_{n}^{\pm}\to f^{\pm}$), 由 $\mathcal M$ 对逐点极限封闭知 $f\in\mathcal M$.

综上, 可测函数类恰为包含简单函数且对逐点极限封闭的最小类. $\blacksquare$

### 习题二

利用上一题结论证明: $Y$ 关于 $\sigma\left(X\right)$ 可测当且仅当 $Y=f\left(X\right)$, 其中 $f:\mathbb R\to\mathbb R$ 可测.

### 解答 习题二

$\left(\Leftarrow\right)$ 若 $Y=f\left(X\right)$ 且 $f$ 可测, 则对任意博雷尔集 $B$ 有

$$
\left\{Y\in B\right\}=\left\{X\in f^{-1}\left(B\right)\right\}\in\sigma\left(X\right)
$$

(因 $f^{-1}\left(B\right)\in\mathcal R$, 见**公式 1.3.1**), 故 $Y$ 关于 $\sigma\left(X\right)$ 可测.

$\left(\Rightarrow\right)$ 设 $Y$ 关于 $\sigma\left(X\right)$ 可测. 先处理简单函数: 若 $\phi=\sum_{m}c_{m}\mathbf{1}_{B_{m}}$ 是 $\sigma\left(X\right)$-可测简单函数, 则 $B_{m}\in\sigma\left(X\right)$, 故 $B_{m}=\left\{X\in C_{m}\right\}$ (某 $C_{m}\in\mathcal R$), 于是

$$
\begin{aligned}&\quad\;\phi\\
&=\sum_{m}c_{m}\mathbf{1}_{C_{m}}\left(X\right)\\
&=g\left(X\right),\\
g&=\sum_{m}c_{m}\mathbf{1}_{C_{m}}\ \text{可测}.
\end{aligned}
$$

由习题一, $Y$ 是 $\sigma\left(X\right)$-可测简单函数列 $\phi_{n}$ 的逐点极限, 每个 $\phi_{n}=g_{n}\left(X\right)$ 且 $g_{n}$ 可测. 令 $f=\limsup_{n}g_{n}$, 则 $f$ 可测 (**定理 1.3.7**), 且对每个 $\omega$,

$$
g_{n}\left(X\left(\omega\right)\right)\to Y\left(\omega\right),
$$

故

$$
\begin{aligned}&\quad\;f\left(X\left(\omega\right)\right)\\
&=\limsup_{n}g_{n}\left(X\left(\omega\right)\right)\\
&=Y\left(\omega\right).
\end{aligned}
$$

即 $Y=f\left(X\right)$. $\blacksquare$

### 习题三

给出习题二的构造性证明: 由

$$
\left\{m2^{-n}\le Y<\left(m+1\right)2^{-n}\right\}=\left\{X\in B_{m,n}\right\}
$$

(某 $B_{m,n}\in\mathcal R$), 令 $f_{n}\left(x\right)=m2^{-n}$ ($x\in B_{m,n}$), 证明当 $n\to\infty$ 时 $f_{n}\left(x\right)\to f\left(x\right)$ 且 $Y=f\left(X\right)$.

### 解答 习题三

因 $Y$ 关于 $\sigma\left(X\right)$ 可测, 集合

$$
\left\{m2^{-n}\le Y<\left(m+1\right)2^{-n}\right\}\in\sigma\left(X\right),
$$

故存在 $B_{m,n}\in\mathcal R$ 使该集合等于 $\left\{X\in B_{m,n}\right\}$. 对每个 $n$, 令

$$
f_{n}\left(x\right)=\sum_{m}m2^{-n}\mathbf{1}_{B_{m,n}}\left(x\right),
$$

$f_{n}$ 是 $\mathbb R$ 上的阶梯简单函数, 故可测. 由构造, 当 $m2^{-n}\le Y\left(\omega\right)<\left(m+1\right)2^{-n}$ 时 $f_{n}\left(X\left(\omega\right)\right)=m2^{-n}$, 因此 $f_{n}\left(X\right)$ 恰是把 $Y$ 向下取整到 $2^{-n}$ 的倍数:

$$
f_{n}\left(X\left(\omega\right)\right)\le Y\left(\omega\right)<f_{n}\left(X\left(\omega\right)\right)+2^{-n}.
$$

于是

$$
\left|f_{n}\left(X\left(\omega\right)\right)-Y\left(\omega\right)\right|<2^{-n}\to 0,
$$

即 $f_{n}\left(X\right)\to Y$ 逐点.

令 $f=\lim_{n}f_{n}$ (若个别点不收敛则取 $\limsup$ 使之处处定义, 由**定理 1.3.7** $f$ 可测), 则对每个 $\omega$

$$
\begin{aligned}&\quad\;f\left(X\left(\omega\right)\right)\\
&=\lim_{n}f_{n}\left(X\left(\omega\right)\right)\\
&=Y\left(\omega\right),
\end{aligned}
$$

即 $Y=f\left(X\right)$. $\blacksquare$
