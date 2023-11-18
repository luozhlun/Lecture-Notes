- [Chapter 3 Signed Measures and Differentiation](#chapter-3-signed-measures-and-differentiation)
  - [3.1 Signed Measures](#31-signed-measures)
    - [3.1.1 Hahn Decomposition](#311-hahn-decomposition)
    - [3.1.2 Jordan Decomposition](#312-jordan-decomposition)
  - [3.2 Lebesgue-Radon-Nikodym Theorem](#32-lebesgue-radon-nikodym-theorem)
    - [3.2.1 Absolute continuity](#321-absolute-continuity)
    - [3.2.2 The L-R-N Theorem](#322-the-l-r-n-theorem)
- [3.3 Complex Measures](#33-complex-measures)
- [3.4 Differentiation on Euclidean Spaces](#34-differentiation-on-euclidean-spaces)
  - [3.4.1 The Average Value Function](#341-the-average-value-function)
  - [3.4.2 The Maximal Function](#342-the-maximal-function)
  - [3.4.3 Differentiation Theorem](#343-differentiation-theorem)
  - [3.4.4 Some Applications](#344-some-applications)

# Chapter 3 Signed Measures and Differentiation

## 3.1 Signed Measures

$\bf Def\ (Signed\ Measures)$

Let $(X,\mathcal{M})$ be a measurable space. A **signed measure** on $(X,\mathcal{M})$ is a function $\nu:\mathcal{M}\to[-\infty,\infty]$ such that

1. $\nu(\varnothing)=0$.
2. $\nu$ maps to $(-\infty]$ or $[-\infty,\infty)$.
3. If $\{E_j\}\subset\mathcal{M}$ are disjoint, then $\nu(\bigcup_{j=1}^{\infty}E_j)=\sum_{j=1}^{\infty}\nu(E_j)$. Moreover, if $\sum_{j=1}^{\infty}\nu(E_j)<\infty$, then it converges absolutely.

$\bf Prop\ 3.1$

Suppose that $\nu$ is a signed measure on $(X,\mathcal{M})$.

**[Continuity from below]** If $E_1\subset E_2\subset\dots$, then $\nu(\bigcup_{j=1}^\infty E_j)=\lim_{j\to\infty}\nu(E_j)$.

**[Continuity from above]** If $E_1\supset E_2\supset\dots$ and $\nu(E_1)$ is finite, then $\nu(\bigcap_{j=1}^\infty E_j)=\lim_{j\to\infty}\nu(E_j)$.

<br/><br/>

### 3.1.1 Hahn Decomposition

$\bf Def$

A set $E\in\mathcal{M}$ is called **positive** (respectively **negative**, **null**) for $\nu$ if $\nu(F)\geq 0$ (respectively $\nu(F)\leq 0$, $\nu(F)=0$) whenever $F\in\mathcal{M}$ and $F\subset E$.

<br/><br/>

$\bf Thm/Def\ 3.3\ (Hahn\ Decomposition)$

Let $\nu$ be a signed measure, then there exist a positive set $P$ and a negative set $N$ for $\nu$ such that $X=P\sqcup N$. Moreover, if $P',N'$ is another such pair, then $P\triangle P'=N\triangle N'$ is null for $\nu$. $X=P\sqcup N$ is called a **Hahn decomposition**. (Not unique)

<br/><br/>

### 3.1.2 Jordan Decomposition

$\bf Def\ (Mutually\ Singular)$

Two signed measures $\mu$ and $\nu$ on $(X,\mathcal{M})$ are **mutually singular**, denoted by $\mu\perp\nu$, if there exist $E,F\in\mathcal{M}$ such that $X=E\sqcup F$ such that $E$ is $\mu$-null and $F$ is $\nu$-null.

<br/><br/>

$\bf Thm/Def\ 3.4\ (Jordan\ Decomposition)$

Let $\nu$ be a signed measure, then there exist unique positive measures $\nu^+$ and $\nu^-$ on $\mathcal{M}$ such that $\nu=\nu^+-\nu^-$ and $\nu^+\perp\nu^-$. The $\nu^+$, $\nu^-$ are called the **positive, negative variations** of $\nu$. And $\nu=\nu^+-\nu^-$ is called the **Jordan decomposition** of $\nu$. Then **total variation** of $\nu$ is $|\nu|=\nu^++\nu^-$. Let $L^1(\nu)=L^1(\nu^+)\cap L^1(\nu^-)$ and for $f\in L^1(\nu)$ define $\int fd\nu=\int fd\nu^+-\int fd\nu^-$.

> $\it Proof$
>
> (Existence) Let $X=P\sqcup N$ be a Hahn decomposition of $nu$. Define positive measures $\nu^+(E)=\nu(E\cap P)$ and $\nu^-(E)=-\nu(E\cap N)$.
>
> (Uniqueness) If there is another pair $\mu^+$ and $\mu^-$. Since they are mutually singular, there exist $P',N'\in\mathcal{M}$ such that $X=P'\sqcup N'$, $P'$ is $\mu^-$-null and $N'$ is $\mu^+$-null. Since $\nu=\nu^+-\nu^-$, $P'$ is positive and $N'$ is negative for $\nu$. So $X=P'\sqcup N'$ is also a Hahn decomposition of $\nu$. So $\nu(P'\bigtriangleup P)=0$. Then
> $$
\mu^+(E)=\mu^+(E\cap P')=\nu(E\cap P')=\nu(E\cap P)=\nu^+(E).$$
> and likewise $\mu^-=\nu^-$.   

<br/><br/>

$\bf Prop$

Let $\nu$ be a signed measure on $(X,\mathcal{M})$. 

1. [Exercise 3.1.2] $E$ is $\nu$-null $\Leftrightarrow$ $|\nu|(E)=0$.
2. [Exercise 3.1.2] $\nu\perp\mu$ $\Leftrightarrow$ $|\nu|\perp\mu$ $\Leftrightarrow$ $\nu^+\perp\mu$ and $\nu^-\perp\mu$.
3. $L^1(\nu)=L^1(|\nu|)$, and if $f\in L^1(\nu)$, then $|\int fd\nu|\leq\int |f|d|\nu|$.

<br/><br/>

## 3.2 Lebesgue-Radon-Nikodym Theorem

### 3.2.1 Absolute continuity

$\bf Def\ (Absolute\ Continuity)$

Suppose $\nu$ is a signed measure and $\mu$ is a positive measure on $(X,\mathcal{M})$. We say $\nu$ is **absolutely continuous** w.r.t. $\mu$, denoted by $\nu\ll\mu$, if $\nu(E)=0$ for every $E\in\mathcal{M}$ with $\mu(E)=0$.

<br/><br/>

$\bf Prop$

Suppose $\nu$ is a signed measure and $\mu$ is a positive measure on $(X,\mathcal{M})$. 

1. $\nu\ll\mu$ and $\nu\perp\mu$ $\Leftrightarrow$ $\nu\equiv0$
2. $\nu\ll\mu$ $\Leftrightarrow$ $|\nu|\ll\mu$ $\Leftrightarrow$ $\nu^+\ll\mu$ and $\nu^-\ll\mu$.

<br/><br/>

$\bf Thm\ 3.5$

Let $\nu$ be a finite signed measure, and $\mu$ is a positive measure on $(X,\mathcal{M})$. Then $\nu\ll\mu$ if and only if for every $\varepsilon>0$, there exists $\delta>0$ such that $|\nu|(E)<\varepsilon$ whenever $\mu(E)<\delta$.

$\bf Cor\ 3.6\ (Absolute\ Continuity\ of\ Integrals)$

Suppose $\mu$ is a positive measure and $f\in L^1(\mu)$. Then for every $\varepsilon>0$, there exists $\delta>0$ such that $\int_E |f|d\mu<\varepsilon$ whenever $\mu(E)<\delta$.

> $\it Proof$
>
> Apply Theorem 3.5 to the measure $\nu:E\mapsto\int_E|f|d\mu$.

<br/><br/>

$\bf Def\ (Extended\ Integrable\ Functions)$

Suppose $\mu$ is a positive measure on $(X,\mathcal{M})$. A measurable function $f:X\to\mathbb{R}$ is an **extended $\mu$-integrable function** if at most one of $\int f^+d\mu$, $\int f^-d\mu$ is infinite. In this case, $\int_E fd\mu:=\int_E f^+d\mu-\int_E f^-d\mu\in\overline{\mathbb{R}}$ is well-defined.

If $f:X\to\mathbb{R}$ is an extended $\mu$-integrable function, then $\nu:E\mapsto\int_E fd\mu$ is a signed measure and $\nu\ll\mu$. In this case, we write $d\nu=fd\mu$ and $f=\frac{d\nu}{d\mu}$.

<br/><br/>

### 3.2.2 The L-R-N Theorem

$\bf Thm\ 3.8\ (Lebesgue-Radon-Nikodym\ Theorem)$

Let $\nu$ be a $\sigma$-finite signed measure and $\mu$ a $\sigma$-finite positive measure on $(X,\mathcal{M})$. Then there exist unique $\sigma$-finite signed measures $\lambda,\rho$ on $(X,\mathcal{M})$ such that $\lambda\perp\mu$, $\rho\ll\mu$, and $\nu=\lambda+\rho$, called the **Lebesgue decomposition** of $\nu$ w.r.t. $\mu$. Moreover, there exists an extended $\mu$-integrable function $f:X\to\mathbb{R}$ such that $d\rho=fd\mu$. Such $f$ is unique up to $\mu$-a.e..

In particular, if $\nu\ll\mu$, then clearly $\nu=0+\nu$ is the unique Lebesgue decomposition. Hence there exists an extended $\mu$-integrable function $f:X\to\mathbb{R}$ such that $d\nu=fd\mu$, denoted by $\frac{d\nu}{d\mu}$ and called the **Radon-Nikodym derivative** of $\nu$ w.r.t. $\mu$.

<br/><br/>

$\bf Prop\ 3.9$

Suppose $\nu$ is a $\sigma$-finite signed measure and $\mu$, $\lambda$ are $\sigma$-finite positive measures on $(X,\mathcal{M})$ such that $\nu\ll\mu\ll\lambda$.

1. If $g\in L^1(\nu)$, then $g\frac{d\nu}{d\mu}\in L^1(\mu)$ and

$$
\int gd\nu=\int g\frac{d\nu}{d\mu}d\mu.
$$

2. $\nu\ll\lambda$ and for $\lambda$-a.e. $x\in X$,

$$
\frac{d\nu}{d\lambda}=\frac{d\nu}{d\mu}\frac{d\mu}{d\lambda}.
$$

<br/><br/>

# 3.3 Complex Measures

$\bf Def\ (Complex\ Measures)$

Let $(X,\mathcal{M})$ be a measurable space. A **complex measure** on $(X,\mathcal{M})$ is a function $\nu:\mathcal{M}\to\mathbb{C}$ such that

1. $\nu(\varnothing)=0$.
2. If $\{E_j\}\subset\mathcal{M}$ are disjoint, then $\nu(\bigcup_{j=1}^{\infty}E_j)=\sum_{j=1}^{\infty}\nu(E_j)$.

If $\nu$ is a complex measure, then $\nu_r=\mathrm{Re}(\nu)$ and $\nu_i=\mathrm{Im}(\nu)$ are finite signed measures. Define $L^1(\nu)=L^1(\nu_r)\cap L^1(\nu_i)$ and for $f\in L^1(\nu)$ define $\int fd\nu=\int fd\nu_r+i\int fd\nu_i$.

$\bf Prop/Def$

Suppose that $\mu$ is a positive measure and $f\in L^1(\mu)$. Then $\nu(E)=\int_E fd\mu$ defines a complex measure. In this case, we write $d\nu=fd\mu$. Conversely, we write $d\nu=fd\mu$ if $\nu(E)=\int_E fd\mu$ for all $E\in\mathcal{M}$.

<br/><br/>

$\bf Thm\ 3.12\ (Lebesgue-Radon-Nikodym\ Theorem\ for\ Complex\ Measures)$

Let $\nu$ be a complex measure and $\mu$ a $\sigma$-finite positive measure on $(X,\mathcal{M})$. Then there exists a unique complex measure $\lambda$ and a unique $f\in L^1(\mu)$ such that $d\nu=d\lambda+fd\mu$. Moreover, if $\nu\ll\mu$, then $f$ is denoted by $\frac{d\nu}{d\mu}$. In this case, $\frac{d\nu}{d\mu}=\frac{d\nu_r}{d\mu}+i\frac{d\nu_i}{d\mu}$.

> $\it Proof$
>
> Apply L-R-N theorem to $\nu_r$ and $\nu_i$. There are unique $\sigma$-finite signed measures $\lambda_r,\lambda_i$ and $f_r,f_i\in L^1(\mu)$ such that $\lambda_r\perp\mu$, $\lambda_i\perp\mu$, $d\nu_r=d\lambda_r+f_rd\mu_r$ and $d\nu_i=d\lambda_i+f_id\mu_i$. Let $\lambda=\lambda_r+i\lambda_i$ and $f=f_r+if_i$, then $d\nu=d\lambda+fd\mu$. And clearly $\lambda\perp\mu$. 
>
> For uniqueness, take the real and imaginary parts and use L-R-N theorem, then one can show every parts will agree with the $\lambda_r,\lambda_i,f_r,f_i$ we chose before.  

By taking real and imaginary parts of $\nu$, we can also show that Theorem 3.9 works if $\nu$ is a complex measure.

<br/><br/>

$\bf Prop/Def\ (Total\ Variation)$

If $\nu$ is a complex measure, then there is a unique positive measure, denoted by $|\nu|$ and called the **total variation** of $\nu$, such that $d|\nu|=|\frac{d\nu}{d\mu}|d\mu$ whenever $\nu\ll\mu$ and $\mu$ is positive $\sigma$-finite. In particular, $\frac{d|\nu|}{d\mu}=|\frac{d\nu}{d\mu}|$. Moreover, if $\nu$ is real-valued, then $|\nu|=\nu^++\nu^-$.

<br/><br/>

$\bf Prop\ 3.13$

Let $\nu$ be a complex measure.

1. $|\nu(E)|\leq|\nu|(E)|$ fo all $E\in\mathcal{M}$.
2. $\nu\ll|\nu|$ and $|\frac{d\nu}{d|\nu|}|=1$ $|\nu|$-a.e.
3. $L^1(\nu)=L^1(|\nu|)$, and if $f\in L^1(\nu)$, then $|\int fd\nu|\leq\int |f|d|\nu|$.

> $\it Proof$
>
> (1) Fix $\mu=|\nu_r|+|\nu_i|$, then $\mu$ is a finite positive measure with $\nu\ll\mu$. Then
> $$
\left|\int_Ed\nu\right|=\left|\int_E\frac{d\nu}{d\mu}d\mu\right|
\leq\int_E\left|\frac{d\nu}{d\mu}\right|d\mu=|\nu|(E).$$
>
> (2) Clearly $\nu\ll|\nu|\ll\mu$. Applying Theorem 3.9 (b), we have
> $$
\frac{d\nu}{d\mu}=\frac{d\nu}{d|\nu|}\frac{d|\nu|}{d\mu}
=\frac{d\nu}{d|\nu|}\left|\frac{d\nu}{d\mu}\right|.$$
> Taking absolute values, we obtain $\left|\frac{d\nu}{d\mu}\right|\left(\left|\frac{d\nu}{d|\nu|}\right|-1\right)=0$. Let $E=\{x:\frac{d\nu}{d\mu}(x)=0\}$. Note that
> $$
|\nu|(E)=\int_E\left|\frac{d\nu}{d\mu}\right|d\mu=0.$$
> So $\frac{d\nu}{d\mu}=0$ $|\nu|$-a.e. and hence $\left|\frac{d\nu}{d|\nu|}\right|=1$ $|\nu|$-a.e..
>
> (3) See Math721 HW8 Problem 2: Folland, Section 3.3, Problem 18.

$\bf Prop\ 3.14$

If $\nu_1$ and $\nu_2$ are complex measures, then $|\nu_1+\nu_2|\leq|\nu_1|+|\nu_2|$.

> $\it Proof$
>
> Consider $\mu=|\nu_1|+|\nu_2|$. Then $\nu_1,\nu_2\ll\mu$.

<br/><br/>

$\bf Prop$

Let $E\in\mathcal{M}$, then $E$ is $\nu$-null if and only if $|\nu|(E)=0$.

> $\it Proof$
> 
> Suppose that $|\nu|(E)=0$. If $F\in\mathcal{M}$ and $F\subset E$, then it follows from Folland Proposition 3.13 (a) that $|\nu(F)|\leq |\nu|(F)\leq|\nu|(E)=0$. So $\nu(F)=0$. Hence $E$ is $\nu$-null.
> 
> For the other direction, suppose that $E$ is $\nu$-null. Note that by Folland Proposition 3.13 (b), $\nu\ll|\nu|$. Let $f=\frac{d\nu}{d|\nu|}$. Then for arbitrary $A\in\mathcal{M}$,
> $$
0=\nu(A\cap E)=\int_{A\cap E}fd|\nu|=\int_A\chi_Efd|\nu|.$$
> Since $|\nu|$ is a positive measure, by Folland Proposition 2.23 (b), $\chi_Ef=0$ $|\nu|$-a.e. Note that by Folland Proposition 3.13 (b), $|f|=1$ $|\nu|$-a.e.. It follows that $|\chi_E|=\frac{|\chi_Ef|}{|f|}=0$ $|\nu|-$a.e., and hence $|\nu|(E)=0$.

<br/><br/>

# 3.4 Differentiation on Euclidean Spaces

In this section, we consider the Lebesgue measure $m$ on $\mathbb{R}^n$.

$\bf Lem$

If $f:\mathbb{R}^n\to\mathbb{C}$ is continuous, then

$$
f(x)=\lim_{r\to 0}\frac{1}{mB(x,r)}\int_{B(x,r)}f(y)dy.
$$

<br/><br/>

## 3.4.1 The Average Value Function

$\bf Def\ (Locally\ integrable)$

A measurable function $f:\mathbb{R}^n\to\mathbb{C}$ is **locally integrable** if $\int_K|f(x)|dx<\infty$ for every bounded measurable set $K\subset\mathbb{R}^n$. Let $L_\mathrm{loc}^1$ denote the set of locally integrable functions.

Given $f\in L_\mathrm{loc}^1$, $x\in\mathbb{R}^n$ and $r>0$, we define

$$
A_rf(x)=\frac{1}{mB(x,r)}\int_{B(x,r)}f(y)dy.
$$

<br/><br/>

$\bf Lem\ 3.15$

Let $\mathcal{C}$ be a collection of open balls in $\mathbb{R}^n$ and let $U=\bigcup_{B\in\mathcal{C}}B$. If $c<m(U)$, then there exist disjoint $B_1,\dots,B_k\in\mathcal{C}$ such that $\sum_{j=1}^{k}m(B_j)>\frac{c}{3^n}$.



<br/><br/>

$\bf Lem\ 3.16$

If $f\in L_\mathrm{loc}^1$, then $A_rf(x)$ as a function of $(r,x)\in\mathbb{R}^+\times\mathbb{R}^n\to \mathbb{R}$ is continuous.

<br/><br/>

## 3.4.2 The Maximal Function

$\bf Def$

Given $f\in L_\mathrm{loc}^1$, the **Hardy-Littlewood maximal function** is

$$
Hf(x)=\sup_{r>0}A_r|f|(x)=\sup_{r>0}\frac{1}{mB(x,r)}\int_{B(x,r)}|f(y)|dy
$$

Clearly, $Hf:\mathbb{R}^n\to[0,\infty]$ is measurable, since $(Hf)^{-1}(a,\infty]=\bigcup_{r>0}(A_r|f|)^{-1}(a,\infty)$.

<br/><br/>

$\bf Thm\ 3.17\ (The\ Maximal\ Theorem)$

There is a constant $c>0$ such that for all $f\in L^1$ and all $\alpha>0$,

$$
m(\{x:Hf(x)>\alpha\})\leq\frac{c}{\alpha}\int|f(x)|dx.
$$

<br/><br/>

## 3.4.3 Differentiation Theorem

$\bf Def\ (Lebesgue\ Set)$

Given $f\in L_\mathrm{loc}^1$, the **Lebesgue set** of $f$ is

$$
L_f=\left\{x:\lim_{r\to0}\frac{1}{mB(x,r)}\int_{B(x,r)}|f(y)-f(x)|dy=0\right\}.
$$

Clearly, if $x\in L_f$, then $\lim_{r\to0}A_rf(x)=f(x)$.

$\bf Def\ (Shrinking\ Nicely)$

A family $\{E_r\}_{r>0}$ of Borel sets in $\mathbb{R}^n$ shrink nicely to $x\in \mathbb{R}^n$ if

1. $E_r\subset B(x,r)$ for all $r>0$.
2. There is $\alpha>0$ such that $m(E_r)>\alpha mB(x,r)$ for all $r>0$.

<br/><br/>

$\bf Thm\ 3.18/3.20/3.21\ (The\ Lebesgue\ Differentiation\ Theorem)$

1. [Theorem 3.18] If $f\in L_\mathrm{loc}^1$, then $\lim_{r\to0}A_rf(x)=f(x)$ for a.e. $x\in \mathbb{R}^n$.
2. [Theorem 3.20] If $f\in L_\mathrm{loc}^1$, then $m(L_f^c)=0$.
3. [Theorem 3.21 The Lebesgue Differentiation Theorem]

Suppose that $f\in L_\mathrm{loc}^1$. For every $x\in L_f$ and family $\{E_r\}_{r>0}$ that shrinks nicely to $x$,

$$
\begin{aligned}
&\lim_{r\to 0}\frac{1}{m(E_r)}\int_{E_r}|f(y)-f(x)|dy=0,\\
&\lim_{r\to 0}\frac{1}{m(E_r)}\int_{E_r}f(y)dy=f(x).
\end{aligned}
$$

<br/><br/>

## 3.4.4 Some Applications

$\bf Def\ (Regular\ Measures)$

A positive Borel measure $\nu$ on $\mathbb{R}^n$ is **regular** if

1. $\nu(K)<\infty$ for every compact set $K\subset \mathbb{R}^n$.
2. $\nu(E)=\inf\{\nu(U):U\text{ open }, E\subset U\}$ for every Borel set $E$.

A signed or complex Borel measure $\nu$ on $\mathbb{R}^n$ is **regular** if $|\nu|$ is regular.

$\bf Rmk$

1. In Folland Section 7.2, we will show (1) implies (2).
2. Every regular measure is $\sigma$-finite.

<br/><br/>

$\bf Lem$

If $f\in L^+(\mathbb{R}^n)$ and $d\nu=fdm$, then $\nu$ is regular if and only if $f\in L_\mathrm{loc}^1$.

> $\it Proof$
>
> $(\Rightarrow)$ If $E$ is bounded, then $\overline E$ is compact, and hence $\int_E fdm\leq\int_{\overline E}fdm=\nu(\overline E)<\infty$.

<br/><br/>

$\bf Thm\ 3.22$

Let $\nu$ be a regular signed or complex Borel measure on $\mathbb{R}^n$ and let $d\nu=d\lambda+fdm$ be the Lebesgue decomposition w.r.t. $m$. Then for $m$-a.e. $x\in \mathbb{R}^n$, and family $\{E_r\}_{r>0}$ that shrinks nicely to $x$,

$$
\lim_{r\to 0}\frac{v(E_r)}{m(E_r)}=f(x).
$$