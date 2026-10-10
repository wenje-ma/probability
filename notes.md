# 概率论

## 概率空间与代数

**定义 1.1.1** ($\sigma$-代数)

设 $\Omega$ 非空, 称 $\mathcal F\subset\mathcal P\left(\Omega\right)$ 为 $\Omega$ 上的一个 **$\sigma$-代数**, 若满足:

(1) $\Omega\in\mathcal F$;

(2) 对补运算封闭: $A\in\mathcal F\Rightarrow A^{c}\in\mathcal F$;

(3) 对可数并封闭:

$$
\left\{A_{i}\right\}_{i=1}^{\infty}\subset\mathcal F\Rightarrow\bigcup_{i=1}^{\infty}A_{i}\in\mathcal F.
$$

由 $\cap_{i}A_{i}=\left(\cup_{i}A_{i}^{c}\right)^{c}$, $\sigma$-代数对可数交亦封闭. 此处"可数"指有限或可数无穷.

**定义 1.1.2** (代数)

设 $\Omega$ 非空, $\mathcal F\subset\mathcal P\left(\Omega\right)$. 称 $\mathcal F$ 为 $\Omega$ 上的一个**代数**, 若满足:

(1) $\Omega\in\mathcal F$;

(2) 对补运算封闭: $A\in\mathcal F\Rightarrow A^{c}\in\mathcal F$;

(3) 对有限并封闭: $A,B\in\mathcal F\Rightarrow A\cup B\in\mathcal F$.

**定义 1.1.3** (概率空间与概率测度)

**概率空间**是三元组 $\left(\Omega,\mathcal F,P\right)$, 其中 $\Omega$ 为样本空间, $\mathcal F$ 为事件族 ($\sigma$-代数), $P:\mathcal F\to\left[0,1\right]$ 为**概率测度**, 即满足:

(1) $P\left(\Omega\right)=1$;

(2) 可数可加性: 对两两不交的事件列 $\left\{A_{i}\right\}$,

$$
P\left(\cup_{i}A_{i}\right)=\sum_{i}P\left(A_{i}\right).
$$

更一般地, 满足 (2) 且取值非负的非负可数可加集函数 $\mu$ 称为**测度**.

**定理 1.1.1** (概率测度的性质)

设 $\left(\Omega,\mathcal F,P\right)$ 为概率空间, 则:

(1) $P\left(\varnothing\right)=0$;

(2) 单调性: $A\subset B\Rightarrow P\left(A\right)\le P\left(B\right)$;

(3) 若 $A_{n}\uparrow A$ 则 $P\left(A_{n}\right)\uparrow P\left(A\right)$ (下连续), 若 $A_{n}\downarrow A$ 则 $P\left(A_{n}\right)\downarrow P\left(A\right)$ (上连续).

## 随机变量与分布函数

**定义 1.2.1** (随机变量)

设 $X$ 是 $\left(\Omega,\mathcal F,P\right)$ 上的实值函数, 若对每个博雷尔集 $B\subset\mathbb R$ 有 $X^{-1}\left(B\right)\in\mathcal F$, 则称 $X$ 为**随机变量** (或称 $\mathcal F$-可测).

**定义 1.2.2** (分布与分布函数)

$X$ 在 $\left(\mathbb R,\mathcal R\right)$ 上诱导的概率测度 $\mu\left(A\right)=P\left(X\in A\right)$ 称为 $X$ 的**分布**; 其**分布函数**为 $F\left(x\right)=P\left(X\le x\right)$.

**定理 1.2.1** (分布函数的性质)

设 $F\left(x\right)=P\left(X\le x\right)$, 则:

(1) $F$ 非降;

(2) $\lim_{x\to\infty}F\left(x\right)=1$, $\lim_{x\to-\infty}F\left(x\right)=0$;

(3) $F$ 右连续, 即 $\lim_{y\downarrow x}F\left(y\right)=F\left(x\right)$;

(4) 若 $F\left(x-\right)=\lim_{y\uparrow x}F\left(y\right)$, 则 $F\left(x-\right)=P\left(X< x\right)$;

(5) $P\left(X=x\right)=F\left(x\right)-F\left(x-\right)$.

**定理 1.2.2** (分布函数的逆)

