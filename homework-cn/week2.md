# week2

> **定义 1.2.1 (随机变量)**
> 
> 设 $X$ 是 $\left(\Omega,\mathcal{F},P\right)$ 上的实值函数, 若对每个博雷尔集 $B\subset\mathbb{R}$ 有 $X^{-1}\left(B\right)\in\mathcal{F}$, 则称 $X$ 为随机变量 (或称 $\mathcal{F}$-可测).

> **定理 1.2.1 (分布函数的性质)**
> 
> 设 $F\left(x\right)=P\left(X\le{x}\right)$, 则: (1) $F$ 非降; (2) $\lim_{x\to\infty}F\left(x\right)=1$, $\lim_{x\to-\infty}F\left(x\right)=0$; (3) $F$ 右连续, 即 $\lim_{y\downarrow{x}}F\left(y\right)=F\left(x\right)$; (4) 若 $F\left(x-\right)=\lim_{y\uparrow{x}}F\left(y\right)$, 则 $F\left(x-\right)=P\left(X<{}x\right)$; (5) $P\left(X=x\right)=F\left(x\right)-F\left(x-\right)$.

> **定义 1.2.2 (分布与分布函数)**
> 
> $X$ 在 $\left(\mathbb{R},\mathcal{R}\right)$ 上诱导的概率测度 $\mu\left(A\right)=P\left(X\in{A}\right)$ 称为 $X$ 的分布; 其分布函数为 $F\left(x\right)=P\left(X\le{x}\right)$.

> **定理 1.2.2 (分布函数的逆)**
> 
> 设 $F$ 是分布函数. 定义其逆 $F^{-1}\left(y\right)=\sup\left\{x:F\left(x\right)<{}y\right\}$, $y\in\left(0,1\right)$. 若 $U$ 服从 $\left(0,1\right)$ 上的均匀分布, 则 $F^{-1}\left(U\right)$ 以 $F$ 为分布函数. 该构造也是计算机生成随机变量的标准方法.

> **定义 1.3.1 (可测映射)**
> 
> 设 $\left(\Omega,\mathcal{F}\right)$, $\left(S,\mathcal{S}\right)$ 为可测空间. 若对一切 $B\in\mathcal{S}$ 有 $X^{-1}\left(B\right)\in\mathcal{F}$, 则称 $X:\Omega\to{S}$ 为可测映射. 当 $S=\mathbb{R}^{d}$, $\mathcal{S}=\mathcal{R}^{d}$ 且 $d>1$ 时, $X$ 称为随机向量; $d=1$ 时称为随机变量.

> **定理 1.3.1 (可测性的生成元判据)**
> 
> 设 $\mathcal{A}$ 生成 $\mathcal{S}$ (即 $\mathcal{S}$ 是包含 $\mathcal{A}$ 的最小 $\sigma$-代数). 若对一切 $A\in\mathcal{A}$ 有 $\left\{X\in{A}\right\}\in\mathcal{F}$, 则 $X$ 可测.

> **例 1.3.2 (生成元的选择)**
> 
> 在 $\left(\mathbb{R},\mathcal{R}\right)$ 上, 生成元可取 $\left\{\left(-\infty,x\right]:x\in\mathbb{R}\right\}$ 或 $\left\{\left(-\infty,x\right):x\in\mathbb{Q}\right\}$; 在 $\left(\mathbb{R}^{d},\mathcal{R}^{d}\right)$ 上, 可取 $\left\{\left(a_{1},b_{1}\right)\times\cdots\times\left(a_{d},b_{d}\right):a_{i}<{}b_{i}\right\}$ 或开集族.

> **定理 1.3.4 (复合可测)**
> 
> 若 $X:\left(\Omega,\mathcal{F}\right)\to\left(S,\mathcal{S}\right)$ 与 $f:\left(S,\mathcal{S}\right)\to\left(T,\mathcal{T}\right)$ 均可测, 则 $f\left(X\right)$ 是 $\left(\Omega,\mathcal{F}\right)\to\left(T,\mathcal{T}\right)$ 的可测映射. 特别地, $cX$, $X^{2}$, $\sin{X}$ 等均为随机变量.

## 1

设 $X,Y$ 是 $\left(\Omega,\mathcal{F},P\right)$ 上的随机变量, $A\in\mathcal{F}$. 若 $Z\left(\omega\right)=X\left(\omega\right)$ (当 $\omega\in{A}$), $Z\left(\omega\right)=Y\left(\omega\right)$ (当 $\omega\in{A}^{c}$), 证明 $Z$ 是随机变量.

### 解答 1

对任意博雷尔集 $B\in\mathcal{R}$, 由 $Z$ 的定义 (**定义 1.2.1 (随机变量)**),

$$
Z^{-1}\left(B\right)=\left(A\cap\left\{\omega:X\left(\omega\right)\in{B}\right\}\right)\cup\left(A^{c}\cap\left\{\omega:Y\left(\omega\right)\in{B}\right\}\right).
$$

因 $X,Y$ 是随机变量, $\left\{X\in{B}\right\},\left\{Y\in{B}\right\}\in\mathcal{F}$; 又 $A\in\mathcal{F}$ 且 $\mathcal{F}$ 是 $\sigma$-代数, 故 $A^{c}\in\mathcal{F}$, 进而 $Z^{-1}\left(B\right)\in\mathcal{F}$. 由 $B$ 任意, $Z$ 是随机变量. $\blacksquare$

