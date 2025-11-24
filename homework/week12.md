# week12

> **定理 2.3.1 (博雷尔-坎泰利引理)**
> 
> 若 $\sum_{n=1}^{\infty}P\left(A_{n}\right)<\infty$, 则 $P\left(A_{n}\;\text{无穷多次}\right)=0$. (不需独立性; 由 $EN=\sum{P}\left(A_{k}\right)<\infty$ 得 $N=\sum\mathbf{1}_{A_{k}}<\infty$ 几乎处处.)

> **定理 2.3.7 (第二博雷尔-坎泰利引理)**
> 
> 若 $A_{n}$ 独立且 $\sum_{n}P\left(A_{n}\right)=\infty$, 则 $P\left(A_{n}\;\text{无穷多次}\right)=1$. (用 $1-x\le{e}^{-x}$ 估计 $\prod\left(1-P\left(A_{n}\right)\right)$.)

## 2

设 $X_{1},X_{2},\dots$ 独立. 证明 $\sup_{n}X_{n}<\infty$ 几乎处处当且仅当存在 $A$ 使 $\sum_{n}P\left(X_{n}>A\right)<\infty$.

### 解答 2

$\left(\Leftarrow\right)$ 设存在 $A$ 使 $\sum_{n}P\left(X_{n}>A\right)<\infty$. 事件 $\left\{X_{n}>A\right\}$ 满足**定理 2.3.1 (博雷尔-坎泰利引理)** 的条件, 故 $P\left(X_{n}>A\;\text{无穷多次}\right)=0$, 即几乎处处只有有限个 $X_{n}$ 超过 $A$. 因此 $\sup_{n}X_{n}\le{A}<\infty$ 几乎处处 (注: 此方向不需独立性).

$\left(\Rightarrow\right)$ 设 $\sup_{n}X_{n}<\infty$ 几乎处处. 则存在 $A$ 使 $P\left(\sup_{n}X_{n}\le{A}\right)>0$ (因 $\sup_{n}X_{n}$ 几乎处处有限, $\cup_{A}\left\{\sup\le{A}\right\}$ 覆盖几乎处处全空间). 于是

$$
\left\{X_{n}>A\;\text{无穷多次}\right\}\subset\left\{\sup_{n}X_{n}>A\right\}
$$

蕴含

$$
P\left(X_{n}>A\;\text{无穷多次}\right)\le{P}\left(\sup_{n}X_{n}>A\right)=1-P\left(\sup_{n}X_{n}\le{A}\right)<1.
$$

反设 $\sum_{n}P\left(X_{n}>A\right)=\infty$. 因 $X_{n}$ 独立, 由**定理 2.3.7 (第二博雷尔-坎泰利引理)** 得 $P\left(X_{n}>A\;\text{无穷多次}\right)=1$, 与上式矛盾. 故 $\sum_{n}P\left(X_{n}>A\right)<\infty$.

$\blacksquare$

## 2

设 $g\ge0$ 连续. 若 $X_{n}\Rightarrow{X}_{\infty}$, 证明

$$
\liminf_{n\to\infty}Eg\left(X_{n}\right)\ge{E}g\left(X_{\infty}\right).
$$

### 解答 2

由**定理 3.2.8 (斯科罗霍德表示)**, 存在同一概率空间上的随机变量 $Y_{n}=_{d}X_{n}$ 与 $Y_{\infty}=_{d}X_{\infty}$, 使 $Y_{n}\to{Y}_{\infty}$ 几乎处处. 因 $g$ 连续, $g\left(Y_{n}\right)\to{g}\left(Y_{\infty}\right)$ 几乎处处.

$g\ge0$ 且 $g\left(Y_{n}\right)\ge0$, 由**定理 1.6.5 (法图引理)**:

$$
\liminf_{n\to\infty}E\,g\left(Y_{n}\right)\ge{E}\liminf_{n\to\infty}g\left(Y_{n}\right)=E\,g\left(Y_{\infty}\right).
$$

最后一步用 $g\left(Y_{n}\right)\to{g}\left(Y_{\infty}\right)$ 几乎处处. 因 $Y_{n}=_{d}X_{n}$ 与 $Y_{\infty}=_{d}X_{\infty}$, $E\,g\left(Y_{n}\right)=E\,g\left(X_{n}\right)$, $E\,g\left(Y_{\infty}\right)=E\,g\left(X_{\infty}\right)$, 代入得

$$
\liminf_{n\to\infty}Eg\left(X_{n}\right)\ge{E}g\left(X_{\infty}\right).
$$

$\blacksquare$
