# 作业 1

> **定义 1.1.1** ($\sigma$-代数)<br>设 $\Omega$ 非空, 称 $\mathcal F\subset\mathcal P\left(\Omega\right)$ 为 $\Omega$ 上的一个 **$\sigma$-代数**, 若满足:<br>(1) $\Omega\in\mathcal F$;<br>(2) 对补运算封闭: $A\in\mathcal F\Rightarrow A^{c}\in\mathcal F$;<br>(3) 对可数并封闭: $\left\{A_{i}\right\}_{i=1}^{\infty}\subset\mathcal F\Rightarrow\bigcup_{i=1}^{\infty}A_{i}\in\mathcal F$.<br>由 $\cap_{i}A_{i}=\left(\cup_{i}A_{i}^{c}\right)^{c}$, $\sigma$-代数对可数交亦封闭. 此处"可数"指有限或可数无穷.

> **定义 1.1.2** (代数)<br>设 $\Omega$ 非空, $\mathcal F\subset\mathcal P\left(\Omega\right)$. 称 $\mathcal F$ 为 $\Omega$ 上的一个**代数**, 若满足:<br>(1) $\Omega\in\mathcal F$;<br>(2) 对补运算封闭: $A\in\mathcal F\Rightarrow A^{c}\in\mathcal F$;<br>(3) 对有限并封闭: $A,B\in\mathcal F\Rightarrow A\cup B\in\mathcal F$.

> **定义 1.1.3** (概率空间与概率测度)<br>**概率空间**是三元组 $\left(\Omega,\mathcal F,P\right)$, 其中 $\Omega$ 为样本空间, $\mathcal F$ 为事件族 ($\sigma$-代数), $P:\mathcal F\to\left[0,1\right]$ 为**概率测度**, 即满足:<br>(1) $P\left(\Omega\right)=1$;<br>(2) 可数可加性: 对两两不交的事件列 $\left\{A_{i}\right\}$, $P\left(\cup_{i}A_{i}\right)=\sum_{i}P\left(A_{i}\right)$.<br>更一般地, 满足 (2) 且取值非负的非负可数可加集函数 $\mu$ 称为**测度**.

> **定理 1.1.1** (概率测度的性质)<br>设 $\left(\Omega,\mathcal F,P\right)$ 为概率空间, 则:<br>(1) $P\left(\varnothing\right)=0$;<br>(2) 单调性: $A\subset B\Rightarrow P\left(A\right)\le P\left(B\right)$;<br>(3) 若 $A_{n}\uparrow A$ 则 $P\left(A_{n}\right)\uparrow P\left(A\right)$ (下连续), 若 $A_{n}\downarrow A$ 则 $P\left(A_{n}\right)\downarrow P\left(A\right)$ (上连续).

### 习题一

设 $\Omega=\mathbb R$, $\mathcal F$ 为所有满足"$A$ 或 $A^{c}$ 可数"的子集, $P\left(A\right)=0$ (若 $A$ 可数)、$P\left(A\right)=1$ (若 $A^{c}$ 可数). 证明 $\left(\Omega,\mathcal F,P\right)$ 是概率空间.

### 解答 习题一

先证 $\mathcal F$ 是 $\sigma$-代数 (**定义 1.1.1**). 由于 $\Omega^{c}=\varnothing$ 可数, $\Omega\in\mathcal F$. 若 $A\in\mathcal F$, 则 $A^{c}$ 满足"$A^{c}$ 或 $\left(A^{c}\right)^{c}=A$ 可数", 故 $A^{c}\in\mathcal F$. 设 $\left\{A_{i}\right\}_{i=1}^{\infty}\subset\mathcal F$ 是可数列, 分两种情况:

(1) 存在某个 $A_{j}$ 使 $A_{j}^{c}$ 可数, 则

$$
\begin{aligned}
&\quad\;\left(\cup_{i}A_{i}\right)^{c}\\
&=\cap_{i}A_{i}^{c}\\
&\subset A_{j}^{c}
\end{aligned}
$$

