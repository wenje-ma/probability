# week11

> **定理 1.6.4 (切比雪夫不等式)**
> 
> 若 $\phi:\mathbb{R}\to\mathbb{R}$ 非负, 非降, $\phi\left(a\right)>0$, 则 $P\left(X\ge{a}\right)\le{E}\phi\left(X\right)/\phi\left(a\right)$. 取 $\phi\left(y\right)=y$ 得马尔可夫不等式 $P\left(Y>a\right)\le{E}Y/a$.

> **定理 1.7.2 (富比尼/托内利定理)**
> 
> 对非负可测 $h$ 与任意随机变量 $X$, 若 $H\left(x\right)=\int_{\left(-\infty,x\right]}h\left(y\right)\,\mathrm{d}y$, 则由托内利定理

> **引理 2.2.13 (矩的尾部公式)**
> 
> 若 $Y\ge0$ 且 $p>0$, 则

> **定义 2.3.1 (依概率收敛)**
> 
> $X_{n}\to{X}$ 依概率指对任意 $\varepsilon>0$, $P\left(\left|X_{n}-X\right|>\varepsilon\right)\to0$.

## 2

证明 (a)

$$
d\left(X,Y\right)=E\left(\frac{\left|X-Y\right|}{1+\left|X-Y\right|}\right)
$$

在随机变量集合上定义了一个度量, 即满足:

(1) $d\left(X,Y\right)=0$ 当且仅当 $X=Y$ 几乎处处;

(2) $d\left(X,Y\right)=d\left(Y,X\right)$;

(3) $d\left(X,Z\right)\le{d}\left(X,Y\right)+d\left(Y,Z\right)$;

(b) $d\left(X_{n},X\right)\to0$ ($n\to\infty$) 当且仅当 $X_{n}\to{X}$ 依概率.

### 解答 2

记 $g\left(t\right)=t/\left(1+t\right)$ ($t\ge0$).

(a)(1) 因 $g\ge0$ 且 $g\left(t\right)=0$ 当且仅当 $t=0$, 由**习题 1.4.1 (积分为零蕴含几乎处处为零)**,

$$
d\left(X,Y\right)=0\Leftrightarrow{E}\,g\left(\left|X-Y\right|\right)=0\Leftrightarrow{g}\left(\left|X-Y\right|\right)=0\;\text{几乎处处}\Leftrightarrow\left|X-Y\right|=0\;\text{几乎处处}\Leftrightarrow{X}=Y\;\text{几乎处处}.
$$

(a)(2) 由 $\left|X-Y\right|=\left|Y-X\right|$ 立即得 $d\left(X,Y\right)=d\left(Y,X\right)$.

(a)(3) $g$ 非降, 故 $\left|X-Z\right|\le\left|X-Y\right|+\left|Y-Z\right|$ 蕴含

$$
g\left(\left|X-Z\right|\right)\le{g}\left(\left|X-Y\right|+\left|Y-Z\right|\right);
$$

又 $g$ 次可加, $g\left(a+b\right)\le{g}\left(a\right)+g\left(b\right)$, 故

$$
g\left(\left|X-Z\right|\right)\le{g}\left(\left|X-Y\right|\right)+g\left(\left|Y-Z\right|\right).
$$

取期望即得 $d\left(X,Z\right)\le{d}\left(X,Y\right)+d\left(Y,Z\right)$. 综上 $d$ 是度量.

(b) 先证"依概率收敛 $\Rightarrow$ 度量收敛". 设 $X_{n}\to{X}$ 依概率. 对 $\varepsilon>0$, 因 $g\le1$ 且在 $\left[0,\varepsilon\right]$ 上 $g\le{g}\left(\varepsilon\right)$,

$$
d\left(X_{n},X\right)=E\,g\left(\left|X_{n}-X\right|\right)\le{g}\left(\varepsilon\right)P\left(\left|X_{n}-X\right|\le\varepsilon\right)+P\left(\left|X_{n}-X\right|>\varepsilon\right)\le{g}\left(\varepsilon\right)+P\left(\left|X_{n}-X\right|>\varepsilon\right).
$$

令 $n\to\infty$ 得

$$
\limsup_{n}d\left(X_{n},X\right)\le{g}\left(\varepsilon\right),
$$

再令 $\varepsilon\to0$ 得 $d\left(X_{n},X\right)\to0$.

再证"度量收敛 $\Rightarrow$ 依概率收敛". 设 $d\left(X_{n},X\right)\to0$. 因 $g$ 严格递增,

$$
\left\{\left|X_{n}-X\right|>\varepsilon\right\}=\left\{g\left(\left|X_{n}-X\right|\right)>g\left(\varepsilon\right)\right\},
$$

由马尔可夫不等式 (**定理 1.6.4 (切比雪夫不等式)**),

$$
P\left(\left|X_{n}-X\right|>\varepsilon\right)=P\left(g\left(\left|X_{n}-X\right|\right)>g\left(\varepsilon\right)\right)\le\frac{E\,g\left(\left|X_{n}-X\right|\right)}{g\left(\varepsilon\right)}=\frac{d\left(X_{n},X\right)}{g\left(\varepsilon\right)}\to0.
$$

故 $X_{n}\to{X}$ 依概率 (**定义 2.3.1 (依概率收敛)**).

$\blacksquare$

## 1

设 $A_{n}$ 是一列独立事件且对一切 $n$ 有 $P\left(A_{n}\right)<1$. 证明 $P\left(\cup_{n}A_{n}\right)=1$ 蕴含 $\sum_{n}P\left(A_{n}\right)=\infty$, 从而 $P\left(A_{n}\;\text{无穷多次}\right)=1$.

### 解答 1

由 $P\left(\cup_{n}A_{n}\right)=1$ 得 $P\left(\cap_{n}A_{n}^{c}\right)=0$. 因 $A_{n}$ 独立, $A_{n}^{c}$ 亦独立, 即对有限个:

$$
P\left(\cap_{n=1}^{N}A_{n}^{c}\right)=\prod_{n=1}^{N}P\left(A_{n}^{c}\right).
$$

故对每个 $N$,

$$
P\left(\bigcap_{n=1}^{N}A_{n}^{c}\right)=\prod_{n=1}^{N}\left(1-P\left(A_{n}\right)\right).
$$

令 $N\to\infty$ 得

$$
\prod_{n=1}^{\infty}\left(1-P\left(A_{n}\right)\right)=P\left(\cap_{n}A_{n}^{c}\right)=0.
$$

反设 $\sum_{n}P\left(A_{n}\right)<\infty$. 因 $P\left(A_{n}\right)<1$ 即 $1-P\left(A_{n}\right)>0$, 且 $\sum{P}\left(A_{n}\right)<\infty$ 保证

$$
\sum\log\left(1-P\left(A_{n}\right)\right)
$$

收敛 ($\log\left(1-x\right)\sim-x$), 故

$$
\prod_{n=1}^{\infty}\left(1-P\left(A_{n}\right)\right)>0,
$$

矛盾. 所以 $\sum_{n}P\left(A_{n}\right)=\infty$.

由**定理 2.3.7 (第二博雷尔-坎泰利引理)** ($A_{n}$ 独立且 $\sum{P}\left(A_{n}\right)=\infty$), $P\left(A_{n}\;\text{无穷多次}\right)=1$.

$\blacksquare$
