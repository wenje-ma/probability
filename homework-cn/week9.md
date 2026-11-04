# week9

> **定理 1.5.7 (单调收敛定理)**
> 
> 若 $0\le f_{n}$ 且 $f_{n}\uparrow f$ 逐点, 则 $\int f_{n}\,\mathrm{d}\mu\uparrow\int f\,\mathrm{d}\mu$.

> **定理 1.6.4 (切比雪夫不等式)**
> 
> 若 $\phi:\mathbb R\to\mathbb R$ 非负, 非降, $\phi\left(a\right)> 0$, 则 $P\left(X\ge a\right)\le E\phi\left(X\right)/\phi\left(a\right)$. 取 $\phi\left(y\right)=y$ 得马尔可夫不等式 $P\left(Y> a\right)\le EY/a$.

> **定理 1.6.9 (换元公式)**
> 
> 设 $X$ 是取值于 $\left(S,\mathcal S\right)$ 的随机元, 分布为 $\mu$ (即 $\mu\left(A\right)=P\left(X\in A\right)$). 若 $f:\left(S,\mathcal S\right)\to\left(\mathbb R,\mathcal R\right)$ 可测且 $f\ge 0$ 或 $E\left|f\left(X\right)\right|< \infty$, 则

> **定理 1.7.2 (富比尼/托内利定理)**
> 
> 对非负可测 $h$ 与任意随机变量 $X$, 若 $H\left(x\right)=\int_{\left(-\infty,x\right]}h\left(y\right)\,\mathrm{d}y$, 则由托内利定理

$$
EH\left(X\right)=\int_{-\infty}^{\infty}h\left(y\right)P\left(X\ge y\right)\,\mathrm{d}y.
$$
(半开区间含右端点, 故尾部用 $X\ge y$; 这是引理 2.2.13 的推广, 取 $h\left(y\right)=py^{p-1}\mathbf{1}_{\left\{y\ge 0\right\}}$ 即还原.)

> **引理 2.2.13 (矩的尾部公式)**
> 
> 若 $Y\ge 0$ 且 $p> 0$, 则

$$
E\left(Y^{p}\right)=\int_{0}^{\infty}py^{p-1}P\left(Y> y\right)\,\mathrm{d}y.
$$
它是"对尾部 $P\left(Y> y\right)$ 逐层积分"思想的体现.

## 1

设 $f$ 是 $\left[0,1\right]$ 上的可测函数且

$$
\int_{0}^{1}\left|f\left(x\right)\right|^{2}\,\mathrm{d}x< \infty.
$$

$U_{1},U_{2},\dots$ 独立且均服从 $\left[0,1\right]$ 上的均匀分布,

$$
I_{n}=n^{-1}\left(f\left(U_{1}\right)+\dots+f\left(U_{n}\right)\right),
$$

$$
I=\int_{0}^{1}f\left(x\right)\,\mathrm{d}x.
$$

用切比雪夫不等式估计 $P\left(\left|I_{n}-I\right|> a/n^{1/2}\right)$.

### 解答 1

由 $U_{1}$ 服从 $\left(0,1\right)$ 上的均匀分布及**定理 1.6.9 (换元公式)**,

$$
Ef\left(U_{1}\right)=\int_{0}^{1}f\left(x\right)\,\mathrm{d}x=I,
$$

故 $EI_{n}=I$. 记

$$
\sigma^{2}=\int_{0}^{1}f\left(x\right)^{2}\,\mathrm{d}x< \infty,
$$

由 $U_{i}$ 独立同分布,

$$
\mathrm{var}\left(I_{n}\right)=\frac{1}{n}\mathrm{var}\left(f\left(U_{1}\right)\right)\le\frac{1}{n}Ef\left(U_{1}\right)^{2}=\frac{\sigma^{2}}{n},
$$

其中

$$
\mathrm{var}\left(Y\right)=EY^{2}-\left(EY\right)^{2}\le EY^{2}.
$$

由切比雪夫不等式 (**定理 1.6.4 (切比雪夫不等式)**, 取 $\phi\left(x\right)=x^{2}$, 均值 $I$),

$$
P\left(\left|I_{n}-I\right|> a/n^{1/2}\right)\le\frac{\mathrm{var}\left(I_{n}\right)}{\left(a/n^{1/2}\right)^{2}}\le\frac{\sigma^{2}/n}{a^{2}/n}=\frac{\sigma^{2}}{a^{2}}.
$$

即

$$
P\left(\left|I_{n}-I\right|> a/n^{1/2}\right)\le\frac{1}{a^{2}}\int_{0}^{1}f\left(x\right)^{2}\,\mathrm{d}x.
$$

$\blacksquare$

## 2

证明: 若 $X\ge 0$ 取整数值, 则 $EX=\sum_{n\ge 1}P\left(X\ge n\right)$.

### 解答 2

对任意 $\omega$, 记 $X\left(\omega\right)=N$ (非负整数). 则 $\mathbf{1}_{\left\{X\ge k\right\}}\left(\omega\right)=1$ 当且仅当 $k\le N$, 故

$$
\sum_{k=1}^{\infty}\mathbf{1}_{\left\{X\ge k\right\}}\left(\omega\right)=\#\left\{k\ge 1:k\le N\right\}=N=X\left(\omega\right).
$$

即

$$
X=\sum_{k=1}^{\infty}\mathbf{1}_{\left\{X\ge k\right\}}
$$

逐点成立. 各项非负, 由期望的单调收敛定理 (**定理 1.5.7 (单调收敛定理)**) 取期望:

$$
EX=E\left[\sum_{k=1}^{\infty}\mathbf{1}_{\left\{X\ge k\right\}}\right]=\sum_{k=1}^{\infty}P\left(X\ge k\right),
$$

即 $EX=\sum_{n\ge 1}P\left(X\ge n\right)$. $\blacksquare$

## 3

若 $X\ge 0$ 取整数值, 写出 $EX^{2}$ 的类似表达式.

### 解答 3

用尾部求和的记号

$$
X=\sum_{k\ge 1}\mathbf{1}_{\left\{X\ge k\right\}}.
$$

将 $X^{2}$ 写成二重和并按 $\max$ 重组: 使 $\max\left(i,j\right)=n$ 的有序正整数对 $\left(i,j\right)$ 恰有 $2n-1$ 个, 故

$$
X^{2}=\left(\sum_{i\ge 1}\mathbf{1}_{\left\{X\ge i\right\}}\right)\left(\sum_{j\ge 1}\mathbf{1}_{\left\{X\ge j\right\}}\right)=\sum_{i,j\ge 1}\mathbf{1}_{\left\{X\ge\max\left(i,j\right)\right\}}=\sum_{n\ge 1}\left(2n-1\right)\mathbf{1}_{\left\{X\ge n\right\}}.
$$

各项非负, 由单调收敛定理 (**定理 1.5.7 (单调收敛定理)**) 取期望:

$$
EX^{2}=\sum_{n\ge 1}\left(2n-1\right)P\left(X\ge n\right).
$$

这就是 $EX^{2}$ 的尾部表达式. $\blacksquare$
