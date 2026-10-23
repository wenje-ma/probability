# Probability Theory

## Probability Spaces and Algebras

**Definition 1.1.1** ($\sigma$-Algebra)

Let $\Omega$ be nonempty. $\mathcal F\subset\mathcal P\left(\Omega\right)$ is called a **$\sigma$-algebra** on $\Omega$ if it satisfies:

(1) $\Omega\in\mathcal F$;

(2) closed under complementation: $A\in\mathcal F\Rightarrow A^{c}\in\mathcal F$;

(3) closed under countable unions:

$$
\left\{A_{i}\right\}_{i=1}^{\infty}\subset\mathcal F\Rightarrow\bigcup_{i=1}^{\infty}A_{i}\in\mathcal F.
$$

Since $\cap_{i}A_{i}=\left(\cup_{i}A_{i}^{c}\right)^{c}$, a $\sigma$-algebra is also closed under countable intersections. Here "countable" means finite or countably infinite.

**Definition 1.1.2** (Algebra)

Let $\Omega$ be nonempty and $\mathcal F\subset\mathcal P\left(\Omega\right)$. $\mathcal F$ is called an **algebra** on $\Omega$ if it satisfies:

(1) $\Omega\in\mathcal F$;

(2) closed under complementation: $A\in\mathcal F\Rightarrow A^{c}\in\mathcal F$;

(3) closed under finite unions: $A,B\in\mathcal F\Rightarrow A\cup B\in\mathcal F$.

**Definition 1.1.3** (Probability Space and Probability Measure)

A **probability space** is a triple $\left(\Omega,\mathcal F,P\right)$, where $\Omega$ is the sample space, $\mathcal F$ is the family of events (a $\sigma$-algebra), and $P:\mathcal F\to\left[0,1\right]$ is a **probability measure**, i.e. it satisfies:

(1) $P\left(\Omega\right)=1$;

(2) countable additivity: for any pairwise disjoint sequence of events $\left\{A_{i}\right\}$,

$$
P\left(\cup_{i}A_{i}\right)=\sum_{i}P\left(A_{i}\right).
$$

More generally, a nonnegative countably additive set function $\mu$ satisfying (2) and taking nonnegative values is called a **measure**.

**Theorem 1.1.1** (Properties of Probability Measures)

Let $\left(\Omega,\mathcal F,P\right)$ be a probability space. Then:

(1) $P\left(\varnothing\right)=0$;

(2) monotonicity: $A\subset B\Rightarrow P\left(A\right)\le P\left(B\right)$;

(3) if $A_{n}\uparrow A$ then $P\left(A_{n}\right)\uparrow P\left(A\right)$ (continuity from below); if $A_{n}\downarrow A$ then $P\left(A_{n}\right)\downarrow P\left(A\right)$ (continuity from above).

## Random Variables and Distribution Functions

**Definition 1.2.1** (Random Variable)

Let $X$ be a real-valued function on $\left(\Omega,\mathcal F,P\right)$. If $X^{-1}\left(B\right)\in\mathcal F$ for every Borel set $B\subset\mathbb R$, then $X$ is called a **random variable** (or $\mathcal F$-measurable).

**Definition 1.2.2** (Distribution and Distribution Function)

The probability measure $\mu\left(A\right)=P\left(X\in A\right)$ induced by $X$ on $\left(\mathbb R,\mathcal R\right)$ is called the **distribution** of $X$; its **distribution function** is $F\left(x\right)=P\left(X\le x\right)$.

**Theorem 1.2.1** (Properties of Distribution Functions)

Let $F\left(x\right)=P\left(X\le x\right)$. Then:

(1) $F$ is nondecreasing;

(2) $\lim_{x\to\infty}F\left(x\right)=1$, $\lim_{x\to-\infty}F\left(x\right)=0$;

(3) $F$ is right-continuous, i.e. $\lim_{y\downarrow x}F\left(y\right)=F\left(x\right)$;

(4) if $F\left(x-\right)=\lim_{y\uparrow x}F\left(y\right)$, then $F\left(x-\right)=P\left(X< x\right)$;

(5) $P\left(X=x\right)=F\left(x\right)-F\left(x-\right)$.

**Theorem 1.2.2** (Inverse of a Distribution Function)

