# 作业 9

> **定理 1.6.4** (切比雪夫不等式)<br>若 $\phi:\mathbb R\to\mathbb R$ 非负、非降, $\phi\left(a\right)>0$, 则 $P\left(X\ge a\right)\le E\phi\left(X\right)/\phi\left(a\right)$. 取 $\phi\left(x\right)=x^{2}$ 得 $P\left(\left|X-EX\right|\ge a\right)\le\mathrm{var}\left(X\right)/a^{2}$.

> **定理 2.2.1** (不相关变量的方差可加)<br>若 $X_{1},\dots,X_{n}$ 平方可积且两两不相关, 则 $\mathrm{var}\left(X_{1}+\dots+X_{n}\right)=\mathrm{var}\left(X_{1}\right)+\dots+\mathrm{var}\left(X_{n}\right)$. 对 $c\in\mathbb R$ 有 $\mathrm{var}\left(cY\right)=c^{2}\mathrm{var}\left(Y\right)$.

> **引理 2.2.2** (L$^{p}$ 收敛蕴含依概率收敛)<br>若 $p>0$ 且 $E\left|Z_{n}\right|^{p}\to 0$, 则 $Z_{n}\to 0$ 依概率. 它是切比雪夫不等式取 $\phi\left(x\right)=x^{p}$ 的直接推论.

> **定理 2.2.3** (L$^{2}$ 弱大数定律)<br>若 $X_{1},X_{2},\dots$ 两两不相关, $EX_{i}=\mu$, $\mathrm{var}\left(X_{i}\right)\le C<\infty$, $S_{n}=X_{1}+\dots+X_{n}$, 则当 $n\to\infty$ 时 $S_{n}/n\to\mu$ 在 $L^{2}$ 中且依概率.

### 习题一

设 $X_{1},X_{2},\dots$ 两两不相关, $EX_{i}=\mu_{i}$, 且当 $i\to\infty$ 时 $\mathrm{var}\left(X_{i}\right)/i\to 0$. 设 $S_{n}=X_{1}+\dots+X_{n}$, $\nu_{n}=ES_{n}/n$. 证明当 $n\to\infty$ 时 $S_{n}/n-\nu_{n}\to 0$ 在 $L^{2}$ 中且依概率.

### 解答 习题一

由期望的线性, $E\left(S_{n}/n\right)=\nu_{n}$, 故

$$
\begin{aligned}
&\quad\;E\left(\frac{S_{n}}{n}-\nu_{n}\right)^{2}\\
&=\mathrm{var}\left(\frac{S_{n}}{n}\right)\\
&=\frac{1}{n^{2}}\mathrm{var}\left(S_{n}\right).
\end{aligned}
$$

由 $X_{i}$ 两两不相关及**定理 2.2.1**,

$$
\mathrm{var}\left(S_{n}\right)=\sum_{i=1}^{n}\mathrm{var}\left(X_{i}\right).
$$

下面证

$$
\frac{1}{n^{2}}\sum_{i=1}^{n}\mathrm{var}\left(X_{i}\right)\to 0.
$$

由 $\mathrm{var}\left(X_{i}\right)/i\to 0$, 对任意 $\epsilon>0$ 存在 $N$ 使 $i\ge N$ 时 $\mathrm{var}\left(X_{i}\right)<\epsilon i$. 于是

$$
\begin{aligned}
&\quad\;\frac{1}{n^{2}}\sum_{i=1}^{n}\mathrm{var}\left(X_{i}\right)\\
&\le\frac{1}{n^{2}}\sum_{i<N}\mathrm{var}\left(X_{i}\right)+\frac{\epsilon}{n^{2}}\sum_{i=N}^{n}i\\
&\le\frac{C}{n^{2}}+\frac{\epsilon}{n^{2}}\cdot\frac{n\left(n+1\right)}{2},
\end{aligned}
$$

其中

$$
C=\sum_{i<N}\mathrm{var}\left(X_{i}\right)
$$

为常数. 令 $n\to\infty$ 得

$$
\limsup_{n}\frac{1}{n^{2}}\sum_{i=1}^{n}\mathrm{var}\left(X_{i}\right)\le\epsilon/2,
$$

再令 $\epsilon\to 0$ 得极限为 $0$. 故 $S_{n}/n-\nu_{n}\to 0$ 在 $L^{2}$ 中.

又由**引理 2.2.2** (取 $p=2$, $Z_{n}=S_{n}/n-\nu_{n}$), $L^{2}$ 收敛蕴含依概率收敛, 故 $S_{n}/n-\nu_{n}\to 0$ 依概率. $\blacksquare$

### 习题二

L$^{2}$ 弱大数定律可推广到某些相依序列. 设 $EX_{n}=0$, 且当 $m\le n$ 时 $EX_{n}X_{m}\le r\left(n-m\right)$ (左边不加绝对值!), 其中 $r\left(k\right)\to 0$ ($k\to\infty$). 证明 $\left(X_{1}+\dots+X_{n}\right)/n\to 0$ 依概率.

### 解答 习题二

记 $S_{n}=X_{1}+\dots+X_{n}$. 因 $EX_{n}=0$, $E\left(S_{n}/n\right)=0$. 展开 $E\left(S_{n}^{2}\right)$:

$$
E\left(S_{n}^{2}\right)=\sum_{i=1}^{n}EX_{i}^{2}+\sum_{i\ne j}E\left(X_{i}X_{j}\right).
$$

由假设取 $m=n=i$ 得 $EX_{i}^{2}\le r\left(0\right)$, 故对角项

$$
\sum_{i}EX_{i}^{2}\le n\,r\left(0\right).
$$

对交叉项, $i\ne j$ 时若 $i<j$ 直接由假设得 $E\left(X_{i}X_{j}\right)\le r\left(j-i\right)$; 若 $i>j$, 利用 $E\left(X_{i}X_{j}\right)=E\left(X_{j}X_{i}\right)$ 且 $j<i$, 由假设得 $E\left(X_{j}X_{i}\right)\le r\left(i-j\right)$. 故对一切 $i\ne j$ 有 $E\left(X_{i}X_{j}\right)\le r\left(\left|i-j\right|\right)$, 于是

$$
\begin{aligned}
&\quad\;\sum_{i\ne j}E\left(X_{i}X_{j}\right)\\
&\le\sum_{i\ne j}r\left(\left|i-j\right|\right)\\
&=2\sum_{k=1}^{n-1}\left(n-k\right)r\left(k\right)\\
&\le 2n\sum_{k=1}^{n-1}r\left(k\right).
\end{aligned}
$$

合并得

$$
\begin{aligned}
&\quad\;E\left(\frac{S_{n}}{n}\right)^{2}\\
&=\frac{E\left(S_{n}^{2}\right)}{n^{2}}\\
&\le\frac{r\left(0\right)}{n}+\frac{2}{n}\sum_{k=1}^{n-1}r\left(k\right).
\end{aligned}
$$

由 $r\left(k\right)\to 0$, 其算术平均

$$
\frac{1}{n}\sum_{k=1}^{n-1}r\left(k\right)\to 0
$$

(切萨罗平均收敛). 故 $E\left(S_{n}/n\right)^{2}\to 0$, 即 $S_{n}/n\to 0$ 在 $L^{2}$ 中, 再由**引理 2.2.2** 得 $S_{n}/n\to 0$ 依概率. $\blacksquare$