## 2

设 $F\left(x\right)=P\left(X\le{x}\right)$ 连续, 证明 $Y=F\left(X\right)$ 在 $\left(0,1\right)$ 上均匀分布, 即对 $y\in\left[0,1\right]$ 有 $P\left(Y\le{y}\right)=y$.

### 解答 2

因 $F$ 非降且连续, 定义广义逆 ($0<{}y<1$):

$$
G\left(y\right)=\inf\left\{x:F\left(x\right)\ge{y}\right\}.
$$

由 $F$ 右连续有 $F\left(G\left(y\right)\right)\ge{y}$; 由 $F$ 连续 (从而左连续) 有 $F\left(G\left(y\right)\right)=y$; 且 $F\left(x\right)<{}y$ 当且仅当 $x<{}G\left(y\right)$ (连续性排除了跳跃).

对 $0\le{y}\le1$ 分三种情形:

(1) 当 $0<{}y<1$ 时, 由 $F\left(X\right)\le{y}$ 与 $X\le{G}\left(y\right)$ 等价,

$$
P\left(Y\le{y}\right)=P\left(F\left(X\right)\le{y}\right)=P\left(X\le{G}\left(y\right)\right)=F\left(G\left(y\right)\right)=y;
$$

(2) 当 $y=0$ 时,

$$
G\left(0\right)=\inf\left\{x:F\left(x\right)\ge0\right\}=-\infty,
$$

故

$$
P\left(Y\le0\right)=P\left(F\left(X\right)=0\right)=P\left(X\le{G}\left(0\right)\right)=0;
$$

(3) 当 $y=1$ 时, $P\left(Y\le1\right)=1$ 恒成立.

综上对 $y\in\left[0,1\right]$ 有 $P\left(Y\le{y}\right)=y$, 即 $Y=F\left(X\right)$ 服从 $\left(0,1\right)$ 上的均匀分布. $\blacksquare$

## 3

证明: 从 $\mathbb{R}^{d}\to\mathbb{R}$ 的连续函数是从 $\left(\mathbb{R}^{d},\mathcal{R}^{d}\right)$ 到 $\left(\mathbb{R},\mathcal{R}\right)$ 的可测映射.

### 解答 3

设 $f:\mathbb{R}^{d}\to\mathbb{R}$ 连续. 对任意 $a\in\mathbb{R}$, 集合

$$
\left\{x:f\left(x\right)<{}a\right\}=f^{-1}\left(\left(-\infty,a\right)\right)
$$

是开集, 因为 $\left(-\infty,a\right)$ 是开集而 $f$ 连续. 而 $\mathbb{R}^{d}$ 中开集均属于博雷尔 $\sigma$-代数 $\mathcal{R}^{d}$, 故 $\left\{x:f\left(x\right)<{}a\right\}\in\mathcal{R}^{d}$.

依据**定理 1.3.1 (可测性的生成元判据)**, 取生成元族

$$
\mathcal{A}=\left\{\left(-\infty,a\right):a\in\mathbb{R}\right\}.
$$

由**例 1.3.2 (生成元的选择)**, $\mathcal{A}$ 生成 $\mathcal{R}$ (仅 $\left\{\left(-\infty,a\right):a\in\mathbb{Q}\right\}$ 已生成之); 而上面已证对一切 $a$ 有 $\left\{f<{}a\right\}\in\mathcal{R}^{d}$, 故 $f$ 可测. $\blacksquare$

## 4

证明: $\mathcal{R}^{d}$ 是使所有连续函数都可测的最小 $\sigma$-代数.

### 解答 4

设 $\mathcal{G}$ 为使所有连续函数 $f:\mathbb{R}^{d}\to\mathbb{R}$ 都可测的最小 $\sigma$-代数, 即 $\mathcal{G}$ 是包含所有 $\left\{x:f\left(x\right)\in{B}\right\}$ ($f$ 连续, $B\in\mathcal{R}$) 的最小 $\sigma$-代数.

一方面, 由解答 1 知每个连续函数对 $\left(\mathbb{R}^{d},\mathcal{R}^{d}\right)$ 可测, 故 $\mathcal{R}^{d}$ 是"使所有连续函数可测"的 $\sigma$-代数之一, 从而 $\mathcal{G}\subset\mathcal{R}^{d}$.

另一方面, 对任意开集 $U\subset\mathbb{R}^{d}$, 令 $g_{U}\left(x\right)=d\left(x,U^{c}\right)$ 为 $x$ 到闭集 $U^{c}$ 的距离. 函数 $g_{U}$ 连续, 且 $g_{U}\left(x\right)>0$ 当且仅当 $x\notin{U}^{c}$, 即 $x\in{U}$. 于是

$$
U=\left\{x:g_{U}\left(x\right)>0\right\}=g_{U}^{-1}\left(\left(0,\infty\right)\right).
$$

因 $g_{U}$ 连续, $g_{U}$ 对 $\mathcal{G}$ 可测 (**定义 1.3.1 (可测映射)**), 故 $U\in\mathcal{G}$. 所有开集 $U$ 生成 $\mathcal{R}^{d}$, 故 $\mathcal{R}^{d}\subset\mathcal{G}$.

两方向合起来得 $\mathcal{G}=\mathcal{R}^{d}$. $\blacksquare$
