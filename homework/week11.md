# 作业 11

> **引理 2.2.13** (矩的尾部公式)<br>若 $Y\ge 0$ 且 $p>0$, 则 $$E\left(Y^{p}\right)=\int_{0}^{\infty}py^{p-1}P\left(Y>y\right)\,\mathrm{d}y.$$ 它是"对尾部 $P\left(Y>y\right)$ 逐层积分"思想的体现.

> **定理 1.7.2** (富比尼/托内利定理)<br>对非负可测 $h$ 与任意随机变量 $X$, 若 $H\left(x\right)=\int_{\left(-\infty,x\right]}h\left(y\right)\,\mathrm{d}y$, 则由托内利定理 $$EH\left(X\right)=\int_{-\infty}^{\infty}h\left(y\right)P\left(X\ge y\right)\,\mathrm{d}y.$$ (半开区间含右端点, 故尾部用 $X\ge y$; 这是引理 2.2.13 的推广, 取 $h\left(y\right)=py^{p-1}\mathbf{1}_{\left\{y\ge 0\right\}}$ 即还原.)

### 习题一

若 $X\ge 0$ 取整数值, 写出 $EX^{2}$ 的类似表达式.

### 解答 习题一

用习题 2.2.6(i) 的记号

$$
X=\sum_{k\ge 1}\mathbf{1}_{\left\{X\ge k\right\}}.
$$

将 $X^{2}$ 写成二重和并按 $\max$ 重组: 使 $\max\left(i,j\right)=n$ 的有序正整数对 $\left(i,j\right)$ 恰有 $2n-1$ 个, 故

$$
\begin{aligned}
&\quad\;X^{2}\\
&=\Bigl(\sum_{i\ge 1}\mathbf{1}_{\left\{X\ge i\right\}}\Bigr)\Bigl(\sum_{j\ge 1}\mathbf{1}_{\left\{X\ge j\right\}}\Bigr)\\
&=\sum_{i,j\ge 1}\mathbf{1}_{\left\{X\ge\max\left(i,j\right)\right\}}\\
&=\sum_{n\ge 1}\left(2n-1\right)\mathbf{1}_{\left\{X\ge n\right\}}.
\end{aligned}
$$

各项非负, 由单调收敛定理 (**定理 1.5.7**) 取期望:

$$
EX^{2}=\sum_{n\ge 1}\left(2n-1\right)P\left(X\ge n\right).
$$

这就是 $EX^{2}$ 的尾部表达式. $\blacksquare$

### 习题二

推广**引理 2.2.13** 证明: 若

$$
H\left(x\right)=\int_{\left(-\infty,x\right]}h\left(y\right)\,\mathrm{d}y
$$

且 $h\left(y\right)\ge 0$, 则

$$
EH\left(X\right)=\int_{-\infty}^{\infty}h\left(y\right)P\left(X\ge y\right)\,\mathrm{d}y.
$$

特别情形 $H\left(x\right)=\exp\left(\theta x\right)$ ($\theta>0$) 时给出相应结论.

### 解答 习题二

将 $H$ 写成尾部积分的指示形式. 因

$$
H\left(x\right)=\int_{\left(-\infty,x\right]}h\left(y\right)\,\mathrm{d}y,
$$

代入 $X$ 得

$$
\begin{aligned}
&\quad\;H\left(X\right)\\
&=\int_{\left(-\infty,X\right]}h\left(y\right)\,\mathrm{d}y\\
&=\int_{-\infty}^{\infty}h\left(y\right)\mathbf{1}_{\left\{y\le X\right\}}\,\mathrm{d}y\\
&=\int_{-\infty}^{\infty}h\left(y\right)\mathbf{1}_{\left\{X\ge y\right\}}\,\mathrm{d}y.
\end{aligned}
$$

被积函数非负, 由托内利定理 (**定理 1.7.2**) 交换期望与积分:

$$
\begin{aligned}
&\quad\;EH\left(X\right)\\
&=\int_{-\infty}^{\infty}h\left(y\right)E\bigl[\mathbf{1}_{\left\{X\ge y\right\}}\bigr]\,\mathrm{d}y\\
&=\int_{-\infty}^{\infty}h\left(y\right)P\left(X\ge y\right)\,\mathrm{d}y.
\end{aligned}
$$

当 $H\left(x\right)=\exp\left(\theta x\right)$、$\theta>0$ 时, $h\left(y\right)=H'\left(y\right)=\theta e^{\theta y}$, 代入得

$$
Ee^{\theta X}=\theta\int_{-\infty}^{\infty}e^{\theta y}P\left(X\ge y\right)\,\mathrm{d}y.
$$

$\blacksquare$
