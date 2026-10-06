# 作业 8

> **定理 2.1.16** (密度与独立)<br>设 $X_{1},\dots,X_{n}$ 有联合密度 $f$. 若 $f$ 可写成 $f\left(x_{1},\dots,x_{n}\right)=g_{1}\left(x_{1}\right)\cdots g_{n}\left(x_{n}\right)$ ($g_{i}\ge 0$ 可测), 则 $X_{1},\dots,X_{n}$ 独立; 反之, 若 $X_{1},\dots,X_{n}$ 独立且各有密度, 则联合密度为边缘密度之积. (见习题 2.1.1.)

> **定理 2.1.13** (独立变量的乘积期望)<br>若 $X_{1},\dots,X_{n}$ 独立且 (a) 各 $X_{i}\ge 0$, 或 (b) 各 $E\left|X_{i}\right|<\infty$, 则 $$E\left(\prod_{i=1}^{n}X_{i}\right)=\prod_{i=1}^{n}EX_{i}.$$

> **定义 2.1.3** (不相关)<br>若 $EX^{2},EY^{2}<\infty$ 且 $EXY=EX\cdot EY$, 称 $X,Y$ **不相关**. 独立蕴含不相关 (由**定理 2.1.13**), 但不相关不蕴含独立.

> **例 1.6.13** (泊松分布)<br>$Z$ 服从参数为 $\lambda$ 的**泊松分布**, 记 $Z\sim\mathrm{泊松}\left(\lambda\right)$, 指 $P\left(Z=k\right)=e^{-\lambda}\lambda^{k}/k!$, $k=0,1,2,\dots$.

> **习题 2.1.10** (卷积公式)<br>若 $X,Y$ 独立且取整数值, 则 $P\left(X+Y=n\right)=\sum_{m}P\left(X=m\right)P\left(Y=n-m\right)$.

### 习题一

设 $\left(X_{1},\dots,X_{n}\right)$ 有密度 $f\left(x_{1},\dots,x_{n}\right)$, 即

$$
P\left(\left(X_{1},\dots,X_{n}\right)\in A\right)=\int_{A}f\left(x\right)\,\mathrm{d}x
$$

($A\in\mathcal R^{n}$). 若 $f$ 可写成

$$
f\left(x\right)=g_{1}\left(x_{1}\right)\cdots g_{n}\left(x_{n}\right)
$$

($g_{m}\ge 0$ 可测, 不必是概率密度), 证明 $X_{1},\dots,X_{n}$ 独立.

### 解答 习题一

对任意博雷尔集 $A_{1},\dots,A_{n}$, 由联合密度与托内利定理 (**定理 1.7.2**, 被积函数非负可分离):

$$
\begin{aligned}
&\quad\;P\left(X_{1}\in A_{1},\dots,X_{n}\in A_{n}\right)\\
&=\int_{A_{1}\times\cdots\times A_{n}}f\left(x\right)\,\mathrm{d}x\\
&=\prod_{i=1}^{n}\int_{A_{i}}g_{i}\left(x_{i}\right)\,\mathrm{d}x_{i}.
\end{aligned}
$$

另一方面, 取 $A_{i}=\mathbb R$ 代入, 因 $f$ 是概率密度故 $\int f=1$, 得

$$
\prod_{i=1}^{n}\int_{\mathbb R}g_{i}\left(x_{i}\right)\,\mathrm{d}x_{i}=1.
$$

而 $X_{i}$ 的边缘分布为

$$
\begin{aligned}
&\quad\;P\left(X_{i}\in A_{i}\right)\\
&=\int_{\mathbb R^{n}}\mathbf{1}_{A_{i}}\left(x_{i}\right)g_{1}\left(x_{1}\right)\cdots g_{n}\left(x_{n}\right)\,\mathrm{d}x\\
&=\Bigl(\int_{A_{i}}g_{i}\,\mathrm{d}x_{i}\Bigr)\prod_{j\ne i}\int_{\mathbb R}g_{j}\,\mathrm{d}x_{j}.
\end{aligned}
$$

于是

$$
\begin{aligned}
&\quad\;\prod_{i=1}^{n}P\left(X_{i}\in A_{i}\right)\\
&=\Bigl(\prod_{i=1}^{n}\int_{A_{i}}g_{i}\,\mathrm{d}x_{i}\Bigr)\prod_{i=1}^{n}\prod_{j\ne i}\int_{\mathbb R}g_{j}\,\mathrm{d}x_{j}\\
&=\Bigl(\prod_{i=1}^{n}\int_{A_{i}}g_{i}\,\mathrm{d}x_{i}\Bigr)\Bigl(\prod_{j=1}^{n}\int_{\mathbb R}g_{j}\,\mathrm{d}x_{j}\Bigr)^{n-1}.
\end{aligned}
$$

因 $\prod_{j}\int_{\mathbb R}g_{j}=1$, 故

$$
\begin{aligned}
&\quad\;\prod_{i}P\left(X_{i}\in A_{i}\right)\\
&=\prod_{i}\int_{A_{i}}g_{i}\,\mathrm{d}x_{i}\\
&=P\left(X_{1}\in A_{1},\dots,X_{n}\in A_{n}\right).
\end{aligned}
$$

