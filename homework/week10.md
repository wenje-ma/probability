# week10

> **定理 1.5.7 (单调收敛定理)**
> 
> 若 $0\le{f}_{n}$ 且 $f_{n}\uparrow{f}$ 逐点, 则 $\int{f}_{n}\,\mathrm{d}\mu\uparrow\int{f}\,\mathrm{d}\mu$.

> **定理 1.6.4 (切比雪夫不等式)**
> 
> 若 $\phi:\mathbb{R}\to\mathbb{R}$ 非负, 非降, $\phi\left(a\right)>0$, 则 $P\left(X\ge{a}\right)\le{E}\phi\left(X\right)/\phi\left(a\right)$. 取 $\phi\left(y\right)=y$ 得马尔可夫不等式 $P\left(Y>a\right)\le{E}Y/a$.

> **定理 1.6.9 (换元公式)**
> 
> 设 $X$ 是取值于 $\left(S,\mathcal{S}\right)$ 的随机元, 分布为 $\mu$ (即 $\mu\left(A\right)=P\left(X\in{A}\right)$). 若 $f:\left(S,\mathcal{S}\right)\to\left(\mathbb{R},\mathcal{R}\right)$ 可测且 $f\ge0$ 或 $E\left|f\left(X\right)\right|<\infty$, 则

## 3

若 $X\ge0$ 取整数值, 写出 $EX^{2}$ 的类似表达式.

### 解答 3

用尾部求和的记号

$$
X=\sum_{k\ge1}\mathbf{1}_{\left\{X\ge{k}\right\}}.
$$

将 $X^{2}$ 写成二重和并按 $\max$ 重组: 使 $\max\left(i,j\right)=n$ 的有序正整数对 $\left(i,j\right)$ 恰有 $2n-1$ 个, 故

$$
X^{2}=\left(\sum_{i\ge1}\mathbf{1}_{\left\{X\ge{i}\right\}}\right)\left(\sum_{j\ge1}\mathbf{1}_{\left\{X\ge{j}\right\}}\right)=\sum_{i,j\ge1}\mathbf{1}_{\left\{X\ge\max\left(i,j\right)\right\}}=\sum_{n\ge1}\left(2n-1\right)\mathbf{1}_{\left\{X\ge{n}\right\}}.
$$

各项非负, 由单调收敛定理 (**定理 1.5.7 (单调收敛定理)**) 取期望:

$$
EX^{2}=\sum_{n\ge1}\left(2n-1\right)P\left(X\ge{n}\right).
$$

这就是 $EX^{2}$ 的尾部表达式.

$\blacksquare$

## 1

推广**引理 2.2.13 (矩的尾部公式)** 证明: 若

$$
H\left(x\right)=\int_{\left(-\infty,x\right]}h\left(y\right)\,\mathrm{d}y
$$

且 $h\left(y\right)\ge0$, 则

$$
EH\left(X\right)=\int_{-\infty}^{\infty}h\left(y\right)P\left(X\ge{y}\right)\,\mathrm{d}y.
$$

特别情形 $H\left(x\right)=\exp\left(\theta{x}\right)$ ($\theta>0$) 时给出相应结论.

### 解答 1

将 $H$ 写成尾部积分的指示形式. 因

$$
H\left(x\right)=\int_{\left(-\infty,x\right]}h\left(y\right)\,\mathrm{d}y,
$$

代入 $X$ 得

$$
H\left(X\right)=\int_{\left(-\infty,X\right]}h\left(y\right)\,\mathrm{d}y=\int_{-\infty}^{\infty}h\left(y\right)\mathbf{1}_{\left\{y\le{X}\right\}}\,\mathrm{d}y=\int_{-\infty}^{\infty}h\left(y\right)\mathbf{1}_{\left\{X\ge{y}\right\}}\,\mathrm{d}y.
$$

被积函数非负, 由托内利定理 (**定理 1.7.2 (富比尼/托内利定理)**) 交换期望与积分:

$$
EH\left(X\right)=\int_{-\infty}^{\infty}h\left(y\right)E\left[\mathbf{1}_{\left\{X\ge{y}\right\}}\right]\,\mathrm{d}y=\int_{-\infty}^{\infty}h\left(y\right)P\left(X\ge{y}\right)\,\mathrm{d}y.
$$

当 $H\left(x\right)=\exp\left(\theta{x}\right)$, $\theta>0$ 时, $h\left(y\right)=H'\left(y\right)=\theta{e}^{\theta{y}}$, 代入得

$$
Ee^{\theta{X}}=\theta\int_{-\infty}^{\infty}e^{\theta{y}}P\left(X\ge{y}\right)\,\mathrm{d}y.
$$

$\blacksquare$
