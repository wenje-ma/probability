# 作业 7

> **定理 1.7.2** (富比尼定理)<br>若 $f\ge 0$ 或 $\int\left|f\right|\,\mathrm{d}\left(\mu_{1}\times\mu_{2}\right)<\infty$, 则 $$\int_{X}\int_{Y}f\,\mu_{2}\left(\mathrm{d}y\right)\mu_{1}\left(\mathrm{d}x\right)=\int_{X\times Y}f\,\mathrm{d}\left(\mu_{1}\times\mu_{2}\right)=\int_{Y}\int_{X}f\,\mu_{1}\left(\mathrm{d}x\right)\mu_{2}\left(\mathrm{d}y\right).$$ 特别地, 非负情形可交换积分次序 (托内利).

> **定义 2.1.1** (独立事件)<br>事件 $A,B\in\mathcal F$ 独立指 $P\left(A\cap B\right)=P\left(A\right)P\left(B\right)$. 事件列 $A_{1},\dots,A_{n}$ 独立指对任意 $I\subset\left\{1,\dots,n\right\}$ 有 $P\left(\cap_{i\in I}A_{i}\right)=\prod_{i\in I}P\left(A_{i}\right)$.

> **定义 2.1.2** (独立随机变量)<br>随机变量 $X_{1},\dots,X_{n}$ 独立指对一切博雷尔集 $B_{1},\dots,B_{n}$ 有 $$P\left(X_{1}\in B_{1},\dots,X_{n}\in B_{n}\right)=\prod_{i=1}^{n}P\left(X_{i}\in B_{i}\right).$$

> **定理 2.1.1** (独立与 $\sigma$-代数)<br>(1) 若 $X,Y$ 独立, 则 $\sigma\left(X\right)$ 与 $\sigma\left(Y\right)$ 独立;<br>(2) 若 $\mathcal A_{1},\dots,\mathcal A_{n}$ 独立, 则 $\sigma\left(\mathcal A_{1}\right),\dots,\sigma\left(\mathcal A_{n}\right)$ 独立 (定理 2.1.7). 故验证随机变量独立可只对生成元进行.

### 习题一

设 $\mu$ 是 $\mathbb R$ 上的有限测度, $F\left(x\right)=\mu\left(\left(-\infty,x\right]\right)$. 证明

$$
\int\left(F\left(x+c\right)-F\left(x\right)\right)\,\mathrm{d}x=c\mu\left(\mathbb R\right).
$$

### 解答 习题一

由分布函数性质,

$$
F\left(x+c\right)-F\left(x\right)=\mu\left(\left(x,x+c\right]\right).
$$

于是

$$
\begin{aligned}&\quad\;\int\left(F\left(x+c\right)-F\left(x\right)\right)\,\mathrm{d}x\\
&=\int\mu\left(\left(x,x+c\right]\right)\,\mathrm{d}x\\
&=\int\int\mathbf{1}_{\left(x,x+c\right]}\left(y\right)\,\mu\left(\mathrm{d}y\right)\,\mathrm{d}x.
\end{aligned}
$$

被积函数非负, 由托内利定理 (**定理 1.7.2**) 交换积分次序:

$$
\int\int\mathbf{1}_{\left(x,x+c\right]}\left(y\right)\,\mu\left(\mathrm{d}y\right)\,\mathrm{d}x=\int\int\mathbf{1}_{y-c\le x<y}\,\mathrm{d}x\,\mu\left(\mathrm{d}y\right).
$$

对固定的 $y$,

$$
\int\mathbf{1}_{y-c\le x<y}\,\mathrm{d}x
$$

是长度为 $c$ 的区间 $\left[y-c,y\right)$ 的勒贝格测度, 等于 $c$. 故

$$
\begin{aligned}&\quad\;\int\left(F\left(x+c\right)-F\left(x\right)\right)\,\mathrm{d}x\\
&=\int c\,\mu\left(\mathrm{d}y\right)\\
&=c\mu\left(\mathbb R\right).
\end{aligned}
$$

$\blacksquare$

### 习题二

直接从定义证明: 若 $X$ 与 $Y$ 独立, $f,g$ 是可测函数, 则 $f\left(X\right)$ 与 $g\left(Y\right)$ 独立.

### 解答 习题二

对任意博雷尔集 $A,B\in\mathcal R$, 记

$$
\begin{aligned}\left\{f\left(X\right)\in A\right\}&=\left\{X\in f^{-1}\left(A\right)\right\},\\
\left\{g\left(Y\right)\in B\right\}&=\left\{Y\in g^{-1}\left(B\right)\right\}.
\end{aligned}
$$

因 $f,g$ 可测, $f^{-1}\left(A\right),g^{-1}\left(B\right)\in\mathcal R$. 由 $X,Y$ 独立的定义 (**定义 2.1.2**, 对一切博雷尔集成立),

$$
P\left(X\in f^{-1}\left(A\right),\,Y\in g^{-1}\left(B\right)\right)=P\left(X\in f^{-1}\left(A\right)\right)P\left(Y\in g^{-1}\left(B\right)\right).
$$

即

$$
P\left(f\left(X\right)\in A,\,g\left(Y\right)\in B\right)=P\left(f\left(X\right)\in A\right)P\left(g\left(Y\right)\in B\right).
$$

由于 $A,B$ 任意, $f\left(X\right)$ 与 $g\left(Y\right)$ 独立. $\blacksquare$
