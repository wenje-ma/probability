# week6

> **例 1.6.13 (泊松分布)**
> 
> $Z$ 服从参数为 $\lambda$ 的泊松分布, 记 $Z\sim\mathrm{泊松}\left(\lambda\right)$, 指 $P\left(Z=k\right)=e^{-\lambda}\lambda^{k}/k!$, $k=0,1,2,\dots$.

> **定理 1.7.2 (富比尼定理)**
> 
> 若 $f\ge 0$, 则 (托内利)

$$
\int_{X}\int_{Y}f\,\mu_{2}\left(\mathrm{d}y\right)\mu_{1}\left(\mathrm{d}x\right)=\int_{X\times Y}f\,\mathrm{d}\left(\mu_{1}\times\mu_{2}\right)=\int_{Y}\int_{X}f\,\mu_{1}\left(\mathrm{d}x\right)\mu_{2}\left(\mathrm{d}y\right).
$$
特别地, 非负情形可交换积分次序 (托内利).

> **定义 2.1.1 (独立事件)**
> 
> 事件 $A,B\in\mathcal F$ 独立指 $P\left(A\cap B\right)=P\left(A\right)P\left(B\right)$. 事件列 $A_{1},\dots,A_{n}$ 独立指对任意 $I\subset\left\{1,\dots,n\right\}$ 有 $P\left(\cap_{i\in I}A_{i}\right)=\prod_{i\in I}P\left(A_{i}\right)$.

> **定理 2.1.1 (独立与 $\sigma$-代数)**
> 
> (1) 若 $X,Y$ 独立, 则 $\sigma\left(X\right)$ 与 $\sigma\left(Y\right)$ 独立; (2) 若 $\mathcal A_{1},\dots,\mathcal A_{n}$ 独立, 则 $\sigma\left(\mathcal A_{1}\right),\dots,\sigma\left(\mathcal A_{n}\right)$ 独立. 故验证随机变量独立可只对生成元进行.

> **定义 2.1.2 (独立随机变量)**
> 
> 随机变量 $X_{1},\dots,X_{n}$ 独立指对一切博雷尔集 $B_{1},\dots,B_{n}$ 有

$$
P\left(X_{1}\in B_{1},\dots,X_{n}\in B_{n}\right)=\prod_{i=1}^{n}P\left(X_{i}\in B_{i}\right).
$$

> **定义 2.1.3 (不相关)**
> 
> 若 $EX^{2},EY^{2}< \infty$ 且 $EXY=EX\cdot EY$, 称 $X,Y$ 不相关. 独立蕴含不相关, 但不相关不蕴含独立.

> **习题 2.1.10 (卷积公式)**
> 
> 若 $X,Y$ 独立且取整数值, 则 $P\left(X+Y=n\right)=\sum_{m}P\left(X=m\right)P\left(Y=n-m\right)$.

> **定理 2.1.13 (独立变量的乘积期望)**
> 
> 若 $X_{1},\dots,X_{n}$ 独立且 (a) 各 $X_{i}\ge 0$, 或 (b) 各 $E\left|X_{i}\right|< \infty$, 则

$$
E\left(\prod_{i=1}^{n}X_{i}\right)=\prod_{i=1}^{n}EX_{i}.
$$

> **定理 2.1.16 (密度与独立)**
> 
> 设 $X_{1},\dots,X_{n}$ 有联合密度 $f$. 若 $f$ 可写成 $f\left(x_{1},\dots,x_{n}\right)=g_{1}\left(x_{1}\right)\cdots g_{n}\left(x_{n}\right)$ ($g_{i}\ge 0$ 可测), 则 $X_{1},\dots,X_{n}$ 独立; 反之, 若 $X_{1},\dots,X_{n}$ 独立且各有密度, 则联合密度为边缘密度之积.

## 1

设 $\mu$ 是 $\mathbb R$ 上的有限测度, $F\left(x\right)=\mu\left(\left(-\infty,x\right]\right)$. 证明

$$
\int\left(F\left(x+c\right)-F\left(x\right)\right)\,\mathrm{d}x=c\mu\left(\mathbb R\right).
$$

### 解答 1

由分布函数性质,

$$
F\left(x+c\right)-F\left(x\right)=\mu\left(\left(x,x+c\right]\right).
$$

于是

$$
\int\left(F\left(x+c\right)-F\left(x\right)\right)\,\mathrm{d}x=\int\mu\left(\left(x,x+c\right]\right)\,\mathrm{d}x=\int\int\mathbf{1}_{\left(x,x+c\right]}\left(y\right)\,\mu\left(\mathrm{d}y\right)\,\mathrm{d}x.
$$

被积函数非负, 由托内利定理 (**定理 1.7.2 (富比尼定理)**) 交换积分次序:

$$
\int\int\mathbf{1}_{\left(x,x+c\right]}\left(y\right)\,\mu\left(\mathrm{d}y\right)\,\mathrm{d}x=\int\int\mathbf{1}_{y-c\le x< y}\,\mathrm{d}x\,\mu\left(\mathrm{d}y\right).
$$