设 $F$ 是分布函数. 定义其逆 $F^{-1}\left(y\right)=\sup\left\{x:F\left(x\right)< y\right\}$, $y\in\left(0,1\right)$. 若 $U$ 服从 $\left(0,1\right)$ 上的均匀分布, 则 $F^{-1}\left(U\right)$ 以 $F$ 为分布函数. 该构造也是计算机生成随机变量的标准方法.

## 可测映射与可测函数

**定义 1.3.1** (可测映射)

设 $\left(\Omega,\mathcal F\right)$、$\left(S,\mathcal S\right)$ 为可测空间. 若对一切 $B\in\mathcal S$ 有 $X^{-1}\left(B\right)\in\mathcal F$, 则称 $X:\Omega\to S$ 为**可测映射**. 当 $S=\mathbb R^{d}$、$\mathcal S=\mathcal R^{d}$ 且 $d> 1$ 时, $X$ 称为**随机向量**; $d=1$ 时称为**随机变量**.

**定理 1.3.1** (可测性的生成元判据)

设 $\mathcal A$ 生成 $\mathcal S$ (即 $\mathcal S$ 是包含 $\mathcal A$ 的最小 $\sigma$-代数). 若对一切 $A\in\mathcal A$ 有 $\left\{X\in A\right\}\in\mathcal F$, 则 $X$ 可测.

**例 1.3.2** (生成元的选择)

在 $\left(\mathbb R,\mathcal R\right)$ 上, 生成元可取 $\left\{\left(-\infty,x\right]:x\in\mathbb R\right\}$ 或 $\left\{\left(-\infty,x\right):x\in\mathbb Q\right\}$; 在 $\left(\mathbb R^{d},\mathcal R^{d}\right)$ 上, 可取 $\left\{\left(a_{1},b_{1}\right)\times\cdots\times\left(a_{d},b_{d}\right):a_{i}< b_{i}\right\}$ 或开集族.

**定理 1.3.4** (复合可测)

若 $X:\left(\Omega,\mathcal F\right)\to\left(S,\mathcal S\right)$ 与 $f:\left(S,\mathcal S\right)\to\left(T,\mathcal T\right)$ 均可测, 则 $f\left(X\right)$ 是 $\left(\Omega,\mathcal F\right)\to\left(T,\mathcal T\right)$ 的可测映射. 特别地, $cX$、$X^{2}$、$\sin X$ 等均为随机变量.

**定义 1.3.3** (简单函数)

函数 $\phi:\Omega\to\mathbb R$ 称为**简单函数**, 若

$$
\phi\left(\omega\right)=\sum_{m=1}^{n}c_{m}\mathbf{1}_{A_{m}}\left(\omega\right),
$$

其中 $c_{m}\in\mathbb R$, $A_{m}\in\mathcal F$.

**定理 1.3.7** (随机变量的极限运算)

若 $X_{1},X_{2},\dots$ 是随机变量, 则 $\inf_{n}X_{n}$、$\sup_{n}X_{n}$、$\limsup_{n}X_{n}$、$\liminf_{n}X_{n}$ 都是随机变量. 故

$$
\left\{\omega:\lim_{n}X_{n}\text{ 存在}\right\}=\left\{\omega:\limsup_{n}X_{n}-\liminf_{n}X_{n}=0\right\}
$$

是可测集.

**公式 1.3.1** (由 $X$ 生成的 $\sigma$-代数)

$\sigma\left(X\right)=\left\{\left\{X\in B\right\}:B\in\mathcal S\right\}$ 是使 $X$ 可测的最小 $\sigma$-代数.

## 积分与收敛定理

**定义 1.4.1** (积分的四步定义)

设 $\mu$ 是 $\left(\Omega,\mathcal F\right)$ 上的 $\sigma$-有限测度.

(1) 简单函数 $\phi=\sum_{i}a_{i}\mathbf{1}_{A_{i}}$ ($A_{i}$ 两两不交, $\mu\left(A_{i}\right)< \infty$) 的积分为

$$
\int\phi\,\mathrm{d}\mu=\sum_{i}a_{i}\mu\left(A_{i}\right);
$$

(2) 非负有界、在有限测度集外为零的 $f$ 的积分为