Let $F$ be a distribution function. Define its inverse $F^{-1}\left(y\right)=\sup\left\{x:F\left(x\right)< y\right\}$, $y\in\left(0,1\right)$. If $U$ follows the uniform distribution on $\left(0,1\right)$, then $F^{-1}\left(U\right)$ has distribution function $F$. This construction is also the standard method for generating random variables on a computer.

## Measurable Mappings and Measurable Functions

**Definition 1.3.1** (Measurable Mapping)

Let $\left(\Omega,\mathcal F\right)$ and $\left(S,\mathcal S\right)$ be measurable spaces. If $X^{-1}\left(B\right)\in\mathcal F$ for all $B\in\mathcal S$, then $X:\Omega\to S$ is called a **measurable mapping**. When $S=\mathbb R^{d}$, $\mathcal S=\mathcal R^{d}$ and $d> 1$, $X$ is called a **random vector**; when $d=1$, it is called a **random variable**.

**Theorem 1.3.1** (Generator Criterion for Measurability)

Suppose $\mathcal A$ generates $\mathcal S$ (i.e. $\mathcal S$ is the smallest $\sigma$-algebra containing $\mathcal A$). If $\left\{X\in A\right\}\in\mathcal F$ for all $A\in\mathcal A$, then $X$ is measurable.

**Example 1.3.2** (Choice of Generators)

On $\left(\mathbb R,\mathcal R\right)$, one may take $\left\{\left(-\infty,x\right]:x\in\mathbb R\right\}$ or $\left\{\left(-\infty,x\right):x\in\mathbb Q\right\}$ as generators; on $\left(\mathbb R^{d},\mathcal R^{d}\right)$, one may take $\left\{\left(a_{1},b_{1}\right)\times\cdots\times\left(a_{d},b_{d}\right):a_{i}< b_{i}\right\}$ or the family of open sets.

**Theorem 1.3.4** (Composition of Measurable Maps)

If $X:\left(\Omega,\mathcal F\right)\to\left(S,\mathcal S\right)$ and $f:\left(S,\mathcal S\right)\to\left(T,\mathcal T\right)$ are both measurable, then $f\left(X\right)$ is a measurable mapping $\left(\Omega,\mathcal F\right)\to\left(T,\mathcal T\right)$. In particular, $cX$, $X^{2}$, $\sin X$, etc. are all random variables.

**Definition 1.3.3** (Simple Function)

A function $\phi:\Omega\to\mathbb R$ is called a **simple function** if

$$
\phi\left(\omega\right)=\sum_{m=1}^{n}c_{m}\mathbf{1}_{A_{m}}\left(\omega\right),
$$

where $c_{m}\in\mathbb R$, $A_{m}\in\mathcal F$.

**Theorem 1.3.7** (Limit Operations on Random Variables)

If $X_{1},X_{2},\dots$ are random variables, then $\inf_{n}X_{n}$, $\sup_{n}X_{n}$, $\limsup_{n}X_{n}$, $\liminf_{n}X_{n}$ are all random variables. Hence

$$
\left\{\omega:\lim_{n}X_{n}\text{ 存在}\right\}=\left\{\omega:\limsup_{n}X_{n}-\liminf_{n}X_{n}=0\right\}
$$

is a measurable set.

**Formula 1.3.1** (The $\sigma$-Algebra Generated by $X$)

$\sigma\left(X\right)=\left\{\left\{X\in B\right\}:B\in\mathcal S\right\}$ is the smallest $\sigma$-algebra with respect to which $X$ is measurable.

## Integration and Convergence Theorems

**Definition 1.4.1** (The Four-Step Definition of the Integral)

Let $\mu$ be a $\sigma$-finite measure on $\left(\Omega,\mathcal F\right)$.

(1) The integral of a simple function $\phi=\sum_{i}a_{i}\mathbf{1}_{A_{i}}$ ($A_{i}$ pairwise disjoint, $\mu\left(A_{i}\right)< \infty$) is

$$
\int\phi\,\mathrm{d}\mu=\sum_{i}a_{i}\mu\left(A_{i}\right);
$$

(2) the integral of a nonnegative bounded function $f$ vanishing outside a set of finite measure is

$$
\int f\,\mathrm{d}\mu=\sup_{\phi\le f}\int\phi\,\mathrm{d}\mu;
$$

