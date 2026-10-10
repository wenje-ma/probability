# 作业 14

> **定义 3.3.1** (特征函数)<br>随机变量 $X$ 的特征函数为 $\phi_{X}\left(t\right)=Ee^{itX}=\int e^{itx}\,\mu\left(\mathrm{d}x\right)$, 其中 $\mu$ 为 $X$ 的分布.

> **定理 3.3.1** (特征函数的性质)<br>(1) $\phi\left(0\right)=1$;<br>(2) $\phi\left(-t\right)=\overline{\phi\left(t\right)}$;<br>(3) $\left|\phi\left(t\right)\right|\le 1$;<br>(4) $\left|\phi\left(t+h\right)-\phi\left(t\right)\right|\le E\left|e^{ihX}-1\right|$, 故 $\phi$ 在 $\mathbb R$ 上一致连续;<br>(5) $Ee^{it\left(aX+b\right)}=e^{itb}\phi\left(at\right)$.

> **定理 3.3.2** (独立和的特征函数)<br>若 $X_{1},X_{2}$ 独立且特征函数为 $\phi_{1},\phi_{2}$, 则 $X_{1}+X_{2}$ 的特征函数为 $\phi_{1}\left(t\right)\phi_{2}\left(t\right)$.

> **定义 3.2.1** (依分布收敛)<br>$X_{n}\Rightarrow X_{\infty}$ (依分布收敛) 指分布函数 $F_{n}\left(x\right)\to F_{\infty}\left(x\right)$ 在 $F_{\infty}$ 的一切连续点上成立.

> **定理 3.2.8** (斯科罗霍德表示)<br>若 $X_{n}\Rightarrow X_{\infty}$, 则存在同一概率空间上的随机变量 $Y_{n}=_{d}X_{n}$ 使 $Y_{n}\to Y_{\infty}=_{d}X_{\infty}$ 几乎处处.

> **定理 1.6.5** (法图引理)<br>若 $Z_{n}\ge 0$, 则 $E\liminf_{n}Z_{n}\le\liminf_{n}EZ_{n}$.

### 习题一

设 $X\sim N\left(0,1\right)$, 密度为 $\left(2\pi\right)^{-1/2}e^{-x^{2}/2}$. 补充完整课堂上关于其特征函数的计算 (参考**例 3.3.5**), 证明 $\phi\left(t\right)=Ee^{itX}=e^{-t^{2}/2}$.

### 解答 习题一

特征函数为

$$
\phi\left(t\right)=\int_{-\infty}^{\infty}e^{itx}\left(2\pi\right)^{-1/2}e^{-x^{2}/2}\,\mathrm{d}x.
$$

第一步, 去掉虚部. 由欧拉公式 $e^{itx}=\cos\left(tx\right)+i\sin\left(tx\right)$, 而 $\sin\left(tx\right)$ 关于 $x$ 是奇函数、$e^{-x^{2}/2}$ 是偶函数, 故

$$
\int\sin\left(tx\right)e^{-x^{2}/2}\,\mathrm{d}x=0,
$$

只剩

$$
\phi\left(t\right)=\int_{-\infty}^{\infty}\cos\left(tx\right)\left(2\pi\right)^{-1/2}e^{-x^{2}/2}\,\mathrm{d}x.
$$

第二步, 对 $t$ 求导 (在积分号下求导, 被积函数关于 $t$ 的导数有可积控制):

$$
\phi'\left(t\right)=\int_{-\infty}^{\infty}\left(-x\right)\sin\left(tx\right)\left(2\pi\right)^{-1/2}e^{-x^{2}/2}\,\mathrm{d}x.
$$

第三步, 对上式分部积分. 令 $u=\sin\left(tx\right)$, $\mathrm{d}v=\left(-x\right)e^{-x^{2}/2}\,\mathrm{d}x$, 则 $v=e^{-x^{2}/2}$, 边界项

$$
\left[\sin\left(tx\right)e^{-x^{2}/2}\right]_{-\infty}^{\infty}=0,
$$

故

$$
\begin{aligned}
&\quad\;\phi'\left(t\right)\\
&=\int_{-\infty}^{\infty}\sin\left(tx\right)\frac{\mathrm{d}}{\mathrm{d}x}\left(e^{-x^{2}/2}\right)\,\mathrm{d}x\\
&=-\int_{-\infty}^{\infty}t\cos\left(tx\right)e^{-x^{2}/2}\,\mathrm{d}x\\
&=-t\phi\left(t\right).
\end{aligned}
$$

第四步, 解微分方程 $\phi'\left(t\right)=-t\phi\left(t\right)$. 令 $\psi\left(t\right)=\phi\left(t\right)e^{t^{2}/2}$, 则

$$
\begin{aligned}
&\quad\;\psi'\left(t\right)\\
&=e^{t^{2}/2}\left(\phi'\left(t\right)+t\phi\left(t\right)\right)\\
&=0.
\end{aligned}
$$

故 $\psi$ 为常数,

$$
\begin{aligned}
&\quad\;\psi\left(t\right)\\
&=\psi\left(0\right)\\
&=\phi\left(0\right)e^{0}\\
&=1
\end{aligned}
$$

(因 $\phi\left(0\right)=Ee^{0}=1$). 于是 $\phi\left(t\right)e^{t^{2}/2}=1$, 即

$$
\phi\left(t\right)=e^{-t^{2}/2}.
$$

(补充: 复平移的物理证明可快速验证:

$$
\int e^{itx}\left(2\pi\right)^{-1/2}e^{-x^{2}/2}\,\mathrm{d}x=e^{-t^{2}/2}\int\left(2\pi\right)^{-1/2}e^{-\left(x-it\right)^{2}/2}\,\mathrm{d}x,
$$

括号内是以均值 $it$ 的正态密度积分, 等于 $1$.) $\blacksquare$

### 习题二

设 $g\ge 0$ 连续. 若 $X_{n}\Rightarrow X_{\infty}$, 证明

$$
\liminf_{n\to\infty}Eg\left(X_{n}\right)\ge Eg\left(X_{\infty}\right).
$$

### 解答 习题二

由**定理 3.2.8** (斯科罗霍德表示), 存在同一概率空间上的随机变量 $Y_{n}=_{d}X_{n}$ 与 $Y_{\infty}=_{d}X_{\infty}$, 使 $Y_{n}\to Y_{\infty}$ 几乎处处. 因 $g$ 连续, $g\left(Y_{n}\right)\to g\left(Y_{\infty}\right)$ 几乎处处.

$g\ge 0$ 且 $g\left(Y_{n}\right)\ge 0$, 由**定理 1.6.5** (法图引理):

$$
\begin{aligned}
&\quad\;\liminf_{n\to\infty}E\,g\left(Y_{n}\right)\\
&\ge E\liminf_{n\to\infty}g\left(Y_{n}\right)\\
&=E\,g\left(Y_{\infty}\right).
\end{aligned}
$$

最后一步用 $g\left(Y_{n}\right)\to g\left(Y_{\infty}\right)$ 几乎处处. 因 $Y_{n}=_{d}X_{n}$ 与 $Y_{\infty}=_{d}X_{\infty}$, $E\,g\left(Y_{n}\right)=E\,g\left(X_{n}\right)$、$E\,g\left(Y_{\infty}\right)=E\,g\left(X_{\infty}\right)$, 代入得

$$
\liminf_{n\to\infty}Eg\left(X_{n}\right)\ge Eg\left(X_{\infty}\right).
$$

$\blacksquare$
