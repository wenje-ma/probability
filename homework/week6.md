# 作业 6

> **定理 1.6.9** (换元公式)<br>设 $X$ 是取值于 $\left(S,\mathcal S\right)$ 的随机元, 分布为 $\mu$ (即 $\mu\left(A\right)=P\left(X\in A\right)$). 若 $f:\left(S,\mathcal S\right)\to\left(\mathbb R,\mathcal R\right)$ 可测且 $f\ge 0$ 或 $E\left|f\left(X\right)\right|<\infty$, 则 $$Ef\left(X\right)=\int_{S}f\left(y\right)\,\mu\left(\mathrm{d}y\right).$$ 证明用四步法: 指示函数、简单函数、非负函数、一般函数.

> **定理 1.7.2** (富比尼定理)<br>若 $f\ge 0$, 则 (托内利) $$\int_{X}\int_{Y}f\,\mu_{2}\left(\mathrm{d}y\right)\mu_{1}\left(\mathrm{d}x\right)=\int_{X\times Y}f\,\mathrm{d}\left(\mu_{1}\times\mu_{2}\right)=\int_{Y}\int_{X}f\,\mu_{1}\left(\mathrm{d}x\right)\mu_{2}\left(\mathrm{d}y\right).$$ 若 $f$ 可积, 即 $\int\left|f\right|\,\mathrm{d}\left(\mu_{1}\times\mu_{2}\right)<\infty$, 则同样的三重等式成立 (富比尼).

### 习题一

设概率测度 $\mu$ 满足

$$
\mu\left(A\right)=\int_{A}f\left(x\right)\,\mathrm{d}x
$$

对一切 $A\in\mathcal R$. 仿照**定理 1.6.9** 的分步证法, 证明对满足 $g\ge 0$ 或

$$
\int\left|g\left(x\right)\right|\,\mu\left(\mathrm{d}x\right)<\infty
$$

的 $g$, 有

$$
\int g\left(x\right)\,\mu\left(\mathrm{d}x\right)=\int g\left(x\right)f\left(x\right)\,\mathrm{d}x.
$$

### 解答 习题一

按**定理 1.6.9** 的四步法逐类验证.

(1) 指示函数. 设 $g=\mathbf{1}_{B}$ ($B\in\mathcal R$), 则由假设

$$
\begin{aligned}
&\quad\;\int\mathbf{1}_{B}\left(x\right)\,\mu\left(\mathrm{d}x\right)\\
&=\mu\left(B\right)\\
&=\int_{B}f\left(x\right)\,\mathrm{d}x\\
&=\int\mathbf{1}_{B}\left(x\right)f\left(x\right)\,\mathrm{d}x.
\end{aligned}
$$

(2) 简单函数. 设 $g=\sum_{m}c_{m}\mathbf{1}_{B_{m}}$ ($c_{m}\in\mathbb R$, $B_{m}\in\mathcal R$), 由积分与期望的线性 (**定理 1.4.7**),

$$
\begin{aligned}
&\quad\;\int g\,\mathrm{d}\mu\\
&=\sum_{m}c_{m}\int\mathbf{1}_{B_{m}}\,\mathrm{d}\mu\\
&=\sum_{m}c_{m}\int\mathbf{1}_{B_{m}}f\,\mathrm{d}x\\
&=\int gf\,\mathrm{d}x.
\end{aligned}
$$

(3) 非负函数. 设 $g\ge 0$, 取 $g_{n}=\left(\left[2^{n}g\right]/2^{n}\right)\wedge n$, 则 $g_{n}$ 是简单函数且 $g_{n}\uparrow g$. 由 (2) 与**定理 1.5.7** (单调收敛),

$$
\begin{aligned}
&\quad\;\int g\,\mathrm{d}\mu\\
&=\lim_{n}\int g_{n}\,\mathrm{d}\mu\\
&=\lim_{n}\int g_{n}f\,\mathrm{d}x\\
&=\int gf\,\mathrm{d}x.
\end{aligned}
$$

(4) 一般可积函数. 设

$$
\int\left|g\right|\,\mathrm{d}\mu<\infty,
$$

分解 $g=g^{+}-g^{-}$, $g^{\pm}\ge 0$. 由 (3) 作用于 $g^{+},g^{-}$ 得

$$
\int g^{\pm}\,\mathrm{d}\mu=\int g^{\pm}f\,\mathrm{d}x,
$$

相减得

$$
\begin{aligned}
&\quad\;\int g\,\mathrm{d}\mu\\
&=\int g^{+}\,\mathrm{d}\mu-\int g^{-}\,\mathrm{d}\mu\\
&=\int g^{+}f\,\mathrm{d}x-\int g^{-}f\,\mathrm{d}x\\
&=\int gf\,\mathrm{d}x.
\end{aligned}
$$

四步合起来即得结论. $\blacksquare$

### 习题二

若

$$
\int_{X}\int_{Y}\left|f\left(x,y\right)\right|\,\mu_{2}\left(\mathrm{d}y\right)\mu_{1}\left(\mathrm{d}x\right)<\infty,
$$

证明

$$
\begin{aligned}
&\quad\;\int_{X}\int_{Y}f\left(x,y\right)\,\mu_{2}\left(\mathrm{d}y\right)\mu_{1}\left(\mathrm{d}x\right)\\
&=\int_{X\times Y}f\,\mathrm{d}\left(\mu_{1}\times\mu_{2}\right)\\
&=\int_{Y}\int_{X}f\left(x,y\right)\,\mu_{1}\left(\mathrm{d}x\right)\mu_{2}\left(\mathrm{d}y\right).
\end{aligned}
$$

### 解答 习题二

设 $\nu=\mu_{1}\times\mu_{2}$ 为乘积测度. 由托内利定理 (**定理 1.7.2**, $f\ge 0$ 情形),

$$
\int_{X\times Y}\left|f\right|\,\mathrm{d}\nu=\int_{X}\int_{Y}\left|f\left(x,y\right)\right|\,\mu_{2}\left(\mathrm{d}y\right)\mu_{1}\left(\mathrm{d}x\right)<\infty,
$$

故 $f$ 关于 $\nu$ 可积. 依据**定理 1.7.2** (富比尼), 可积函数 $f$ 满足

$$
\begin{aligned}
&\quad\;\int_{X}\int_{Y}f\,\mu_{2}\left(\mathrm{d}y\right)\mu_{1}\left(\mathrm{d}x\right)\\
&=\int_{X\times Y}f\,\mathrm{d}\nu\\
&=\int_{Y}\int_{X}f\,\mu_{1}\left(\mathrm{d}x\right)\mu_{2}\left(\mathrm{d}y\right),
\end{aligned}
$$

这正是要证的结论. $\blacksquare$
