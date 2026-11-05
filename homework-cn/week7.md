# week7

> **例 1.6.13 (泊松分布)**
> 
> $Z$ 服从参数为 $\lambda$ 的泊松分布, 记 $Z\sim\mathrm{泊松}\left(\lambda\right)$, 指 $P\left(Z=k\right)=e^{-\lambda}\lambda^{k}/k!$, $k=0,1,2,\dots$.

> **定理 1.7.2 (富比尼定理)**
> 
> 若 $f\ge0$, 则 (托内利)

> **定义 2.1.2 (独立随机变量)**
> 
> 随机变量 $X_{1},\dots,X_{n}$ 独立指对一切博雷尔集 $B_{1},\dots,B_{n}$ 有

> **定义 2.1.3 (不相关)**
> 
> 若 $EX^{2},EY^{2}<\infty$ 且 $EXY=EX\cdot{E}Y$, 称 $X,Y$ 不相关. 独立蕴含不相关, 但不相关不蕴含独立.

> **习题 2.1.10 (卷积公式)**
> 
> 若 $X,Y$ 独立且取整数值, 则 $P\left(X+Y=n\right)=\sum_{m}P\left(X=m\right)P\left(Y=n-m\right)$.

> **定理 2.1.13 (独立变量的乘积期望)**
> 
> 若 $X_{1},\dots,X_{n}$ 独立且 (a) 各 $X_{i}\ge0$, 或 (b) 各 $E\left|X_{i}\right|<\infty$, 则

> **定理 2.1.16 (密度与独立)**
> 
> 设 $X_{1},\dots,X_{n}$ 有联合密度 $f$. 若 $f$ 可写成 $f\left(x_{1},\dots,x_{n}\right)=g_{1}\left(x_{1}\right)\cdots{g}_{n}\left(x_{n}\right)$ ($g_{i}\ge0$ 可测), 则 $X_{1},\dots,X_{n}$ 独立; 反之, 若 $X_{1},\dots,X_{n}$ 独立且各有密度, 则联合密度为边缘密度之积.

## 1

设 $\Omega=\left(0,1\right)$, $\mathcal{F}$ 为博雷尔集, $P$ 为勒贝格测度. 证明 $X_{n}\left(\omega\right)=\sin\left(2\pi{n}\omega\right)$ ($n=1,2,\dots$) 两两不相关但不独立.

### 解答 1

先证两两不相关. 对任意正整数 $n$,

$$
EX_{n}=\int_{0}^{1}\sin\left(2\pi{n}\omega\right)\,\mathrm{d}\omega=0,
$$

(正弦在一个整周期上的积分为零). 对 $n\ne{m}$, 由积化和差公式

$$
\sin\left(2\pi{n}\omega\right)\sin\left(2\pi{m}\omega\right)=\frac{1}{2}\left(\cos\left(2\pi\left(n-m\right)\omega\right)-\cos\left(2\pi\left(n+m\right)\omega\right)\right).
$$

而

$$
\int_{0}^{1}\cos\left(2\pi{k}\omega\right)\,\mathrm{d}\omega=0
$$

对一切整数 $k\ne0$ 成立 ($n\ne{m}$ 时 $n-m\ne0$ 且 $n+m\ne0$), 故

$$
EX_{n}X_{m}=\frac{1}{2}\int_{0}^{1}\left(\cos\left(2\pi\left(n-m\right)\omega\right)-\cos\left(2\pi\left(n+m\right)\omega\right)\right)\,\mathrm{d}\omega=0=EX_{n}EX_{m}.
$$

所以 $X_{n}$ 两两不相关 (**定义 2.1.3 (不相关)**).

再证不独立. 取 $A=\left\{x:x>1/2\right\}$, $B=\left\{x:x>\sqrt{3}/2\right\}$. 由 $\sin\left(2\pi\omega\right)>1/2$ 得

$$
2\pi\omega\in\left(\pi/6,5\pi/6\right)\,\left(\mathrm{mod}\,2\pi\right),
$$

即 $\omega\in\left(1/12,5/12\right)$, 故 $P\left(X_{1}>1/2\right)=\lambda\left(1/12,5/12\right)=1/3>0$; 由 $\sin\left(4\pi\omega\right)>\sqrt{3}/2$ 得

$$
P\left(X_{2}>\sqrt{3}/2\right)=\lambda\left(\left(1/12,1/6\right)\cup\left(7/12,2/3\right)\right)=1/6>0.
$$

但当 $\omega\in\left(1/12,5/12\right)$ 时, $\sin\left(4\pi\omega\right)$ 的最大值为 $\sqrt{3}/2$ (在端点 $\omega=1/12$ 处), 故 $X_{1}>1/2$ 蕴含 $X_{2}\le\sqrt{3}/2$, 即

$$
P\left(X_{1}>1/2,\,X_{2}>\sqrt{3}/2\right)=0,
$$

而

$$
P\left(X_{1}>1/2\right)P\left(X_{2}>\sqrt{3}/2\right)=1/3\cdot1/6>0,
$$

二者不等, 故 $X_{1},X_{2}$ 不独立, 从而整列 $X_{n}$ 不独立 (**定义 2.1.2 (独立随机变量)**). $\blacksquare$

## 2

设 $X\sim\mathrm{泊松}\left(\lambda\right)$, $Y\sim\mathrm{泊松}\left(\mu\right)$ 独立, 用卷积公式证明 $X+Y\sim\mathrm{泊松}\left(\lambda+\mu\right)$.

### 解答 2

$X,Y$ 独立且取非负整数值, 由卷积公式 (**习题 2.1.10 (卷积公式)**), 对 $n\ge0$,

$$
P\left(X+Y=n\right)=\sum_{m=0}^{n}P\left(X=m\right)P\left(Y=n-m\right)=\sum_{m=0}^{n}\frac{e^{-\lambda}\lambda^{m}}{m!}\cdot\frac{e^{-\mu}\mu^{n-m}}{\left(n-m\right)!}.
$$

提出公因子并用二项式定理:

$$
P\left(X+Y=n\right)=\frac{e^{-\left(\lambda+\mu\right)}}{n!}\sum_{m=0}^{n}\frac{n!}{m!\left(n-m\right)!}\lambda^{m}\mu^{n-m}=\frac{e^{-\left(\lambda+\mu\right)}}{n!}\left(\lambda+\mu\right)^{n}.
$$

这正是参数为 $\lambda+\mu$ 的泊松分布的概率质量函数 (**例 1.6.13 (泊松分布)**), 故 $X+Y\sim\mathrm{泊松}\left(\lambda+\mu\right)$. $\blacksquare$