可数, 故 $\cup_{i}A_{i}\in\mathcal F$;

(2) 所有 $A_{i}$ 都可数, 则 $\cup_{i}A_{i}$ 可数, 故 $\cup_{i}A_{i}\in\mathcal F$.

故 $\mathcal F$ 是 $\sigma$-代数.

再证 $P$ 良定义. 若 $A$ 与 $A^{c}$ 同时可数, 则 $\mathbb R=A\cup A^{c}$ 可数, 与 $\mathbb R$ 不可数矛盾, 故"$A$ 可数"与"$A^{c}$ 可数"互斥, $P$ 的两种取值不会冲突.

最后验证 $P$ 是概率测度 (**定义 1.1.3**). 显然 $P\left(\Omega\right)=1$ (因 $\Omega^{c}=\varnothing$ 可数). 设 $\left\{A_{i}\right\}$ 两两不交, 分两种情况:

(1) 所有 $A_{i}$ 可数, 则 $\cup_{i}A_{i}$ 可数,

$$
\begin{aligned}
&\quad\;P\left(\cup_{i}A_{i}\right)\\
&=0\\
&=\sum_{i}P\left(A_{i}\right).
\end{aligned}
$$

(2) 存在某个 $A_{j}^{c}$ 可数. 因 $A_{i}\cap A_{j}=\varnothing$ 蕴含 $A_{i}\subset A_{j}^{c}$ 对 $i\ne j$, 故每个 $i\ne j$ 的 $A_{i}$ 可数, $P\left(A_{i}\right)=0$; 又

$$
\begin{aligned}
&\quad\;\left(\cup_{i}A_{i}\right)^{c}\\
&=\cap_{i}A_{i}^{c}\\
&\subset A_{j}^{c}
\end{aligned}
$$

可数, 故 $P\left(\cup_{i}A_{i}\right)=1=P\left(A_{j}\right)$. 于是

$$
\begin{aligned}
&\quad\;P\left(\cup_{i}A_{i}\right)\\
&=1\\
&=\sum_{i}P\left(A_{i}\right).
\end{aligned}
$$

综上 $\left(\Omega,\mathcal F,P\right)$ 是概率空间. $\blacksquare$

### 习题二

设 $\mathcal F_{1}\subset\mathcal F_{2}\subset\cdots$ 是一列 $\sigma$-代数, 给出一个例子说明 $\cup_{i}\mathcal F_{i}$ 不必是 $\sigma$-代数.

### 解答 习题二

取 $\Omega=\mathbb N$, 对每个 $i$ 令 $\mathcal F_{i}$ 为由前 $i$ 个单点生成的 $\sigma$-代数

$$
\sigma\left(\left\{1\right\},\left\{2\right\},\dots,\left\{i\right\}\right)
$$

(**定义 1.1.1**). 于是 $A\in\mathcal F_{i}$ 当且仅当 $A$ 有限或 $A^{c}$ 有限且所含元素均属前 $i$ 个. 从而

$$
\cup_{i}\mathcal F_{i}=\left\{A\subset\mathbb N:A\text{ 有限或 }A^{c}\text{ 有限}\right\},
$$

即"有限-余有限代数".

现取 $A_{k}=\left\{2k\right\}$, 则每个 $A_{k}\in\cup_{i}\mathcal F_{i}$ (单点有限), 但 $\cup_{k}A_{k}=\left\{2,4,6,\dots\right\}$ 与它的补集 $\left\{1,3,5,\dots\right\}$ 都既非有限也非余有限, 故 $\cup_{k}A_{k}\notin\cup_{i}\mathcal F_{i}$. 这说明 $\cup_{i}\mathcal F_{i}$ 对可数并不封闭, 不是 $\sigma$-代数 (**定义 1.1.1** (3) 不满足).

而 $\cup_{i}\mathcal F_{i}$ 确是代数 (有限并、有限交、补均保持"有限或余有限", **定义 1.1.2**), 正说明 $\sigma$-代数比代数多要求"可数并封闭"这一事实. $\blacksquare$
