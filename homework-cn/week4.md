# week4

> **定理 1.1.1 (概率测度的性质)**
> 
> 设 $\mu$ 为概率测度. 则: (1) $\mu\left(\varnothing\right)=0$; (2) 可数可加性: 对两两不交 $\left\{E_{n}\right\}$, $\mu\left(\bigcup_{n}E_{n}\right)=\sum_{n}\mu\left(E_{n}\right)$; (3) 下连续性: 若 $E_{n}\uparrow{E}$, 则 $\mu\left(E_{n}\right)\uparrow\mu\left(E\right)$.

> **公式 1.3.1 (由 $X$ 生成的 $\sigma$-代数)**
> 
> $\sigma\left(X\right)=\left\{\left\{X\in{B}\right\}:B\in\mathcal{S}\right\}$ 是使 $X$ 可测的最小 $\sigma$-代数.

> **定义 1.3.3 (简单函数)**
> 
> 函数 $\phi:\Omega\to\mathbb{R}$ 称为简单函数, 若 $\phi\left(\omega\right)=\sum_{m=1}^{n}c_{m}\mathbf{1}_{A_{m}}\left(\omega\right)$, 其中 $c_{m}\in\mathbb{R}$, $A_{m}\in\mathcal{F}$.

> **定理 1.3.7 (随机变量的极限运算)**
> 
> 若 $X_{1},X_{2},\dots$ 是随机变量, 则 $\inf_{n}X_{n}$, $\sup_{n}X_{n}$, $\limsup_{n}X_{n}$, $\liminf_{n}X_{n}$ 都是随机变量. 故 $\left\{\omega:\lim_{n}X_{n}\text{~存在}\right\}=\left\{\omega:\limsup_{n}X_{n}-\liminf_{n}X_{n}=0\right\}$ 是可测集.

> **定义 1.4.1 (积分的四步定义)**
> 
> 设 $\mu$ 是 $\left(\Omega,\mathcal{F}\right)$ 上的 $\sigma$-有限测度. (1) 简单函数 $\phi=\sum_{i}a_{i}\mathbf{1}_{A_{i}}$ ($A_{i}$ 两两不交, $\mu\left(A_{i}\right)<\infty$) 的积分为 $\int\phi\,\mathrm{d}\mu=\sum_{i}a_{i}\mu\left(A_{i}\right)$; (2) 非负有界,在有限测度集外为零的 $f$ 的积分为 $\int{f}\,\mathrm{d}\mu=\sup_{\phi\le{f}}\int\phi\,\mathrm{d}\mu$; (3) 非负可测 $f$ 的积分为 $\int{f}\,\mathrm{d}\mu=\sup\left\{\int{h}\,\mathrm{d}\mu:0\le{h}\le{f},\,h\text{~有界且~}\mu\left(\left\{h>0\right\}\right)<\infty\right\}$; (4) 一般可测 $f$ 若 $\int\left|f\right|\,\mathrm{d}\mu<\infty$ 称可积, $\int{f}\,\mathrm{d}\mu=\int{f}^{+}\,\mathrm{d}\mu-\int{f}^{-}\,\mathrm{d}\mu$, 其中 $f^{+}=f\vee0$, $f^{-}=\left(-f\right)\vee0$.

> **定理 1.4.7 (积分的基本性质)**
> 
> 设 $f,g$ 可积, 则: (1) 若 $f\ge0$ 几乎处处, 则 $\int{f}\,\mathrm{d}\mu\ge0$; (2) 对 $a\in\mathbb{R}$, $\int{a}f\,\mathrm{d}\mu=a\int{f}\,\mathrm{d}\mu$; (3) $\int\left(f+g\right)\,\mathrm{d}\mu=\int{f}\,\mathrm{d}\mu+\int{g}\,\mathrm{d}\mu$; (4) 若 $g\le{f}$ 几乎处处, 则 $\int{g}\,\mathrm{d}\mu\le\int{f}\,\mathrm{d}\mu$.

> **定理 1.5.7 (单调收敛定理)**
> 
> 若 $0\le{f}_{n}$ 且 $f_{n}\uparrow{f}$ 逐点, 则 $\int{f}_{n}\,\mathrm{d}\mu\uparrow\int{f}\,\mathrm{d}\mu$.

## 1

给出解答 2的构造性证明: 由

$$
\left\{m2^{-n}\le{Y}<\left(m+1\right)2^{-n}\right\}=\left\{X\in{B}_{m,n}\right\}
$$

(某 $B_{m,n}\in\mathcal{R}$), 令 $f_{n}\left(x\right)=m2^{-n}$ ($x\in{B}_{m,n}$), 证明当 $n\to\infty$ 时 $f_{n}\left(x\right)\to{f}\left(x\right)$ 且 $Y=f\left(X\right)$.

### 解答 1

因 $Y$ 关于 $\sigma\left(X\right)$ 可测, 集合