$$
\int f\,\mathrm{d}\mu=\sup_{\phi\le f}\int\phi\,\mathrm{d}\mu;
$$

(3) 非负可测 $f$ 的积分为

$$
\int f\,\mathrm{d}\mu=\sup\left\{\int h\,\mathrm{d}\mu:0\le h\le f,\ h\text{ 有界且 }\mu\left(\left\{h> 0\right\}\right)< \infty\right\};
$$

(4) 一般可测 $f$ 若 $\int\left|f\right|\,\mathrm{d}\mu< \infty$ 称**可积**, 则

$$
\int f\,\mathrm{d}\mu=\int f^{+}\,\mathrm{d}\mu-\int f^{-}\,\mathrm{d}\mu,
$$

其中 $f^{+}=f\vee 0$, $f^{-}=\left(-f\right)\vee 0$.

**定理 1.4.7** (积分的基本性质)

设 $f,g$ 可积, 则:

(1) 若 $f\ge 0$ 几乎处处, 则 $\int f\,\mathrm{d}\mu\ge 0$;

(2) 对 $a\in\mathbb R$, $\int af\,\mathrm{d}\mu=a\int f\,\mathrm{d}\mu$;

(3) $\int\left(f+g\right)\,\mathrm{d}\mu=\int f\,\mathrm{d}\mu+\int g\,\mathrm{d}\mu$;

(4) 若 $g\le f$ 几乎处处, 则 $\int g\,\mathrm{d}\mu\le\int f\,\mathrm{d}\mu$.

**定理 1.5.7** (单调收敛定理)

若 $0\le f_{n}$ 且 $f_{n}\uparrow f$ 逐点, 则

$$
\int f_{n}\,\mathrm{d}\mu\uparrow\int f\,\mathrm{d}\mu.
$$

**定理 1.6.5** (法图引理)

若 $Z_{n}\ge 0$, 则

$$
E\liminf_{n}Z_{n}\le\liminf_{n}EZ_{n}.
$$

**习题 1.4.1** (积分为零的函数)

若 $f\ge 0$ 且 $\int f\,\mathrm{d}\mu=0$, 则 $f=0$ 几乎处处.

**定理 1.6.9** (换元公式)

设 $X$ 是取值于 $\left(S,\mathcal S\right)$ 的随机元, 分布为 $\mu$ (即 $\mu\left(A\right)=P\left(X\in A\right)$). 若 $f:\left(S,\mathcal S\right)\to\left(\mathbb R,\mathcal R\right)$ 可测且 $f\ge 0$ 或 $E\left|f\left(X\right)\right|< \infty$, 则

$$
Ef\left(X\right)=\int_{S}f\left(y\right)\,\mu\left(\mathrm{d}y\right).
$$

证明用四步法: 指示函数、简单函数、非负函数、一般函数.

## 乘积空间与富比尼-托内利定理

**定理 1.7.2** (富比尼定理)

若 $f\ge 0$, 则 (托内利)

$$
\begin{aligned}\int_{X}\int_{Y}f\,\mu_{2}\left(\mathrm{d}y\right)\mu_{1}\left(\mathrm{d}x\right)&=\int_{X\times Y}f\,\mathrm{d}\left(\mu_{1}\times\mu_{2}\right)\\&=\int_{Y}\int_{X}f\,\mu_{1}\left(\mathrm{d}x\right)\mu_{2}\left(\mathrm{d}y\right).
\end{aligned}
$$

若 $f$ 可积, 即 $\int\left|f\right|\,\mathrm{d}\left(\mu_{1}\times\mu_{2}\right)< \infty$, 则同样的三重等式成立 (富比尼).

## 独立性与数字特征

**定义 2.1.1** (独立事件)

事件 $A,B\in\mathcal F$ 独立指 $P\left(A\cap B\right)=P\left(A\right)P\left(B\right)$. 事件列 $A_{1},\dots,A_{n}$ 独立指对任意 $I\subset\left\{1,\dots,n\right\}$ 有

$$
P\left(\cap_{i\in I}A_{i}\right)=\prod_{i\in I}P\left(A_{i}\right).
$$

**定义 2.1.2** (独立随机变量)

随机变量 $X_{1},\dots,X_{n}$ 独立指对一切博雷尔集 $B_{1},\dots,B_{n}$ 有

