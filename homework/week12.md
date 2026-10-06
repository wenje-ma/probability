# 作业 12

> **定义 2.3.1** (依概率收敛)<br>$X_{n}\to X$ 依概率指对任意 $\epsilon>0$, $P\left(\left|X_{n}-X\right|>\epsilon\right)\to 0$.

> **定理 1.6.4** (切比雪夫不等式)<br>若 $\phi:\mathbb R\to\mathbb R$ 非负、非降, $\phi\left(a\right)>0$, 则 $P\left(X\ge a\right)\le E\phi\left(X\right)/\phi\left(a\right)$. 取 $\phi\left(y\right)=y$ 得马尔可夫不等式 $P\left(Y>a\right)\le EY/a$.

> **习题 1.4.1**<br>若 $f\ge 0$ 且 $\int f\,\mathrm{d}\mu=0$, 则 $f=0$ 几乎处处.

> **性质** (函数 $g\left(t\right)=t/\left(1+t\right)$)<br>对 $t\ge 0$, $g$ 满足: $g\left(t\right)=0\iff t=0$; $g$ 严格递增, $g\le 1$; $g$ 次可加: $g\left(a+b\right)\le g\left(a\right)+g\left(b\right)$.

### 习题一

证明 (a)

$$
d\left(X,Y\right)=E\Bigl(\dfrac{\left|X-Y\right|}{1+\left|X-Y\right|}\Bigr)
$$

在随机变量集合上定义了一个度量, 即满足: (1) $d\left(X,Y\right)=0$ 当且仅当 $X=Y$ 几乎处处; (2) $d\left(X,Y\right)=d\left(Y,X\right)$; (3) $d\left(X,Z\right)\le d\left(X,Y\right)+d\left(Y,Z\right)$; (b) $d\left(X_{n},X\right)\to 0$ ($n\to\infty$) 当且仅当 $X_{n}\to X$ 依概率.

### 解答 习题一

记 $g\left(t\right)=t/\left(1+t\right)$ ($t\ge 0$).

(a)(1) 因 $g\ge 0$ 且 $g\left(t\right)=0$ 当且仅当 $t=0$, 由**习题 1.4.1** (非负函数积分为零蕴含几乎处处为零),

$$
\begin{aligned}
&\quad\;d\left(X,Y\right)\\
&=0\\
&\iff E\,g\left(\left|X-Y\right|\right)=0\\
&\iff g\left(\left|X-Y\right|\right)=0\ \text{几乎处处}\\
&\iff\left|X-Y\right|=0\ \text{几乎处处}\\
&\iff X=Y\ \text{几乎处处}
\end{aligned}
$$

(a)(2) 由 $\left|X-Y\right|=\left|Y-X\right|$ 立即得 $d\left(X,Y\right)=d\left(Y,X\right)$.

(a)(3) $g$ 非降, 故 $\left|X-Z\right|\le\left|X-Y\right|+\left|Y-Z\right|$ 蕴含

$$
g\left(\left|X-Z\right|\right)\le g\left(\left|X-Y\right|+\left|Y-Z\right|\right);
$$

又 $g$ 次可加, $g\left(a+b\right)\le g\left(a\right)+g\left(b\right)$, 故

$$
g\left(\left|X-Z\right|\right)\le g\left(\left|X-Y\right|\right)+g\left(\left|Y-Z\right|\right).
$$

取期望即得 $d\left(X,Z\right)\le d\left(X,Y\right)+d\left(Y,Z\right)$. 综上 $d$ 是度量.

(b) 先证"依概率收敛 $\Rightarrow$ 度量收敛". 设 $X_{n}\to X$ 依概率. 对 $\epsilon>0$, 因 $g\le 1$ 且在 $\left[0,\epsilon\right]$ 上 $g\le g\left(\epsilon\right)$,

$$
\begin{aligned}
&\quad\;d\left(X_{n},X\right)\\
&=E\,g\left(\left|X_{n}-X\right|\right)\\
&\le g\left(\epsilon\right)P\left(\left|X_{n}-X\right|\le\epsilon\right)+P\left(\left|X_{n}-X\right|>\epsilon\right)\\
&\le g\left(\epsilon\right)+P\left(\left|X_{n}-X\right|>\epsilon\right).
\end{aligned}
$$

令 $n\to\infty$ 得

$$
\limsup_{n}d\left(X_{n},X\right)\le g\left(\epsilon\right),
$$

再令 $\epsilon\to 0$ 得 $d\left(X_{n},X\right)\to 0$.

再证"度量收敛 $\Rightarrow$ 依概率收敛". 设 $d\left(X_{n},X\right)\to 0$. 因 $g$ 严格递增,

$$
\left\{\left|X_{n}-X\right|>\epsilon\right\}=\left\{g\left(\left|X_{n}-X\right|\right)>g\left(\epsilon\right)\right\},
$$

由马尔可夫不等式 (**定理 1.6.4**),

$$
\begin{aligned}
&\quad\;P\left(\left|X_{n}-X\right|>\epsilon\right)\\
&=P\bigl(g\left(\left|X_{n}-X\right|\right)>g\left(\epsilon\right)\bigr)\\
&\le\frac{E\,g\left(\left|X_{n}-X\right|\right)}{g\left(\epsilon\right)}\\
&=\frac{d\left(X_{n},X\right)}{g\left(\epsilon\right)}\\
&\to 0.
\end{aligned}
$$

故 $X_{n}\to X$ 依概率 (**定义 2.3.1**). $\blacksquare$
