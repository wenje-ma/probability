# 作业 3

> **定义 1.3.1** (可测映射)<br>设 $\left(\Omega,\mathcal F\right)$、$\left(S,\mathcal S\right)$ 为可测空间. 若对一切 $B\in\mathcal S$ 有 $X^{-1}\left(B\right)\in\mathcal F$, 则称 $X:\Omega\to S$ 为**可测映射**. 当 $S=\mathbb R^{d}$、$\mathcal S=\mathcal R^{d}$ 且 $d>1$ 时, $X$ 称为**随机向量**; $d=1$ 时称为**随机变量**.

> **定理 1.3.1** (可测性的生成元判据)<br>设 $\mathcal A$ 生成 $\mathcal S$ (即 $\mathcal S$ 是包含 $\mathcal A$ 的最小 $\sigma$-代数). 若对一切 $A\in\mathcal A$ 有 $\left\{X\in A\right\}\in\mathcal F$, 则 $X$ 可测.

> **例 1.3.2** (生成元的选择)<br>在 $\left(\mathbb R,\mathcal R\right)$ 上, 生成元可取 $\left\{\left(-\infty,x\right]:x\in\mathbb R\right\}$ 或 $\left\{\left(-\infty,x\right):x\in\mathbb Q\right\}$; 在 $\left(\mathbb R^{d},\mathcal R^{d}\right)$ 上, 可取 $\left\{\left(a_{1},b_{1}\right)\times\cdots\times\left(a_{d},b_{d}\right):a_{i}<b_{i}\right\}$ 或开集族.

> **定理 1.3.4** (复合可测)<br>若 $X:\left(\Omega,\mathcal F\right)\to\left(S,\mathcal S\right)$ 与 $f:\left(S,\mathcal S\right)\to\left(T,\mathcal T\right)$ 均可测, 则 $f\left(X\right)$ 是 $\left(\Omega,\mathcal F\right)\to\left(T,\mathcal T\right)$ 的可测映射. 特别地, $cX$、$X^{2}$、$\sin X$ 等均为随机变量.

### 习题一

证明: 从 $\mathbb R^{d}\to\mathbb R$ 的连续函数是从 $\left(\mathbb R^{d},\mathcal R^{d}\right)$ 到 $\left(\mathbb R,\mathcal R\right)$ 的可测映射.

### 解答 习题一

设 $f:\mathbb R^{d}\to\mathbb R$ 连续. 对任意 $a\in\mathbb R$, 集合

$$
\left\{x:f\left(x\right)<a\right\}=f^{-1}\left(\left(-\infty,a\right)\right)
$$

是开集, 因为 $\left(-\infty,a\right)$ 是开集而 $f$ 连续. 而 $\mathbb R^{d}$ 中开集均属于博雷尔 $\sigma$-代数 $\mathcal R^{d}$, 故 $\left\{x:f\left(x\right)<a\right\}\in\mathcal R^{d}$.

依据**定理 1.3.1** (可测性的生成元判据), 取生成元族

$$
\mathcal A=\left\{\left(-\infty,a\right):a\in\mathbb R\right\}.
$$

由**例 1.3.2**, $\mathcal A$ 生成 $\mathcal R$ (仅 $\left\{\left(-\infty,a\right):a\in\mathbb Q\right\}$ 已生成之); 而上面已证对一切 $a$ 有 $\left\{f<a\right\}\in\mathcal R^{d}$, 故 $f$ 可测. $\blacksquare$

### 习题二

证明: $\mathcal R^{d}$ 是使所有连续函数都可测的最小 $\sigma$-代数.

### 解答 习题二

设 $\mathcal G$ 为使所有连续函数 $f:\mathbb R^{d}\to\mathbb R$ 都可测的最小 $\sigma$-代数, 即 $\mathcal G$ 是包含所有 $\left\{x:f\left(x\right)\in B\right\}$ ($f$ 连续, $B\in\mathcal R$) 的最小 $\sigma$-代数.

一方面, 由习题一 (1.3.4(i)) 知每个连续函数对 $\left(\mathbb R^{d},\mathcal R^{d}\right)$ 可测, 故 $\mathcal R^{d}$ 是"使所有连续函数可测"的 $\sigma$-代数之一, 从而 $\mathcal G\subset\mathcal R^{d}$.

另一方面, 对任意开集 $U\subset\mathbb R^{d}$, 令 $g_{U}\left(x\right)=d\left(x,U^{c}\right)$ 为 $x$ 到闭集 $U^{c}$ 的距离. 函数 $g_{U}$ 连续, 且 $g_{U}\left(x\right)>0$ 当且仅当 $x\notin U^{c}$, 即 $x\in U$. 于是

$$
\begin{aligned}
&\quad\;U\\
&=\left\{x:g_{U}\left(x\right)>0\right\}\\
&=g_{U}^{-1}\left(\left(0,\infty\right)\right).
\end{aligned}
$$

因 $g_{U}$ 连续, $g_{U}$ 对 $\mathcal G$ 可测 (**定义 1.3.1**), 故 $U\in\mathcal G$. 所有开集 $U$ 生成 $\mathcal R^{d}$, 故 $\mathcal R^{d}\subset\mathcal G$.

两方向合起来得 $\mathcal G=\mathcal R^{d}$. $\blacksquare$