由 $A_{i}$ 任意, $X_{1},\dots,X_{n}$ 独立 (**定义 2.1.2**). $\blacksquare$

### 习题二

设 $\Omega=\left(0,1\right)$, $\mathcal F$ 为博雷尔集, $P$ 为勒贝格测度. 证明 $X_{n}\left(\omega\right)=\sin\left(2\pi n\omega\right)$ ($n=1,2,\dots$) 两两不相关但不独立.

### 解答 习题二

先证两两不相关. 对任意正整数 $n$,

$$
\begin{aligned}
&\quad\;EX_{n}\\
&=\int_{0}^{1}\sin\left(2\pi n\omega\right)\,\mathrm{d}\omega\\
&=0,
\end{aligned}
$$

(正弦在一个整周期上的积分为零). 对 $n\ne m$, 由积化和差公式

$$
\sin\left(2\pi n\omega\right)\sin\left(2\pi m\omega\right)=\frac{1}{2}\Bigl(\cos\bigl(2\pi\left(n-m\right)\omega\bigr)-\cos\bigl(2\pi\left(n+m\right)\omega\bigr)\Bigr).
$$

而

$$
\int_{0}^{1}\cos\left(2\pi k\omega\right)\,\mathrm{d}\omega=0
$$

对一切整数 $k\ne 0$ 成立 ($n\ne m$ 时 $n-m\ne 0$ 且 $n+m\ne 0$), 故

$$
\begin{aligned}
&\quad\;EX_{n}X_{m}\\
&=\frac{1}{2}\int_{0}^{1}\Bigl(\cos\left(2\pi\left(n-m\right)\omega\right)-\cos\left(2\pi\left(n+m\right)\omega\right)\Bigr)\,\mathrm{d}\omega\\
&=0\\
&=EX_{n}EX_{m}.
\end{aligned}
$$

所以 $X_{n}$ 两两不相关 (**定义 2.1.3**).

再证不独立. 取 $A=\left\{x:x>1/2\right\}$, $B=\left\{x:x>\sqrt{3}/2\right\}$. 由 $\sin\left(2\pi\omega\right)>1/2$ 得

$$
2\pi\omega\in\left(\pi/6,5\pi/6\right)\ \left(\mathrm{mod}\ 2\pi\right),
$$

即 $\omega\in\left(1/12,5/12\right)$, 故 $P\left(X_{1}>1/2\right)=\lambda\left(1/12,5/12\right)=1/3>0$; 由 $\sin\left(4\pi\omega\right)>\sqrt{3}/2$ 得

$$
\begin{aligned}
&\quad\;P\left(X_{2}>\sqrt{3}/2\right)\\
&=\lambda\bigl(\left(1/12,1/6\right)\cup\left(7/12,2/3\right)\bigr)\\
&=1/6>0.
\end{aligned}
$$

但当 $\omega\in\left(1/12,5/12\right)$ 时, $\sin\left(4\pi\omega\right)$ 的最大值为 $\sqrt{3}/2$ (在端点 $\omega=1/12$ 处), 故 $X_{1}>1/2$ 蕴含 $X_{2}\le\sqrt{3}/2$, 即

$$
P\left(X_{1}>1/2,\,X_{2}>\sqrt{3}/2\right)=0,
$$

而

$$
P\left(X_{1}>1/2\right)P\left(X_{2}>\sqrt{3}/2\right)=1/3\cdot 1/6>0,
$$

二者不等, 故 $X_{1},X_{2}$ 不独立, 从而整列 $X_{n}$ 不独立 (**定义 2.1.2**). $\blacksquare$

### 习题三

设 $X\sim\mathrm{泊松}\left(\lambda\right)$, $Y\sim\mathrm{泊松}\left(\mu\right)$ 独立, 用卷积公式证明 $X+Y\sim\mathrm{泊松}\left(\lambda+\mu\right)$.

### 解答 习题三

$X,Y$ 独立且取非负整数值, 由卷积公式 (**习题 2.1.10**), 对 $n\ge 0$,

$$
\begin{aligned}
&\quad\;P\left(X+Y=n\right)\\
&=\sum_{m=0}^{n}P\left(X=m\right)P\left(Y=n-m\right)\\
&=\sum_{m=0}^{n}\frac{e^{-\lambda}\lambda^{m}}{m!}\cdot\frac{e^{-\mu}\mu^{n-m}}{\left(n-m\right)!}.
\end{aligned}
$$

提出公因子并用二项式定理:

$$
\begin{aligned}
&\quad\;P\left(X+Y=n\right)\\
&=\frac{e^{-\left(\lambda+\mu\right)}}{n!}\sum_{m=0}^{n}\frac{n!}{m!\left(n-m\right)!}\lambda^{m}\mu^{n-m}\\
&=\frac{e^{-\left(\lambda+\mu\right)}}{n!}\left(\lambda+\mu\right)^{n}.
\end{aligned}
$$

这正是参数为 $\lambda+\mu$ 的泊松分布的概率质量函数 (**例 1.6.13**), 故 $X+Y\sim\mathrm{泊松}\left(\lambda+\mu\right)$. $\blacksquare$
