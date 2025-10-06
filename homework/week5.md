# week5

> **定理 1.1.1 (概率测度的性质)**
> 
> 设 $\mu$ 为概率测度. 则: (1) $\mu\left(\emptyset\right)=0$; (2) 可数可加性: 对两两不交 $\left\{E_{n}\right\}$, $\mu\left(\bigcup_{n}E_{n}\right)=\sum_{n}\mu\left(E_{n}\right)$; (3) 下连续性: 若 $E_{n}\uparrow{E}$, 则 $\mu\left(E_{n}\right)\uparrow\mu\left(E\right)$.

> **定义 1.3.3 (简单函数)**
> 
> 函数 $\phi:\Omega\to\mathbb{R}$ 称为简单函数, 若 $\phi\left(\omega\right)=\sum_{m=1}^{n}c_{m}\mathbf{1}_{A_{m}}\left(\omega\right)$, 其中 $c_{m}\in\mathbb{R}$, $A_{m}\in\mathcal{F}$.

> **定理 1.3.7 (随机变量的极限运算)**
> 
> 若 $X_{1},X_{2},\dots$ 是随机变量, 则 $\inf_{n}X_{n}$, $\sup_{n}X_{n}$, $\limsup_{n}X_{n}$, $\liminf_{n}X_{n}$ 都是随机变量. 故 $\left\{\omega:\lim_{n}X_{n}\text{~存在}\right\}=\left\{\omega:\limsup_{n}X_{n}-\liminf_{n}X_{n}=0\right\}$ 是可测集.

> **定义 1.4.1 (积分的四步定义)**
> 
> 设 $\mu$ 是 $\left(\Omega,\mathcal{F}\right)$ 上的 $\sigma$-有限测度. (1) 简单函数 $\phi=\sum_{i}a_{i}\mathbf{1}_{A_{i}}$ ($A_{i}$ 两两不交, $\mu\left(A_{i}\right)<\infty$) 的积分为 $\int\phi\,\mathrm{d}\mu=\sum_{i}a_{i}\mu\left(A_{i}\right)$; (2) 非负有界,在有限测度集外为零的 $f$ 的积分为 $\int{f}\,\mathrm{d}\mu=\sup_{\phi\le{f}}\int\phi\,\mathrm{d}\mu$; (3) 非负可测 $f$ 的积分为 $\int{f}\,\mathrm{d}\mu=\sup\left\{\int{h}\,\mathrm{d}\mu:0\le{h}\le{f},h\text{~有界且~}\mu\left(\left\{h>0\right\}\right)<\infty\right\}$; (4) 一般可测 $f$ 若 $\int\left|f\right|\,\mathrm{d}\mu<\infty$ 称可积, $\int{f}\,\mathrm{d}\mu=\int{f}^{+}\,\mathrm{d}\mu-\int{f}^{-}\,\mathrm{d}\mu$, 其中 $f^{+}=f\vee0$, $f^{-}=\left(-f\right)\vee0$.

> **定理 1.4.7 (积分的基本性质)**
> 
> 设 $f,g$ 可积, 则: (1) 若 $f\ge0$ 几乎处处, 则 $\int{f}\,\mathrm{d}\mu\ge0$; (2) 对 $a\in\mathbb{R}$, $\int{a}f\,\mathrm{d}\mu=a\int{f}\,\mathrm{d}\mu$; (3) $\int\left(f+g\right)\,\mathrm{d}\mu=\int{f}\,\mathrm{d}\mu+\int{g}\,\mathrm{d}\mu$; (4) 若 $g\le{f}$ 几乎处处, 则 $\int{g}\,\mathrm{d}\mu\le\int{f}\,\mathrm{d}\mu$.

> **定理 1.5.7 (单调收敛定理)**
> 
> 若 $0\le{f}_{n}$ 且 $f_{n}\uparrow{f}$ 逐点, 则 $\int{f}_{n}\,\mathrm{d}\mu\uparrow\int{f}\,\mathrm{d}\mu$.

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