$$
\left\{m2^{-n}\le{Y}<\left(m+1\right)2^{-n}\right\}\in\sigma\left(X\right),
$$

故存在 $B_{m,n}\in\mathcal{R}$ 使该集合等于 $\left\{X\in{B}_{m,n}\right\}$. 对每个 $n$, 令

$$
f_{n}\left(x\right)=\sum_{m}m2^{-n}\mathbf{1}_{B_{m,n}}\left(x\right),
$$

$f_{n}$ 是 $\mathbb{R}$ 上的阶梯简单函数, 故可测. 由构造, 当 $m2^{-n}\le{Y}\left(\omega\right)<\left(m+1\right)2^{-n}$ 时 $f_{n}\left(X\left(\omega\right)\right)=m2^{-n}$, 因此 $f_{n}\left(X\right)$ 恰是把 $Y$ 向下取整到 $2^{-n}$ 的倍数:

$$
f_{n}\left(X\left(\omega\right)\right)\le{Y}\left(\omega\right)<{}f_{n}\left(X\left(\omega\right)\right)+2^{-n}.
$$

于是

$$
\left|f_{n}\left(X\left(\omega\right)\right)-Y\left(\omega\right)\right|<2^{-n}\to0,
$$

即 $f_{n}\left(X\right)\to{Y}$ 逐点.

令 $f=\lim_{n}f_{n}$ (若个别点不收敛则取 $\limsup$ 使之处处定义, 由**定理 1.3.7 (随机变量的极限运算)** $f$ 可测), 则对每个 $\omega$

$$
f\left(X\left(\omega\right)\right)=\lim_{n}f_{n}\left(X\left(\omega\right)\right)=Y\left(\omega\right),
$$

即 $Y=f\left(X\right)$. $\blacksquare$

## 2

证明: 若 $f\ge0$ 且 $\int{f}\,\mathrm{d}\mu=0$, 则 $f=0$ 几乎处处.

### 解答 2

设 $E=\left\{x:f\left(x\right)>0\right\}$. 对每个 $n\ge1$ 记 $E_{n}=\left\{x:f\left(x\right)\ge1/n\right\}$, 则 $E_{n}\uparrow{E}$, 故

$$
\mu\left(E\right)=\lim_{n}\mu\left(E_{n}\right)
$$

(测度的下连续性, **定理 1.1.1 (概率测度的性质)** 第 (3) 条).

反设 $\mu\left(E\right)>0$, 则存在 $n$ 使 $\mu\left(E_{n}\right)>0$. 由 $f\ge\left(1/n\right)\mathbf{1}_{E_{n}}$ 及积分的单调性 (**定理 1.4.7 (积分的基本性质)** 第 (1)(4) 条),

$$
\int{f}\,\mathrm{d}\mu\ge\int\frac{1}{n}\mathbf{1}_{E_{n}}\,\mathrm{d}\mu=\frac{1}{n}\mu\left(E_{n}\right)>0,
$$

与 $\int{f}\,\mathrm{d}\mu=0$ 矛盾. 故 $\mu\left(E\right)=0$, 即 $f=0$ 几乎处处. $\blacksquare$

## 3

设 $f\ge0$,

$$
E_{n,m}=\left\{x:m/2^{n}\le{f}\left(x\right)<\left(m+1\right)/2^{n}\right\}.
$$

证明当 $n\uparrow\infty$ 时

$$
\sum_{m=1}^{\infty}\frac{m}{2^{n}}\mu\left(E_{n,m}\right)\uparrow\int{f}\,\mathrm{d}\mu.
$$

### 解答 3

对每个 $n$, 定义简单函数

$$
f_{n}\left(x\right)=\sum_{m=1}^{\infty}\frac{m}{2^{n}}\mathbf{1}_{E_{n,m}}\left(x\right).
$$

由 $E_{n,m}$ 的定义, 在 $f$ 取有限值处有

$$
f_{n}\left(x\right)\le{f}\left(x\right)<{}f_{n}\left(x\right)+2^{-n},
$$

故 $f_{n}\uparrow{f}$ 逐点 (二分法细分使 $f_{n}$ 单调不减且逼近 $f$). 由简单函数积分的定义 (**定义 1.4.1 (积分的四步定义)** 第 (1) 条),

$$
\int{f}_{n}\,\mathrm{d}\mu=\sum_{m=1}^{\infty}\frac{m}{2^{n}}\mu\left(E_{n,m}\right).
$$

依据**定理 1.5.7 (单调收敛定理)**, 由 $f_{n}\uparrow{f}$ 得

$$
\sum_{m=1}^{\infty}\frac{m}{2^{n}}\mu\left(E_{n,m}\right)=\int{f}_{n}\,\mathrm{d}\mu\uparrow\int{f}\,\mathrm{d}\mu.
$$

这正是要证的结论. $\blacksquare$