$$
P\left(X_{1}\in B_{1},\dots,X_{n}\in B_{n}\right)=\prod_{i=1}^{n}P\left(X_{i}\in B_{i}\right).
$$

**定理 2.1.1** (独立与 $\sigma$-代数)

(1) 若 $X,Y$ 独立, 则 $\sigma\left(X\right)$ 与 $\sigma\left(Y\right)$ 独立;

(2) 若 $\mathcal A_{1},\dots,\mathcal A_{n}$ 独立, 则 $\sigma\left(\mathcal A_{1}\right),\dots,\sigma\left(\mathcal A_{n}\right)$ 独立. 故验证随机变量独立可只对生成元进行.

**定理 2.1.16** (密度与独立)

设 $X_{1},\dots,X_{n}$ 有联合密度 $f$. 若 $f$ 可写成 $f\left(x_{1},\dots,x_{n}\right)=g_{1}\left(x_{1}\right)\cdots g_{n}\left(x_{n}\right)$ ($g_{i}\ge 0$ 可测), 则 $X_{1},\dots,X_{n}$ 独立; 反之, 若 $X_{1},\dots,X_{n}$ 独立且各有密度, 则联合密度为边缘密度之积.

**定理 2.1.13** (独立变量的乘积期望)

若 $X_{1},\dots,X_{n}$ 独立且 (a) 各 $X_{i}\ge 0$, 或 (b) 各 $E\left|X_{i}\right|< \infty$, 则

$$
E\left(\prod_{i=1}^{n}X_{i}\right)=\prod_{i=1}^{n}EX_{i}.
$$

**定义 2.1.3** (不相关)

若 $EX^{2},EY^{2}< \infty$ 且 $EXY=EX\cdot EY$, 称 $X,Y$ **不相关**. 独立蕴含不相关, 但不相关不蕴含独立.

**定理 2.2.1** (不相关变量的方差可加)

若 $X_{1},\dots,X_{n}$ 平方可积且两两不相关, 则

$$
\mathrm{var}\left(X_{1}+\dots+X_{n}\right)=\mathrm{var}\left(X_{1}\right)+\dots+\mathrm{var}\left(X_{n}\right).
$$

对 $c\in\mathbb R$ 有 $\mathrm{var}\left(cY\right)=c^{2}\mathrm{var}\left(Y\right)$.

**例 1.6.13** (泊松分布)

$Z$ 服从参数为 $\lambda$ 的**泊松分布**, 记 $Z\sim\mathrm{Possion}\left(\lambda\right)$, 指 $P\left(Z=k\right)=e^{-\lambda}\lambda^{k}/k!$, $k=0,1,2,\dots$.

**习题 2.1.10** (卷积公式)

若 $X,Y$ 独立且取整数值, 则

$$
P\left(X+Y=n\right)=\sum_{m}P\left(X=m\right)P\left(Y=n-m\right).
$$

**公式** (尾部求和)

若 $X\ge 0$ 取整数值, 则

$$
X=\sum_{k\ge 1}\mathbf{1}_{\left\{X\ge k\right\}},
$$

从而由单调收敛

$$
EX=\sum_{n\ge 1}P\left(X\ge n\right).
$$

**引理 2.2.13** (矩的尾部公式)

若 $Y\ge 0$ 且 $p> 0$, 则

$$
E\left(Y^{p}\right)=\int_{0}^{\infty}py^{p-1}P\left(Y> y\right)\,\mathrm{d}y.
$$

它是"对尾部 $P\left(Y> y\right)$ 逐层积分"思想的体现.

## 不等式

**定理 1.6.4** (切比雪夫不等式)

若 $\phi:\mathbb R\to\mathbb R$ 非负、非降, $\phi\left(a\right)> 0$, 则

$$
P\left(X\ge a\right)\le E\phi\left(X\right)/\phi\left(a\right).
$$

取 $\phi\left(x\right)=x^{2}$ 得 $P\left(\left|X-EX\right|\ge a\right)\le\mathrm{var}\left(X\right)/a^{2}$; 取 $\phi\left(y\right)=y$ 得马尔可夫不等式 $P\left(Y> a\right)\le EY/a$.

**引理 2.2.2** (L$^{p}$ 收敛蕴含依概率收敛)