对固定的 $y$,

$$
\int\mathbf{1}_{y-c\le x< y}\,\mathrm{d}x
$$

是长度为 $c$ 的区间 $\left[y-c,y\right)$ 的勒贝格测度, 等于 $c$. 故

$$
\int\left(F\left(x+c\right)-F\left(x\right)\right)\,\mathrm{d}x=\int c\,\mu\left(\mathrm{d}y\right)=c\mu\left(\mathbb R\right).
$$

$\blacksquare$

## 2

直接从定义证明: 若 $X$ 与 $Y$ 独立, $f,g$ 是可测函数, 则 $f\left(X\right)$ 与 $g\left(Y\right)$ 独立.

### 解答 2

对任意博雷尔集 $A,B\in\mathcal R$, 记

$$
\left\{f\left(X\right)\in A\right\}=\left\{X\in f^{-1}\left(A\right)\right\},\qquad\left\{g\left(Y\right)\in B\right\}=\left\{Y\in g^{-1}\left(B\right)\right\}.
$$

因 $f,g$ 可测, $f^{-1}\left(A\right),g^{-1}\left(B\right)\in\mathcal R$. 由 $X,Y$ 独立的定义 (**定义 2.1.2 (独立随机变量)**, 对一切博雷尔集成立),

$$
P\left(X\in f^{-1}\left(A\right),\,Y\in g^{-1}\left(B\right)\right)=P\left(X\in f^{-1}\left(A\right)\right)P\left(Y\in g^{-1}\left(B\right)\right).
$$

即

$$
P\left(f\left(X\right)\in A,\,g\left(Y\right)\in B\right)=P\left(f\left(X\right)\in A\right)P\left(g\left(Y\right)\in B\right).
$$

由于 $A,B$ 任意, $f\left(X\right)$ 与 $g\left(Y\right)$ 独立. $\blacksquare$

## 3

设 $\left(X_{1},\dots,X_{n}\right)$ 有密度 $f\left(x_{1},\dots,x_{n}\right)$, 即

$$
P\left(\left(X_{1},\dots,X_{n}\right)\in A\right)=\int_{A}f\left(x\right)\,\mathrm{d}x
$$

($A\in\mathcal R^{n}$). 若 $f$ 可写成

$$
f\left(x\right)=g_{1}\left(x_{1}\right)\cdots g_{n}\left(x_{n}\right)
$$

($g_{m}\ge 0$ 可测, 不必是概率密度), 证明 $X_{1},\dots,X_{n}$ 独立.

### 解答 3

对任意博雷尔集 $A_{1},\dots,A_{n}$, 由联合密度与托内利定理 (**定理 1.7.2 (富比尼定理)**, 被积函数非负可分离):

$$
P\left(X_{1}\in A_{1},\dots,X_{n}\in A_{n}\right)=\int_{A_{1}\times\cdots\times A_{n}}f\left(x\right)\,\mathrm{d}x=\prod_{i=1}^{n}\int_{A_{i}}g_{i}\left(x_{i}\right)\,\mathrm{d}x_{i}.
$$

另一方面, 取 $A_{i}=\mathbb R$ 代入, 因 $f$ 是概率密度故 $\int f=1$, 得

$$
\prod_{i=1}^{n}\int_{\mathbb R}g_{i}\left(x_{i}\right)\,\mathrm{d}x_{i}=1.
$$

而 $X_{i}$ 的边缘分布为

$$
P\left(X_{i}\in A_{i}\right)=\int_{\mathbb R^{n}}\mathbf{1}_{A_{i}}\left(x_{i}\right)g_{1}\left(x_{1}\right)\cdots g_{n}\left(x_{n}\right)\,\mathrm{d}x=\left(\int_{A_{i}}g_{i}\,\mathrm{d}x_{i}\right)\prod_{j\ne i}\int_{\mathbb R}g_{j}\,\mathrm{d}x_{j}.
$$

于是

$$
\prod_{i=1}^{n}P\left(X_{i}\in A_{i}\right)=\left(\prod_{i=1}^{n}\int_{A_{i}}g_{i}\,\mathrm{d}x_{i}\right)\prod_{i=1}^{n}\prod_{j\ne i}\int_{\mathbb R}g_{j}\,\mathrm{d}x_{j}=\left(\prod_{i=1}^{n}\int_{A_{i}}g_{i}\,\mathrm{d}x_{i}\right)\left(\prod_{j=1}^{n}\int_{\mathbb R}g_{j}\,\mathrm{d}x_{j}\right)^{n-1}.
$$

因 $\prod_{j}\int_{\mathbb R}g_{j}=1$, 故

$$
\prod_{i}P\left(X_{i}\in A_{i}\right)=\prod_{i}\int_{A_{i}}g_{i}\,\mathrm{d}x_{i}=P\left(X_{1}\in A_{1},\dots,X_{n}\in A_{n}\right).
$$

由 $A_{i}$ 任意, $X_{1},\dots,X_{n}$ 独立 (**定义 2.1.2 (独立随机变量)**). $\blacksquare$
