- [Chapter 3 Central Limit Theorems](#chapter-3-central-limit-theorems)
  - [3.2 Weak Convergence](#32-weak-convergence)
    - [3.2.1 Theory of Weak Convergence](#321-theory-of-weak-convergence)
    - [3.2.2 Tightness](#322-tightness)
  - [3.3 Characteristic Functions](#33-characteristic-functions)
    - [3.3.1 Properties](#331-properties)
    - [3.3.2 Connection to Weak Convergence](#332-connection-to-weak-convergence)
  - [3.4 Central Limit Theorems](#34-central-limit-theorems)
    - [3.4.1 i.i.d Sequences](#341-iid-sequences)
    - [3.4.2 Triangular Arrays](#342-triangular-arrays)
  - [3.7 Poisson Process](#37-poisson-process)
  - [4.1 Conditional Expectation](#41-conditional-expectation)

# Chapter 3 Central Limit Theorems

## 3.2 Weak Convergence

### 3.2.1 Theory of Weak Convergence

$\bf Def\ (Weak\ Convergence)$

1. Let $F_n,F$ be distribution functions. If $F_n(y)\to F(y)$ for every continuous point $y$ of $F$, then we say $F_n\Rightarrow F$ **converges weakly**.
2. A sequence of random variables $X_n\Rightarrow X$ if $F_{X_n}\Rightarrow F_X$.

The following example motivates this definition.

$\bf e.g.$

Let $X\sim F$ and $X_n=X\pm\frac{1}{n}$. Then $F_n(x)=P(X_n\leq x)=F(x\mp\frac{1}{n})\to F(x\mp)$. If $x$ is a continuous point of $F$, then $F_n(x)\to F(x)$. Hence $X_n\Rightarrow X$.

<br/><br/>

$\bf Thm\ 3.2.8$

If $F_n\Rightarrow F$, then there exist random variables $Y_n$ with distribution functions $F_n$ such that $Y_n\to Y$ a.s..

> $\it Proof$
>
> Omit. [Page 118]

$\bf Thm\ 3.2.9$

1. $X_n\Rightarrow X$ if and only if $Eg(X_n)\to Eg(X)$ for all bounded continuous function $g$.
2. $X_n\to X$ in probability implies $X_n\Rightarrow X$ by Theorem 3.2.4 (2).

$\bf Thm\ 3.2.10\ (Continuous\ Map\ Theorem)$

Let $g:\mathbb{R}\to\mathbb{R}$ be a Borel measurable function with $P(X\in D_g)=0$. 

1.  If $X_n\to X$ a.s., then $g(X_n)\to g(X)$ a.s..
2.  If $X_n\to X$ in probability, then $g(X_n)\to g(X)$ in probability.
3.  If $X_n\Rightarrow X$, then $g(X_n)\Rightarrow g(X)$.

> $\it Proof$
>
> (1) (2) follows from the same proof as Theorem 2.3.4.
> 
> (3) By Theorem 3.2.8, $X_n=_d Y_n$ and $X=_d Y$ with $Y_n\to Y$ a.s.. Fix a bounded continuous function $f$. Clearly $D_{f\circ g}\subset D_g$. Note that $P(Y\in D_{f\circ g})=\mu_Y(D_{f\circ g})=\mu_X(D_{f\circ g})=P(X\in D_{f\circ g})=0$. By (1), $fg(Y_n)\to fg(Y)$ a.s.. By DCT, $Efg(X_n)=Eg(Y_n)\to Efg(Y)=Efg(X)$. By Theorem 3.2.9 (1), $g(X_n)\Rightarrow g(X)$.

$\bf Thm\ 3.2.11$

TFAE:

1. $X_n\Rightarrow X$.
2. For all open sets $G$, $\liminf P(X_n\in G)\geq P(X\in G)$.
3. For all closed sets $K$, $\limsup P(X_n\in K)\leq P(X\in K)$.
4. For all Borel sets $A$ with $P(X\in\partial A)=0$, $\lim P(X_n\in A)=P(X\in A)$.

<br/><br/>

$\bf e.g.\ (Some\ Useful\ Results\ of\ Weak\ Convergence)$

1. [Exercise 3.2.12] If $X_n\to X$ in probability, then $X_n\Rightarrow X$. Conversely, if $X_n\Rightarrow c$, where $c$ is a constant, then $X_n\to c$ in probability.
2. [Exercise 3.2.13] If $X_n\Rightarrow X$ and $Y_n\Rightarrow c$, then $X_n+Y_n\Rightarrow X+c$.
3. [Exercise 3.2.14] If $X_n\Rightarrow X$ and $Y_n\Rightarrow c$, then $X_nY_n\Rightarrow cX$.

<br/><br/>


### 3.2.2 Tightness

$\bf Def\ (Tight)$

Let $F_n$ be a sequence of distribution functions. If for all $\varepsilon>0$, there is $M_\varepsilon>0$ such that $\limsup 1-F_n(M_\varepsilon)+F_n(-M_\varepsilon)\leq\varepsilon$, then we say the sequence $F_n$ is **tight**.

$\bf Rmk$

Note that

$$
1-F_n(M_\varepsilon)+F_n(-M_\varepsilon)=P(x>M_\varepsilon)+P(x\leq -M_\varepsilon)
$$


$\bf Thm\ 3.2.12\ (Helly's\ Selection\ Theorem)$

1. For any sequence $F_n$ of distribution functions, there is a subsequence $F_{n_k}$ and a right-continuous increasing function $F$ such that $F_{n_k}\Rightarrow F$.
2. Every subsequential limit $F$ is the distribution function of a random variable if and only if $F_n$ is tight.

<br/><br/>

## 3.3 Characteristic Functions

### 3.3.1 Properties

$\bf Def\ (Characteristic\ Function)$

The characteristic function of random variable $X$ is $\varphi(t)=Ee^{itX}$.

<br/><br/>

$\bf Thm\ 3.3.2$

If $X_1,X_2$ are independent, then $X_1+X_2$ has characteristic function $\varphi_1(t)\varphi_2(t)$.

<br/><br/>

$\bf Thm\ 3.3.11\ (Inversion\ Formula)$

Let $\varphi(t)$ be the characteristic function of random variable $X$ with distribution $\mu$, then if $a<b$, then

$$
\frac{1}{2\pi}\lim_{T\to\infty}\int_{-T}^T\frac{e^{-ita}-e^{-itb}}{it}\varphi(t)dt=\mu(a,b)+\frac{1}{2}\mu(\{a,b\}).
$$

$\bf Rmk$

Suppose that $x$ is a continuous point of the distribution function $F(x)$ of $X$, then

$$
F(x)= \frac{1}{2\pi}\lim_{y\to-\infty}\lim_{T\to\infty}\int_{-T}^T\frac{e^{-ity}-e^{-itx}}{it}\varphi(t)dt.
$$

If $x\in D_F$, then $F(x)=F(x-)$. So $\varphi(t)$ uniquely determines the value of $F(x)$.

<br/><br/>

$\bf Thm\ 3.3.18$

If $E|X|^n<\infty$, then $\varphi^{(n)}(t)=\int(ix)^ne^{itx}d\mu(x)$. IN particular, $EX^n=\varphi^{(n)}(0)/i^n$. Moreover we have Taylor expansion

$$
\varphi(t)=\sum_{m=0}^n\frac{E(itX)^m}{m!}+o(t^n).
$$

<br/><br/>

### 3.3.2 Connection to Weak Convergence

$\bf Lem$

Let $X$ be a random variable with characteristic function $\varphi(t)$. If $u>0$, then

$$
\mu_n\left\{x:|x|>\frac{2}{u}\right\}\leq\frac{1}{u}\int_{-u}^u(1-\varphi(t))dt
$$

> $\it Proof$
> 
> Note that $\int_{-u}^u(1-e^{itx})dt=2u-\int_{-u}^u\cos tx dt=2u-\frac{2\sin ux}{x}$. So
> $$
\begin{aligned}
\frac{1}{u}\int_{-u}^u(1-\varphi(t))dt
&=\frac{1}{u}\int_{-u}^u\int(1-e^{itx})d\mu(x)dt\\
&=\frac{1}{u}\int\int_{-u}^u(1-e^{itx})dtd\mu(x)\\
&=2\int\left(1-\frac{\sin ux}{ux}\right)d\mu(x)\\
&\geq 2\int_{|x|>\frac{2}{u}}\left(1-\frac{\sin ux}{ux}\right)d\mu(x)\\
&\geq 2\int_{|x|>\frac{2}{u}}\left(1-\frac{1}{|ux|}\right)d\mu(x)\\
&\geq 2\int_{|x|>\frac{2}{u}}\left(1-\frac{1}{2}\right)d\mu(x)\\
&=\mu\left\{x:|x|>\frac{2}{u}\right\}.
\end{aligned}$$

$\bf Thm\ 3.3.17\ (Continuity\ Theorem)$

Let $\varphi_n$ be the characteristic function of random variable $X_n$ for $1\leq n\leq \infty$.

1. If $X_n\Rightarrow X_\infty$, then $\varphi_n(t)\to\varphi_\infty(t)$ pointwise.
2. If $\varphi_n(t)\to\varphi(t)$ pointwise and $\varphi$ is continuous at zero, then $X_n\Rightarrow X$ where $X$ is a random variable with characteristic function $\varphi$. Moreover, the distribution functions $F_n$ of $X_n$ are tight.

> $\it Proof$
>
> (1) Noting that $g(x)=e^{itx}$ is a bounded continuous function, apply Theorem 3.2.9 (a).
>
> (2) Tightness: Let $\mu_n$ be the distribution of $X_n$. It suffices to show for all $\varepsilon>0$, there is small enough $u>0$ such that $\limsup_{n\to\infty}\mu_n\{x:|x|>\frac{2}{u}\}\leq\varepsilon$. This is true since $\limsup_{n\to\infty}\mu_n\{x:|x|>\frac{2}{u}\}\leq\frac{1}{u}\int_{-u}^u(1-\varphi(t))dt\to 1-\varphi(0)=0$ as $u\to 0$ by the last lemma.
>
> Now we claim that $F_n\Rightarrow F$ where $F$ is the distribution function with characteristic function $\varphi$. If not, there is a continuous point $x_0$ of $F$ such that $F_n(x_0)\not\to F(x_0)$. Since $\{F_n(x_0)\}$ is bounded, there is a convergent subsequence $F_{n_k}(x_0)$ whose limit is not $F(x_0)$. By Helly's Selection Theorem, there is a further subsequence $F_{n_{k_l}}\Rightarrow F^\ast$ where $F^\ast$ is a distribution function. Then $\varphi_{n_{k_l}}(t)\to\varphi_{F^\ast}(t)$ for all $t$. Hence $\varphi_{F^\ast}(t)=\varphi(t)$. So $F^\ast=F$ since they have the same characteristic function. So $F^\ast$ is continuous at $x_0$ and hence $F_{n_{k_l}}(x_0)\to F^\ast(x_0)=F(x_0)$. It contradicts to the fact that $F_{n_k}(x_0)$ is a convergent sequence whose limit is not $F(x_0)$.


<br/><br/>

## 3.4 Central Limit Theorems

### 3.4.1 i.i.d Sequences


$\bf Thm\ 3.4.1\ (Central\ Limit\ Theorem)$

Let $X_1,X_2,\dots$ be i.i.d. with $EX_i=\mu$ and $VarX_i=\sigma^2\in(0,\infty)$. Let $S_n=\sum_{k=1}^{n}X_{k}$, then

$$
\frac{S_n-n\mu}{\sqrt{\sigma^2n}}\Rightarrow\chi\sim N(0,1).
$$

> $\it Proof$
>
> By possibly replacing $X_i$ by $X_i-\mu$, we may assume $\mu=0$. By Theorem 3.3.18, $Ee^{itX_i}=1-\frac{\sigma^2t^2}{2}+o(t^2)$. Thus the characteristic function of ${S_n}/{\sqrt{\sigma^2n}}$ is
> $$
\varphi(t)
=Ee^{it{S_n}/{\sqrt{\sigma^2n}}}
=\left(Ee^{it{X_i}/{\sqrt{\sigma^2n}}}\right)^n
=\left(1-\frac{1}{2}\left(\frac{t}{\sqrt{\sigma^2n}}\right)^2\sigma^2+o\left(\frac{1}{n}\right)\right)^n\to e^{-t^2/2}.$$
> Now Theorem 3.3.17 completes the proof.

<br/><br/>

### 3.4.2 Triangular Arrays

$\bf Thm\ 3.6.1$

For each $n$, let $X_{n,1},\dots,X_{n,n}$ be independent random variables such that $X_{n,m}\sim B(1,p_{n,m})$. Suppose that

1. $\sum_{m=1}^{n}p_{n,m}\to\lambda\in(0,\infty)$, and
2. $\max_{1\leq m\leq n}p_{n,m}\to 0$.

Then $S_n=\sum_{m=1}^{n}X_{n,m}\Rightarrow Z\sim\mathrm{Poisson}(\lambda)$.

> $\it Proof$
>
> Then characteristic function of $S_n$ is
> $$
\varphi_n(t)=\prod_{m=1}^{n}Ee^{itX_{n,m}}=\prod_{m=1}^{n}(1-p_{n,m}+p_{n,m}e^{it}).$$
> By Lemma 3.4.3/3.4.4, we have
> $$
\left|\prod_{m=1}^{n}(1-p_{n,m}+p_{n,m}e^{it})-\prod_{m=1}^{n}e^{p_{n,m}(e^{it}-1)}\right|
\leq\sum_{m=1}^{n}\left|1-p_{n,m}+p_{n,m}e^{it}-e^{p_{n,m}(e^{it}-1)}\right|
\leq\sum_{m=1}^{n}p_{n,m}^2|e^{it}-1|^2
\leq4\max_{1\leq m\leq n}p_{n,m}\sum_{m=1}^{n}p_{n,m}\to 0.$$
> Note that $\prod_{m=1}^{n}e^{p_{n,m}(e^{it}-1)}=\exp(\sum_{m=1}^{n}p_{n,m}(e^{it}-1))\to\exp(\lambda(e^{it}-1))$. Hence $\varphi_n(t)\to\exp(\lambda(e^{it}-1))$ which is the characteristic of $Z$. Then Theorem 3.3.17 completes the proof.

$\bf Rmk$

In particular, it follows that $B(n,\frac{\lambda}{n})\Rightarrow\mathrm{Poisson}(\lambda)$.

<br/><br/>

## 3.7 Poisson Process

## 4.1 Conditional Expectation

$\bf Def/Prop\ (Conditional\ Expectation)$

Given a probability space $(\Omega,\mathcal{F}_0,P)$. Let $\mathcal{F}\subset\mathcal{F}_0$ be a sub $\sigma$-field. If $X\in\mathcal{F}_0$ is a random variable such that $E|X|<\infty$ then $E(X|\mathcal{F})$ is a random variable $Y$ such that

1. $Y\in\mathcal{F}$, and
2. $\forall A\in\mathcal{F}$, $\int_AXdP=\int_AYdP$.

Such random variables do exist. If there are two random variables that satisfy the definition, then they are equal almost surely. If we take $A=\Omega$, then we obtain the **Law of total expectation**: $E(E(X|\mathcal{F}))=EX$.

> $\it Proof$
>
> Note that $\nu(A)=\int_AXdP$ is a measure on $(\Omega,\mathcal{F})$. Then $E(X|\mathcal{F})$ is just the Radon-Nikodym derivative $\frac{d\nu}{dP}$.

<br/><br/>

$\bf Prop\ 4.1.2$

If $X_1=X_2$ on $B\in\mathcal{F}$, then $E(X_1|\mathcal{F})=E(X_2|\mathcal{F})$ a.s. on $B$.

$\bf Prop$

1. [Prop 4.1.3] If $X\in\mathcal{F}$, then $E(X|\mathcal{F})=X$.
2. [Prop 4.1.4] If $X$ is independent with $\mathcal{F}$, then $E(X|\mathcal{F})=EX$.
3. [Prop 4.1.5] Suppose that $\Omega=\bigsqcup_{\lambda\in\Lambda}\Omega_\lambda$ is a partition of $\Omega$ such that $P(\Omega_\lambda)>0$. Let $\mathcal{F}=\sigma(\{\Omega_\lambda\}_{\lambda\in\Lambda})$, then $E(X|\mathcal{F})=\frac{E(X;\Omega_i)}{P(\Omega_\lambda)}$ on $\Omega_\lambda$.
4. [Theorem 4.1.14] If $X\in\mathcal{F}$ and $E|Y|<\infty$, $E|XY|<\infty$ then $E(XY|\mathcal{F})=XE(Y|\mathcal{F})$.

> $\it Proof$
>
> [Prop 4.1.5] Let $Y$ be defined by $Y=\frac{E(X;\Omega_i)}{P(\Omega_\lambda)}$. Clearly $Y\in\mathcal{F}$. For the second condition, it suffices to check $A=\Omega_i$:
> $$\int_{\Omega_i}\frac{E(X;\Omega_i)}{P(\Omega_i)}dP=E(X;\Omega_i)=\int_{\Omega_i}XdP.$$
>
> [Theorem 4.1.14] First consider $X=1_{B}$, $B\in\mathcal{F}$.

<br/><br/>

To continue the connection with undergraduate notions, we introduce the following definition.

$\bf Def$

1. Random variable $E(X|Y):=E(X|\sigma(Y))$.
2. Number $E(X|B):=\frac{E(X;B)}{P(B)}$.
3. Random variable $P(A,\mathcal{F}):=E(1_A|\mathcal{F})$.
4. Random variable $P(A,Y):=E(1_A|Y)$.
5. Number $P(A,B):=\frac{E(1_A;B)}{P(B)}=\frac{P(AB)}{P(B)}$.

<br/><br/>

$\bf Thm\ 4.1.15$

Suppose that $EX^2<\infty$, then $E(X|\mathcal{F})$ is the variable $Y\in L^2(\mathcal{F})$ that minimize $E(X-Y)^2$.