若 $p> 0$ 且 $E\left|Z_{n}\right|^{p}\to 0$, 则 $Z_{n}\to 0$ 依概率. 它是切比雪夫不等式取 $\phi\left(x\right)=x^{p}$ 的直接推论.

## 收敛性与大数定律

**定义 2.3.1** (依概率收敛)

$X_{n}\to X$ 依概率指对任意 $\epsilon> 0$,

$$
P\left(\left|X_{n}-X\right|> \epsilon\right)\to 0.
$$

**定义 3.2.1** (依分布收敛)

$X_{n}\Rightarrow X_{\infty}$ (依分布收敛) 指分布函数 $F_{n}\left(x\right)\to F_{\infty}\left(x\right)$ 在 $F_{\infty}$ 的一切连续点上成立.

**定理 2.2.3** (L$^{2}$ 弱大数定律)

若 $X_{1},X_{2},\dots$ 两两不相关, $EX_{i}=\mu$, $\mathrm{var}\left(X_{i}\right)\le C< \infty$, $S_{n}=X_{1}+\dots+X_{n}$, 则当 $n\to\infty$ 时 $S_{n}/n\to\mu$ 在 $L^{2}$ 中且依概率.

**定理 3.2.8** (斯科罗霍德表示)

若 $X_{n}\Rightarrow X_{\infty}$, 则存在同一概率空间上的随机变量 $Y_{n}=_{d}X_{n}$ 使 $Y_{n}\to Y_{\infty}=_{d}X_{\infty}$ 几乎处处.

**性质** (函数 $g\left(t\right)=t/\left(1+t\right)$)

对 $t\ge 0$, $g$ 满足: $g\left(t\right)=0\iff t=0$; $g$ 严格递增, $g\le 1$; $g$ 次可加: $g\left(a+b\right)\le g\left(a\right)+g\left(b\right)$.

## 博雷尔-坎泰利引理与几乎必然收敛

**记号** ($A_{n}\ \text{i.o.}$)

$A_{n}\ \text{i.o.}$ (无穷多次发生) 指

$$
\limsup_{n}A_{n}=\cap_{n}\cup_{m\ge n}A_{m}.
$$

**定理 2.3.1** (博雷尔-坎泰利引理)

若 $\sum_{n=1}^{\infty}P\left(A_{n}\right)< \infty$, 则 $P\left(A_{n}\ \text{i.o.}\right)=0$. (不需独立性; 由 $EN=\sum P\left(A_{k}\right)< \infty$ 得 $N=\sum\mathbf{1}_{A_{k}}< \infty$ 几乎处处)

**定理 2.3.7** (第二博雷尔-坎泰利引理)

若 $A_{n}$ 独立且 $\sum_{n}P\left(A_{n}\right)=\infty$, 则 $P\left(A_{n}\ \text{i.o.}\right)=1$. (用 $1-x\le e^{-x}$ 估计 $\prod\left(1-P\left(A_{n}\right)\right)$.)

## 特征函数

**定义 3.3.1** (特征函数)

随机变量 $X$ 的特征函数为

$$
\begin{aligned}\phi_{X}\left(t\right)&=Ee^{itX}\\&=\int e^{itx}\,\mu\left(\mathrm{d}x\right),
\end{aligned}
$$

其中 $\mu$ 为 $X$ 的分布.

**定理 3.3.1** (特征函数的性质)

设 $\phi$ 为随机变量 $X$ 的特征函数, 则:

(1) $\phi\left(0\right)=1$;

(2) $\phi\left(-t\right)=\overline{\phi\left(t\right)}$;

(3) $\left|\phi\left(t\right)\right|\le 1$;

(4) $\left|\phi\left(t+h\right)-\phi\left(t\right)\right|\le E\left|e^{ihX}-1\right|$, 故 $\phi$ 在 $\mathbb R$ 上一致连续;

(5) $Ee^{it\left(aX+b\right)}=e^{itb}\phi\left(at\right)$.

**定理 3.3.2** (独立和的特征函数)

若 $X_{1},X_{2}$ 独立且特征函数为 $\phi_{1},\phi_{2}$, 则 $X_{1}+X_{2}$ 的特征函数为 $\phi_{1}\left(t\right)\phi_{2}\left(t\right)$.