(3) the integral of a nonnegative measurable function $f$ is

$$
\int f\,\mathrm{d}\mu=\sup\left\{\int h\,\mathrm{d}\mu:0\le h\le f,\ h\text{ 有界且 }\mu\left(\left\{h> 0\right\}\right)< \infty\right\};
$$

(4) a general measurable function $f$ is called **integrable** if $\int\left|f\right|\,\mathrm{d}\mu< \infty$, and then

$$
\int f\,\mathrm{d}\mu=\int f^{+}\,\mathrm{d}\mu-\int f^{-}\,\mathrm{d}\mu,
$$

where $f^{+}=f\vee 0$, $f^{-}=\left(-f\right)\vee 0$.

**Theorem 1.4.7** (Basic Properties of the Integral)

Let $f,g$ be integrable. Then:

(1) if $f\ge 0$ almost everywhere, then $\int f\,\mathrm{d}\mu\ge 0$;

(2) for $a\in\mathbb R$, $\int af\,\mathrm{d}\mu=a\int f\,\mathrm{d}\mu$;

(3) $\int\left(f+g\right)\,\mathrm{d}\mu=\int f\,\mathrm{d}\mu+\int g\,\mathrm{d}\mu$;

(4) if $g\le f$ almost everywhere, then $\int g\,\mathrm{d}\mu\le\int f\,\mathrm{d}\mu$.

**Theorem 1.5.7** (Monotone Convergence Theorem)

If $0\le f_{n}$ and $f_{n}\uparrow f$ pointwise, then

$$
\int f_{n}\,\mathrm{d}\mu\uparrow\int f\,\mathrm{d}\mu.
$$

