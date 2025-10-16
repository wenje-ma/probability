# week7

> **定理 1.7.2 (富比尼定理)**
> 
> 若 $f\ge0$, 则 (托内利) $\int_{X}\int_{Y}f\,\mu_{2}\left(\mathrm{d}y\right)\mu_{1}\left(\mathrm{d}x\right)=\int_{X\times{Y}}f\,\mathrm{d}\left(\mu_{1}\times\mu_{2}\right)=\int_{Y}\int_{X}f\,\mu_{1}\left(\mathrm{d}x\right)\mu_{2}\left(\mathrm{d}y\right)$. 特别地, 非负情形可交换积分次序 (托内利).

> **定义 2.1.2 (独立随机变量)**
> 
> 随机变量 $X_{1},\dots,X_{n}$ 独立指对一切博雷尔集 $B_{1},\dots,B_{n}$ 有 $P\left(X_{1}\in{B}_{1},\dots,X_{n}\in{B}_{n}\right)=\prod_{i=1}^{n}P\left(X_{i}\in{B}_{i}\right)$. ## 1 设 $\mu$ 是 $\mathbb{R}$ 上的有限测度, $F\left(x\right)=\mu\left(\left(-\infty,x\right]\right)$. 证明 $$ \int\left(F\left(x+c\right)-F\left(x\right)\right)\,\mathrm{d}x=c\mu\left(\mathbb{R}\right). $$ 由分布函数性质, $$ F\left(x+c\right)-F\left(x\right)=\mu\left(\left(x,x+c\right]\right). $$ 于是 $$ \int\left(F\left(x+c\right)-F\left(x\right)\right)\,\mathrm{d}x=\int\mu\left(\left(x,x+c\right]\right)\,\mathrm{d}x=\int\int\mathbf{1}_{\left(x,x+c\right]}\left(y\right)\,\mu\left(\mathrm{d}y\right)\,\mathrm{d}x. $$ 被积函数非负, 由托内利定理 (**定理 1.7.2 (富比尼定理)**) 交换积分次序: $$ \int\int\mathbf{1}_{\left(x,x+c\right]}\left(y\right)\,\mu\left(\mathrm{d}y\right)\,\mathrm{d}x=\int\int\mathbf{1}_{y-c\le{x}<{}y}\,\mathrm{d}x\,\mu\left(\mathrm{d}y\right). $$ 对固定的 $y$, $$ \int\mathbf{1}_{y-c\le{x}<{}y}\,\mathrm{d}x $$ 是长度为 $c$ 的区间 $\left[y-c,y\right)$ 的勒贝格测度, 等于 $c$. 故 $$ \int\left(F\left(x+c\right)-F\left(x\right)\right)\,\mathrm{d}x=\int{c}\,\mu\left(\mathrm{d}y\right)=c\mu\left(\mathbb{R}\right). $$ $\blacksquare$

## 3

设 $\left(X_{1},\dots,X_{n}\right)$ 有密度 $f\left(x_{1},\dots,x_{n}\right)$, 即

$$
P\left(\left(X_{1},\dots,X_{n}\right)\in{A}\right)=\int_{A}f\left(x\right)\,\mathrm{d}x
$$

($A\in\mathcal{R}^{n}$). 若 $f$ 可写成

$$
f\left(x\right)=g_{1}\left(x_{1}\right)\cdots{g}_{n}\left(x_{n}\right)
$$

($g_{m}\ge0$ 可测, 不必是概率密度), 证明 $X_{1},\dots,X_{n}$ 独立.

### 解答 3

对任意博雷尔集 $A_{1},\dots,A_{n}$, 由联合密度与托内利定理 (**定理 1.7.2 (富比尼定理)**, 被积函数非负可分离):

$$
P\left(X_{1}\in{A}_{1},\dots,X_{n}\in{A}_{n}\right)=\int_{A_{1}\times\cdots\times{A}_{n}}f\left(x\right)\,\mathrm{d}x=\prod_{i=1}^{n}\int_{A_{i}}g_{i}\left(x_{i}\right)\,\mathrm{d}x_{i}.
$$

另一方面, 取 $A_{i}=\mathbb{R}$ 代入, 因 $f$ 是概率密度故 $\int{f}=1$, 得

$$
\prod_{i=1}^{n}\int_{\mathbb{R}}g_{i}\left(x_{i}\right)\,\mathrm{d}x_{i}=1.
$$

而 $X_{i}$ 的边缘分布为

$$
P\left(X_{i}\in{A}_{i}\right)=\int_{\mathbb{R}^{n}}\mathbf{1}_{A_{i}}\left(x_{i}\right)g_{1}\left(x_{1}\right)\cdots{g}_{n}\left(x_{n}\right)\,\mathrm{d}x=\left(\int_{A_{i}}g_{i}\,\mathrm{d}x_{i}\right)\prod_{j\ne{i}}\int_{\mathbb{R}}g_{j}\,\mathrm{d}x_{j}.
$$

于是

$$
\prod_{i=1}^{n}P\left(X_{i}\in{A}_{i}\right)=\left(\prod_{i=1}^{n}\int_{A_{i}}g_{i}\,\mathrm{d}x_{i}\right)\prod_{i=1}^{n}\prod_{j\ne{i}}\int_{\mathbb{R}}g_{j}\,\mathrm{d}x_{j}=\left(\prod_{i=1}^{n}\int_{A_{i}}g_{i}\,\mathrm{d}x_{i}\right)\left(\prod_{j=1}^{n}\int_{\mathbb{R}}g_{j}\,\mathrm{d}x_{j}\right)^{n-1}.
$$

因 $\prod_{j}\int_{\mathbb{R}}g_{j}=1$, 故

$$
\prod_{i}P\left(X_{i}\in{A}_{i}\right)=\prod_{i}\int_{A_{i}}g_{i}\,\mathrm{d}x_{i}=P\left(X_{1}\in{A}_{1},\dots,X_{n}\in{A}_{n}\right).
$$

由 $A_{i}$ 任意, $X_{1},\dots,X_{n}$ 独立 (**定义 2.1.2 (独立随机变量)**).

$\blacksquare$

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

这正是参数为 $\lambda+\mu$ 的泊松分布的概率质量函数 (**例 1.6.13 (泊松分布)**), 故 $X+Y\sim\mathrm{泊松}\left(\lambda+\mu\right)$.

$\blacksquare$
