# week9

> **定理 1.5.7 (单调收敛定理)**
> 
> 若 $0\le{f}_{n}$ 且 $f_{n}\uparrow{f}$ 逐点, 则 $\int{f}_{n}\,\mathrm{d}\mu\uparrow\int{f}\,\mathrm{d}\mu$.

> **定理 1.6.4 (切比雪夫不等式)**
> 
> 若 $\phi:\mathbb{R}\to\mathbb{R}$ 非负, 非降, $\phi\left(a\right)>0$, 则 $P\left(X\ge{a}\right)\le{E}\phi\left(X\right)/\phi\left(a\right)$. 取 $\phi\left(y\right)=y$ 得马尔可夫不等式 $P\left(Y>a\right)\le{E}Y/a$.

> **定理 1.6.9 (换元公式)**
> 
> 设 $X$ 是取值于 $\left(S,\mathcal{S}\right)$ 的随机元, 分布为 $\mu$ (即 $\mu\left(A\right)=P\left(X\in{A}\right)$). 若 $f:\left(S,\mathcal{S}\right)\to\left(\mathbb{R},\mathcal{R}\right)$ 可测且 $f\ge0$ 或 $E\left|f\left(X\right)\right|<\infty$, 则

## 1

设 $f$ 是 $\left[0,1\right]$ 上的可测函数且

$$
\int_{0}^{1}\left|f\left(x\right)\right|^{2}\,\mathrm{d}x<\infty.
$$

$U_{1},U_{2},\dots$ 独立且均服从 $\left[0,1\right]$ 上的均匀分布,

$$
I_{n}=n^{-1}\left(f\left(U_{1}\right)+\dots+f\left(U_{n}\right)\right),
$$

$$
I=\int_{0}^{1}f\left(x\right)\,\mathrm{d}x.
$$

用切比雪夫不等式估计 $P\left(\left|I_{n}-I\right|>a/n^{1/2}\right)$.

### 解答 1

由 $U_{1}$ 服从 $\left(0,1\right)$ 上的均匀分布及**定理 1.6.9 (换元公式)**,

$$
Ef\left(U_{1}\right)=\int_{0}^{1}f\left(x\right)\,\mathrm{d}x=I,
$$

故 $EI_{n}=I$. 记

$$
\sigma^{2}=\int_{0}^{1}f\left(x\right)^{2}\,\mathrm{d}x<\infty,
$$

由 $U_{i}$ 独立同分布,

$$
\mathrm{var}\left(I_{n}\right)=\frac{1}{n}\mathrm{var}\left(f\left(U_{1}\right)\right)\le\frac{1}{n}Ef\left(U_{1}\right)^{2}=\frac{\sigma^{2}}{n},
$$

其中

$$
\mathrm{var}\left(Y\right)=EY^{2}-\left(EY\right)^{2}\le{E}Y^{2}.
$$

由切比雪夫不等式 (**定理 1.6.4 (切比雪夫不等式)**, 取 $\phi\left(x\right)=x^{2}$, 均值 $I$),

$$
P\left(\left|I_{n}-I\right|>a/n^{1/2}\right)\le\frac{\mathrm{var}\left(I_{n}\right)}{\left(a/n^{1/2}\right)^{2}}\le\frac{\sigma^{2}/n}{a^{2}/n}=\frac{\sigma^{2}}{a^{2}}.
$$

即

$$
P\left(\left|I_{n}-I\right|>a/n^{1/2}\right)\le\frac{1}{a^{2}}\int_{0}^{1}f\left(x\right)^{2}\,\mathrm{d}x.
$$

$\blacksquare$

## 2

证明: 若 $X\ge0$ 取整数值, 则 $EX=\sum_{n\ge1}P\left(X\ge{n}\right)$.

### 解答 2

对任意 $\omega$, 记 $X\left(\omega\right)=N$ (非负整数). 则 $\mathbf{1}_{\left\{X\ge{k}\right\}}\left(\omega\right)=1$ 当且仅当 $k\le{N}$, 故

$$
\sum_{k=1}^{\infty}\mathbf{1}_{\left\{X\ge{k}\right\}}\left(\omega\right)=\#\left\{k\ge1:k\le{N}\right\}=N=X\left(\omega\right).
$$

即

$$
X=\sum_{k=1}^{\infty}\mathbf{1}_{\left\{X\ge{k}\right\}}
$$

逐点成立. 各项非负, 由期望的单调收敛定理 (**定理 1.5.7 (单调收敛定理)**) 取期望:

$$
EX=E\left[\sum_{k=1}^{\infty}\mathbf{1}_{\left\{X\ge{k}\right\}}\right]=\sum_{k=1}^{\infty}P\left(X\ge{k}\right),
$$

即 $EX=\sum_{n\ge1}P\left(X\ge{n}\right)$.

$\blacksquare$
