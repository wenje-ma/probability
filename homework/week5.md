# 作业 5

> **定义 1.4.1** (积分的四步定义)<br>设 $\mu$ 是 $\left(\Omega,\mathcal F\right)$ 上的 $\sigma$-有限测度.<br>(1) 简单函数 $\phi=\sum_{i}a_{i}\mathbf{1}_{A_{i}}$ ($A_{i}$ 两两不交, $\mu\left(A_{i}\right)<\infty$) 的积分为 $\int\phi\,\mathrm{d}\mu=\sum_{i}a_{i}\mu\left(A_{i}\right)$;<br>(2) 非负有界、在有限测度集外为零的 $f$ 的积分为 $\int f\,\mathrm{d}\mu=\sup_{\phi\le f}\int\phi\,\mathrm{d}\mu$;<br>(3) 非负可测 $f$ 的积分为 $\int f\,\mathrm{d}\mu=\sup\left\{\int h\,\mathrm{d}\mu:0\le h\le f,\ h\text{ 有界且 }\mu\left(\left\{h>0\right\}\right)<\infty\right\}$;<br>(4) 一般可测 $f$ 若 $\int\left|f\right|\,\mathrm{d}\mu<\infty$ 称**可积**, $\int f\,\mathrm{d}\mu=\int f^{+}\,\mathrm{d}\mu-\int f^{-}\,\mathrm{d}\mu$, 其中 $f^{+}=f\vee 0$, $f^{-}=\left(-f\right)\vee 0$.

> **定理 1.4.7** (积分的基本性质)<br>设 $f,g$ 可积, 则:<br>(1) 若 $f\ge 0$ 几乎处处, 则 $\int f\,\mathrm{d}\mu\ge 0$;<br>(2) 对 $a\in\mathbb R$, $\int af\,\mathrm{d}\mu=a\int f\,\mathrm{d}\mu$;<br>(3) $\int\left(f+g\right)\,\mathrm{d}\mu=\int f\,\mathrm{d}\mu+\int g\,\mathrm{d}\mu$;<br>(4) 若 $g\le f$ 几乎处处, 则 $\int g\,\mathrm{d}\mu\le\int f\,\mathrm{d}\mu$.

> **定理 1.5.7** (单调收敛定理)<br>若 $0\le f_{n}$ 且 $f_{n}\uparrow f$ 逐点, 则 $\int f_{n}\,\mathrm{d}\mu\uparrow\int f\,\mathrm{d}\mu$.

### 习题一

证明: 若 $f\ge 0$ 且 $\int f\,\mathrm{d}\mu=0$, 则 $f=0$ 几乎处处.

### 解答 习题一

设 $E=\left\{x:f\left(x\right)>0\right\}$. 对每个 $n\ge 1$ 记 $E_{n}=\left\{x:f\left(x\right)\ge 1/n\right\}$, 则 $E_{n}\uparrow E$, 故

$$
\mu\left(E\right)=\lim_{n}\mu\left(E_{n}\right)
$$

(测度的下连续性, **定理 1.1.1** (3)).

反设 $\mu\left(E\right)>0$, 则存在 $n$ 使 $\mu\left(E_{n}\right)>0$. 由 $f\ge\left(1/n\right)\mathbf{1}_{E_{n}}$ 及积分的单调性 (**定理 1.4.7** (1)(4)),

$$
\begin{aligned}&\quad\;\int f\,\mathrm{d}\mu\\
&\ge\int\frac{1}{n}\mathbf{1}_{E_{n}}\,\mathrm{d}\mu\\
&=\frac{1}{n}\mu\left(E_{n}\right)\\
&>0,
\end{aligned}
$$

与 $\int f\,\mathrm{d}\mu=0$ 矛盾. 故 $\mu\left(E\right)=0$, 即 $f=0$ 几乎处处. $\blacksquare$

### 习题二

设 $f\ge 0$,

$$
E_{n,m}=\left\{x:m/2^{n}\le f\left(x\right)<\left(m+1\right)/2^{n}\right\}.
$$

证明当 $n\uparrow\infty$ 时

$$
\sum_{m=1}^{\infty}\frac{m}{2^{n}}\mu\left(E_{n,m}\right)\uparrow\int f\,\mathrm{d}\mu.
$$

### 解答 习题二

对每个 $n$, 定义简单函数

$$
f_{n}\left(x\right)=\sum_{m=1}^{\infty}\frac{m}{2^{n}}\mathbf{1}_{E_{n,m}}\left(x\right).
$$

由 $E_{n,m}$ 的定义, 在 $f$ 取有限值处有

$$
f_{n}\left(x\right)\le f\left(x\right)<f_{n}\left(x\right)+2^{-n},
$$

故 $f_{n}\uparrow f$ 逐点 (二分法细分使 $f_{n}$ 单调不减且逼近 $f$). 由简单函数积分的定义 (**定义 1.4.1** (1)),

$$
\int f_{n}\,\mathrm{d}\mu=\sum_{m=1}^{\infty}\frac{m}{2^{n}}\mu\left(E_{n,m}\right).
$$

依据**定理 1.5.7** (单调收敛定理), 由 $f_{n}\uparrow f$ 得

$$
\sum_{m=1}^{\infty}\frac{m}{2^{n}}\mu\left(E_{n,m}\right)=\int f_{n}\,\mathrm{d}\mu\uparrow\int f\,\mathrm{d}\mu.
$$

这正是要证的结论. $\blacksquare$
