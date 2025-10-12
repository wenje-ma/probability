# week6

> **定理 1.4.7 (积分的基本性质)**
> 
> 设 $f,g$ 可积, 则: (1) 若 $f\ge0$ 几乎处处, 则 $\int{f}\,\mathrm{d}\mu\ge0$; (2) 对 $a\in\mathbb{R}$, $\int{a}f\,\mathrm{d}\mu=a\int{f}\,\mathrm{d}\mu$; (3) $\int\left(f+g\right)\,\mathrm{d}\mu=\int{f}\,\mathrm{d}\mu+\int{g}\,\mathrm{d}\mu$; (4) 若 $g\le{f}$ 几乎处处, 则 $\int{g}\,\mathrm{d}\mu\le\int{f}\,\mathrm{d}\mu$.

> **定理 1.5.7 (单调收敛定理)**
> 
> 若 $0\le{f}_{n}$ 且 $f_{n}\uparrow{f}$ 逐点, 则 $\int{f}_{n}\,\mathrm{d}\mu\uparrow\int{f}\,\mathrm{d}\mu$.

> **定理 1.6.9 (换元公式)**
> 
> 设 $X$ 是取值于 $\left(S,\mathcal{S}\right)$ 的随机元, 分布为 $\mu$ (即 $\mu\left(A\right)=P\left(X\in{A}\right)$). 若 $f:\left(S,\mathcal{S}\right)\to\left(\mathbb{R},\mathcal{R}\right)$ 可测且 $f\ge0$ 或 $E\left|f\left(X\right)\right|<\infty$, 则 $Ef\left(X\right)=\int_{S}f\left(y\right)\,\mu\left(\mathrm{d}y\right)$. 证明用四步法: 指示函数, 简单函数, 非负函数, 一般函数.

> **定理 1.7.2 (富比尼定理)**
> 
> 若 $f\ge0$, 则 (托内利) $\int_{X}\int_{Y}f\,\mu_{2}\left(\mathrm{d}y\right)\mu_{1}\left(\mathrm{d}x\right)=\int_{X\times{Y}}f\,\mathrm{d}\left(\mu_{1}\times\mu_{2}\right)=\int_{Y}\int_{X}f\,\mu_{1}\left(\mathrm{d}x\right)\mu_{2}\left(\mathrm{d}y\right)$. 若 $f$ 可积, 即 $\int\left|f\right|\,\mathrm{d}\left(\mu_{1}\times\mu_{2}\right)<\infty$, 则同样的三重等式成立 (富比尼).

## 2

若

$$
\int_{X}\int_{Y}\left|f\left(x,y\right)\right|\,\mu_{2}\left(\mathrm{d}y\right)\mu_{1}\left(\mathrm{d}x\right)<\infty,
$$

证明

$$
\int_{X}\int_{Y}f\left(x,y\right)\,\mu_{2}\left(\mathrm{d}y\right)\mu_{1}\left(\mathrm{d}x\right)=\int_{X\times{Y}}f\,\mathrm{d}\left(\mu_{1}\times\mu_{2}\right)=\int_{Y}\int_{X}f\left(x,y\right)\,\mu_{1}\left(\mathrm{d}x\right)\mu_{2}\left(\mathrm{d}y\right).
$$

### 解答 2

设 $\nu=\mu_{1}\times\mu_{2}$ 为乘积测度. 由托内利定理 (**定理 1.7.2 (富比尼定理)**, $f\ge0$ 情形),

$$
\int_{X\times{Y}}\left|f\right|\,\mathrm{d}\nu=\int_{X}\int_{Y}\left|f\left(x,y\right)\right|\,\mu_{2}\left(\mathrm{d}y\right)\mu_{1}\left(\mathrm{d}x\right)<\infty,
$$

故 $f$ 关于 $\nu$ 可积. 依据**定理 1.7.2 (富比尼定理)**, 可积函数 $f$ 满足

$$
\int_{X}\int_{Y}f\,\mu_{2}\left(\mathrm{d}y\right)\mu_{1}\left(\mathrm{d}x\right)=\int_{X\times{Y}}f\,\mathrm{d}\nu=\int_{Y}\int_{X}f\,\mu_{1}\left(\mathrm{d}x\right)\mu_{2}\left(\mathrm{d}y\right),
$$

这正是要证的结论.

$\blacksquare$

## 2

直接从定义证明: 若 $X$ 与 $Y$ 独立, $f,g$ 是可测函数, 则 $f\left(X\right)$ 与 $g\left(Y\right)$ 独立.

### 解答 2

对任意博雷尔集 $A,B\in\mathcal{R}$, 记

$$
\left\{f\left(X\right)\in{A}\right\}=\left\{X\in{f}^{-1}\left(A\right)\right\},\quad\left\{g\left(Y\right)\in{B}\right\}=\left\{Y\in{g}^{-1}\left(B\right)\right\}.
$$

因 $f,g$ 可测, $f^{-1}\left(A\right),g^{-1}\left(B\right)\in\mathcal{R}$. 由 $X,Y$ 独立的定义 (**定义 2.1.2 (独立随机变量)**, 对一切博雷尔集成立),

$$
P\left(X\in{f}^{-1}\left(A\right),Y\in{g}^{-1}\left(B\right)\right)=P\left(X\in{f}^{-1}\left(A\right)\right)P\left(Y\in{g}^{-1}\left(B\right)\right).
$$

即

$$
P\left(f\left(X\right)\in{A},g\left(Y\right)\in{B}\right)=P\left(f\left(X\right)\in{A}\right)P\left(g\left(Y\right)\in{B}\right).
$$

由于 $A,B$ 任意, $f\left(X\right)$ 与 $g\left(Y\right)$ 独立.

$\blacksquare$