**Theorem 1.6.5** (Fatou's Lemma)

If $Z_{n}\ge 0$, then

$$
E\liminf_{n}Z_{n}\le\liminf_{n}EZ_{n}.
$$

**Problem 1.4.1** (Functions with Zero Integral)

If $f\ge 0$ and $\int f\,\mathrm{d}\mu=0$, then $f=0$ almost everywhere.

**Theorem 1.6.9** (Change of Variables)

Let $X$ be a random element taking values in $\left(S,\mathcal S\right)$ with distribution $\mu$ (i.e. $\mu\left(A\right)=P\left(X\in A\right)$). If $f:\left(S,\mathcal S\right)\to\left(\mathbb R,\mathcal R\right)$ is measurable and $f\ge 0$ or $E\left|f\left(X\right)\right|< \infty$, then

$$
Ef\left(X\right)=\int_{S}f\left(y\right)\,\mu\left(\mathrm{d}y\right).
$$

The proof uses the four-step method: indicator functions, simple functions, nonnegative functions, general functions.

## Product Spaces and the Fubini–Tonelli Theorem

**Theorem 1.7.2** (Fubini's Theorem)

If $f\ge 0$, then (Tonelli)

$$
\begin{aligned}\int_{X}\int_{Y}f\,\mu_{2}\left(\mathrm{d}y\right)\mu_{1}\left(\mathrm{d}x\right)&=\int_{X\times Y}f\,\mathrm{d}\left(\mu_{1}\times\mu_{2}\right)\\&=\int_{Y}\int_{X}f\,\mu_{1}\left(\mathrm{d}x\right)\mu_{2}\left(\mathrm{d}y\right).
\end{aligned}
$$

If $f$ is integrable, i.e. $\int\left|f\right|\,\mathrm{d}\left(\mu_{1}\times\mu_{2}\right)< \infty$, then the same triple equality holds (Fubini).

## Independence and Numerical Characteristics

**Definition 2.1.1** (Independent Events)

Events $A,B\in\mathcal F$ are independent if $P\left(A\cap B\right)=P\left(A\right)P\left(B\right)$. A sequence of events $A_{1},\dots,A_{n}$ is independent if for every $I\subset\left\{1,\dots,n\right\}$,

$$
P\left(\cap_{i\in I}A_{i}\right)=\prod_{i\in I}P\left(A_{i}\right).
$$

**Definition 2.1.2** (Independent Random Variables)

Random variables $X_{1},\dots,X_{n}$ are independent if for all Borel sets $B_{1},\dots,B_{n}$,

$$
P\left(X_{1}\in B_{1},\dots,X_{n}\in B_{n}\right)=\prod_{i=1}^{n}P\left(X_{i}\in B_{i}\right).
$$

**Theorem 2.1.1** (Independence and $\sigma$-Algebras)

(1) If $X,Y$ are independent, then $\sigma\left(X\right)$ and $\sigma\left(Y\right)$ are independent;

(2) if $\mathcal A_{1},\dots,\mathcal A_{n}$ are independent, then $\sigma\left(\mathcal A_{1}\right),\dots,\sigma\left(\mathcal A_{n}\right)$ are independent. Hence, to verify the independence of random variables, it suffices to check the generators.

**Theorem 2.1.16** (Densities and Independence)

Let $X_{1},\dots,X_{n}$ have joint density $f$. If $f$ can be written as $f\left(x_{1},\dots,x_{n}\right)=g_{1}\left(x_{1}\right)\cdots g_{n}\left(x_{n}\right)$ ($g_{i}\ge 0$ measurable), then $X_{1},\dots,X_{n}$ are independent; conversely, if $X_{1},\dots,X_{n}$ are independent and each has a density, then the joint density is the product of the marginal densities.

**Theorem 2.1.13** (Expectation of a Product of Independent Variables)

If $X_{1},\dots,X_{n}$ are independent and (a) each $X_{i}\ge 0$, or (b) each $E\left|X_{i}\right|< \infty$, then

$$
E\left(\prod_{i=1}^{n}X_{i}\right)=\prod_{i=1}^{n}EX_{i}.
$$

**Definition 2.1.3** (Uncorrelated)

If $EX^{2},EY^{2}< \infty$ and $EXY=EX\cdot EY$, then $X,Y$ are called **uncorrelated**. Independence implies uncorrelatedness, but uncorrelatedness does not imply independence.

**Theorem 2.2.1** (Additivity of Variance for Uncorrelated Variables)

If $X_{1},\dots,X_{n}$ are square-integrable and pairwise uncorrelated, then

$$
\mathrm{var}\left(X_{1}+\dots+X_{n}\right)=\mathrm{var}\left(X_{1}\right)+\dots+\mathrm{var}\left(X_{n}\right).
$$

For $c\in\mathbb R$ we have $\mathrm{var}\left(cY\right)=c^{2}\mathrm{var}\left(Y\right)$.

**Example 1.6.13** (Poisson Distribution)

$Z$ follows the **Poisson distribution** with parameter $\lambda$, written $Z\sim\mathrm{Possion}\left(\lambda\right)$, meaning $P\left(Z=k\right)=e^{-\lambda}\lambda^{k}/k!$, $k=0,1,2,\dots$.

**Problem 2.1.10** (Convolution Formula)

If $X,Y$ are independent and integer-valued, then

$$
P\left(X+Y=n\right)=\sum_{m}P\left(X=m\right)P\left(Y=n-m\right).
$$

**Formula** (Tail Summation)

If $X\ge 0$ is integer-valued, then

$$
X=\sum_{k\ge 1}\mathbf{1}_{\left\{X\ge k\right\}},
$$

and hence, by monotone convergence,

$$
EX=\sum_{n\ge 1}P\left(X\ge n\right).
$$

**Lemma 2.2.13** (Tail Formula for Moments)

If $Y\ge 0$ and $p> 0$, then

$$
E\left(Y^{p}\right)=\int_{0}^{\infty}py^{p-1}P\left(Y> y\right)\,\mathrm{d}y.
$$

It embodies the idea of "integrating layer by layer over the tail $P\left(Y> y\right)$".

## Inequalities

**Theorem 1.6.4** (Chebyshev's Inequality)

If $\phi:\mathbb R\to\mathbb R$ is nonnegative and nondecreasing and $\phi\left(a\right)> 0$, then

$$
P\left(X\ge a\right)\le E\phi\left(X\right)/\phi\left(a\right).
$$

Taking $\phi\left(x\right)=x^{2}$ gives $P\left(\left|X-EX\right|\ge a\right)\le\mathrm{var}\left(X\right)/a^{2}$; taking $\phi\left(y\right)=y$ gives Markov's inequality $P\left(Y> a\right)\le EY/a$.

**Lemma 2.2.2** (L$^{p}$ Convergence Implies Convergence in Probability)

If $p> 0$ and $E\left|Z_{n}\right|^{p}\to 0$, then $Z_{n}\to 0$ in probability. It is a direct consequence of Chebyshev's inequality with $\phi\left(x\right)=x^{p}$.

## Convergence and Laws of Large Numbers

**Definition 2.3.1** (Convergence in Probability)

$X_{n}\to X$ in probability means that for every $\varepsilon> 0$,

$$
P\left(\left|X_{n}-X\right|> \varepsilon\right)\to 0.
$$

**Definition 3.2.1** (Convergence in Distribution)

$X_{n}\Rightarrow X_{\infty}$ (convergence in distribution) means that the distribution functions $F_{n}\left(x\right)\to F_{\infty}\left(x\right)$ at every point of continuity of $F_{\infty}$.

**Theorem 2.2.3** (Weak Law of Large Numbers in L$^{2}$)

If $X_{1},X_{2},\dots$ are pairwise uncorrelated, $EX_{i}=\mu$, $\mathrm{var}\left(X_{i}\right)\le C< \infty$, $S_{n}=X_{1}+\dots+X_{n}$, then as $n\to\infty$ we have $S_{n}/n\to\mu$ in $L^{2}$ and in probability.

**Theorem 3.2.8** (Skorokhod Representation)

If $X_{n}\Rightarrow X_{\infty}$, then there exist random variables $Y_{n}=_{d}X_{n}$ on the same probability space such that $Y_{n}\to Y_{\infty}=_{d}X_{\infty}$ almost surely.

**Property** (The Function $g\left(t\right)=t/\left(1+t\right)$)

For $t\ge 0$, $g$ satisfies: $g\left(t\right)=0\iff t=0$; $g$ is strictly increasing and $g\le 1$; $g$ is subadditive: $g\left(a+b\right)\le g\left(a\right)+g\left(b\right)$.

## The Borel–Cantelli Lemma and Almost Sure Convergence

**Notation** ($A_{n}\ \text{i.o.}$)

$A_{n}\ \text{i.o.}$ (infinitely often) means

$$
\limsup_{n}A_{n}=\cap_{n}\cup_{m\ge n}A_{m}.
$$

**Theorem 2.3.1** (Borel–Cantelli Lemma)

If $\sum_{n=1}^{\infty}P\left(A_{n}\right)< \infty$, then $P\left(A_{n}\ \text{i.o.}\right)=0$. (Independence is not needed; from $EN=\sum P\left(A_{k}\right)< \infty$ we get $N=\sum\mathbf{1}_{A_{k}}< \infty$ almost surely)

**Theorem 2.3.7** (Second Borel–Cantelli Lemma)

If the $A_{n}$ are independent and $\sum_{n}P\left(A_{n}\right)=\infty$, then $P\left(A_{n}\ \text{i.o.}\right)=1$. (Use $1-x\le e^{-x}$ to estimate $\prod\left(1-P\left(A_{n}\right)\right)$.)

## Characteristic Functions

**Definition 3.3.1** (Characteristic Function)

The characteristic function of a random variable $X$ is

$$
\begin{aligned}\phi_{X}\left(t\right)&=Ee^{itX}\\&=\int e^{itx}\,\mu\left(\mathrm{d}x\right),
\end{aligned}
$$

where $\mu$ is the distribution of $X$.

**Theorem 3.3.1** (Properties of Characteristic Functions)

Let $\phi$ be the characteristic function of a random variable $X$. Then:

(1) $\phi\left(0\right)=1$;

(2) $\phi\left(-t\right)=\overline{\phi\left(t\right)}$;

(3) $\left|\phi\left(t\right)\right|\le 1$;

(4) $\left|\phi\left(t+h\right)-\phi\left(t\right)\right|\le E\left|e^{ihX}-1\right|$, so $\phi$ is uniformly continuous on $\mathbb R$;

(5) $Ee^{it\left(aX+b\right)}=e^{itb}\phi\left(at\right)$.

**Theorem 3.3.2** (Characteristic Function of an Independent Sum)

If $X_{1},X_{2}$ are independent with characteristic functions $\phi_{1},\phi_{2}$, then the characteristic function of $X_{1}+X_{2}$ is $\phi_{1}\left(t\right)\phi_{2}\left(t\right)$.