故 $f_{n}\uparrow{f}$ 逐点 (二分法细分使 $f_{n}$ 单调不减且逼近 $f$). 由**定义 1.3.3 (简单函数)**积分的定义 (**定义 1.4.1 (积分的四步定义)** 第 (1) 条),

$$
\int{f}_{n}\,\mathrm{d}\mu=\sum_{m=1}^{\infty}\frac{m}{2^{n}}\mu\left(E_{n,m}\right).
$$

依据**定理 1.5.7 (单调收敛定理)**, 由 $f_{n}\uparrow{f}$ 得

$$
\sum_{m=1}^{\infty}\frac{m}{2^{n}}\mu\left(E_{n,m}\right)=\int{f}_{n}\,\mathrm{d}\mu\uparrow\int{f}\,\mathrm{d}\mu.
$$

这正是要证的结论.

$\blacksquare$

## 1

设概率测度 $\mu$ 满足

$$
\mu\left(A\right)=\int_{A}f\left(x\right)\,\mathrm{d}x
$$

对一切 $A\in\mathcal{R}$. 仿照**定理 1.6.9 (换元公式)** 的分步证法, 证明对满足 $g\ge0$ 或

$$
\int\left|g\left(x\right)\right|\,\mu\left(\mathrm{d}x\right)<\infty
$$

的 $g$, 有

$$
\int{g}\left(x\right)\,\mu\left(\mathrm{d}x\right)=\int{g}\left(x\right)f\left(x\right)\,\mathrm{d}x.
$$

### 解答 1

按**定理 1.6.9 (换元公式)** 的四步法逐类验证.

(1) 指示函数. 设 $g=\mathbf{1}_{B}$ ($B\in\mathcal{R}$), 则由假设

$$
\int\mathbf{1}_{B}\left(x\right)\,\mu\left(\mathrm{d}x\right)=\mu\left(B\right)=\int_{B}f\left(x\right)\,\mathrm{d}x=\int\mathbf{1}_{B}\left(x\right)f\left(x\right)\,\mathrm{d}x.
$$

(2) 简单函数. 设 $g=\sum_{m}c_{m}\mathbf{1}_{B_{m}}$ ($c_{m}\in\mathbb{R}$, $B_{m}\in\mathcal{R}$), 由积分与期望的线性 (**定理 1.4.7 (积分的基本性质)**),

$$
\int{g}\,\mathrm{d}\mu=\sum_{m}c_{m}\int\mathbf{1}_{B_{m}}\,\mathrm{d}\mu=\sum_{m}c_{m}\int\mathbf{1}_{B_{m}}f\,\mathrm{d}x=\int{g}f\,\mathrm{d}x.
$$

(3) 非负函数. 设 $g\ge0$, 取 $g_{n}=\left(\left[2^{n}g\right]/2^{n}\right)\wedge{n}$, 则 $g_{n}$ 是简单函数且 $g_{n}\uparrow{g}$. 由 (2) 与**定理 1.5.7 (单调收敛定理)**,

$$
\int{g}\,\mathrm{d}\mu=\lim_{n}\int{g}_{n}\,\mathrm{d}\mu=\lim_{n}\int{g}_{n}f\,\mathrm{d}x=\int{g}f\,\mathrm{d}x.
$$

(4) 一般可积函数. 设

$$
\int\left|g\right|\,\mathrm{d}\mu<\infty,
$$

分解 $g=g^{+}-g^{-}$, $g^{\pm}\ge0$. 由 (3) 作用于 $g^{+},g^{-}$ 得

$$
\int{g}^{\pm}\,\mathrm{d}\mu=\int{g}^{\pm}f\,\mathrm{d}x,
$$

相减得

$$
\int{g}\,\mathrm{d}\mu=\int{g}^{+}\,\mathrm{d}\mu-\int{g}^{-}\,\mathrm{d}\mu=\int{g}^{+}f\,\mathrm{d}x-\int{g}^{-}f\,\mathrm{d}x=\int{g}f\,\mathrm{d}x.
$$

四步合起来即得结论.

$\blacksquare$
