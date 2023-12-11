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
  - [3.5 Functions of Bounded Variation](#35-functions-of-bounded-variation)
    - [3.5.1 Increasing Functions](#351-increasing-functions)
    - [3.5.2 BV functions](#352-bv-functions)
    - [3.5.3 Connections to Complex Measures](#353-connections-to-complex-measures)
    - [3.5.4 Absolutely Continuous Functions](#354-absolutely-continuous-functions)
    - [3.5.5 On Bounded Intervals](#355-on-bounded-intervals)

Ref:

1. [Real Variable Function Ch.1 Set Theory](https://zhuanlan.zhihu.com/p/473263173)
2. [Real Variable Function Ch.2 Lebesgue Measure](https://zhuanlan.zhihu.com/p/487435847)
3. [Real Variable Function Ch.3 Measurable Function](https://zhuanlan.zhihu.com/p/493842948)
4. [Real Variable Function Ch.4 The Lebesgue Integration](https://zhuanlan.zhihu.com/p/513296172)
5. [Real Variable Function Ch.5 Differentiation and Integration](https://zhuanlan.zhihu.com/p/5249.68471)

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

## 3.3 Complex Measures

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

## 3.4 Differentiation on Euclidean Spaces

In this section, we consider the Lebesgue measure $m$ on $\mathbb{R}^n$.

$\bf Lem$

If $f:\mathbb{R}^n\to\mathbb{C}$ is continuous, then

$$
f(x)=\lim_{r\to 0}\frac{1}{mB(x,r)}\int_{B(x,r)}f(y)dy.
$$

<br/><br/>

### 3.4.1 The Average Value Function

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

### 3.4.2 The Maximal Function

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

### 3.4.3 Differentiation Theorem

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

### 3.4.4 Some Applications

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

$\bf Lem$

If $\mu$ is a positive Borel measure on $\mathbb{R}$ such that $\mu(-N,N)<\infty$ for every $N\geq 1$, then $\mu$ is regular.

> $\it Proof$
>
> By the converse part in Theorem 1.16, $\mu$ is the Lebesgue-Stieltjes measure [not its completion here] associated to some increasing right continuous $F$. Finally, note that by Theorem 1.18, the completion of Lebesgue-Stieltjes measures are regular. So the completion of $\mu$ is regular. But clearly we can restrict the condition to all Borel sets. Hence $\mu$ is regular.

<br/><br/>

$\bf Thm\ 3.22$

Let $\nu$ be a regular signed or complex Borel measure on $\mathbb{R}^n$ and let $d\nu=d\lambda+fdm$ be the Lebesgue decomposition w.r.t. $m$. Then for $m$-a.e. $x\in \mathbb{R}^n$, and family $\{E_r\}_{r>0}$ that shrinks nicely to $x$,

$$
\lim_{r\to 0}\frac{\nu(E_r)}{m(E_r)}=f(x).
$$

<br/><br/>

## 3.5 Functions of Bounded Variation

In this section, we consider the Lebesgue measure $m$ on $\mathbb{R}$. All "a.e." in this section will always be w.r.t. the Lebesgue measure.

$\bf Lem$

If $\nu$ is a complex measure $\nu$ s.t. $\nu(-\infty,x]=0$ for all $x\in\mathbb{R}$, then $\nu\equiv0$.

> $\it Proof$
>
> Note that $\nu=\nu_r+i\nu_i$, where $\nu_r$ is a signed Borel measure such that $\nu_r(-\infty,x]=\nu_r^+(-\infty,x]-\nu_r^-(-\infty,x]=0$ for all $x\in\mathbb{R}$. By the uniqueness in Theorem 1.16, $\nu_r^+=\nu_r^-$. Likewise, $\nu_i^+=\nu_i^-$.

<br/><br/>

### 3.5.1 Increasing Functions

$\bf Prop$

Suppose $G:\mathbb{R}\to\mathbb{R}$ is increasing right continuous. Let $\mu_G$ be the Lebesgue-Stieltjes measure associated to $G$. [Theorem 1.16] Suppose $\mu_G=\lambda+\rho$ is the Lebesgue decomposition w.r.t. $m$, then $G'$ exists a.e. and $d\rho=G'(x)dm$.

> $\it Proof$
>
> Assume $d\rho=fdm$. Note that $\mu_G$ is regular by the second lemma in 3.4.4. By Theorem 3.22, for a.e. $x$ and family $\{E_r\}_{r>0}$ that shrinks nicely to $x$,
> $$
\lim_{r\to 0}\frac{\mu_G(E_r)}{m(E_r)}=f(x).$$
> Note that
> $$
G(x+h)-G(x)=\begin{cases}
\mu_G(x,x+h]&h>0,\\\mu_G(x+h,x]&h<0.
\end{cases}$$
> and the families $\{(x-r,x]\}_{r>0}$ and $\{(x,x+r]\}_{r>0}$ shrink nicely to $x$. Hence $G'$ exists and $G'=f$ for a.e. $x$.

<br/><br/>

The result above tells us that increasing right continuous functions are differentiable a.e.. It turns out that the right continuity is unnecessary.

$\bf Thm\ 3.23$

Suppose that $F:\mathbb{R}\to\mathbb{R}$ is increasing. Let $G(x)=F(x+)$. Then

1. $D_f=\{x:f\text{ is discontinuous at }x\}$ is countable.
2. $F'$ and $G'$ exist and equal to each other a.e..

> $\it Proof$
>
> (2) Let $H=F'-G'$. It suffices to show $H'=0$ a.e. Note that $\{H\neq 0\}\subset D_f$ is countable. Fix an enumeration $\{x_j\}=\{H\neq 0\}$ and let $\mu$ be a positive Borel measure defined by $\mu=\sum_{j=1}^{\infty}H(x_j)\delta_{x_j}$ where $\delta_{x_j}$ is the Dirac mass at $x_j$. Then
> $$
\begin{aligned}
\mu(-N,N)
&=\sum_{j:x_j\in(-N,N)}H(x_j)\\
&=\sum_{j:x_j\in(-N,N)}F(x_j+)-F(x_j)\\
&\leq F(N)-F(-N)<\infty.
\end{aligned}$$
> Hence by the second lemma in 3.4.4, $\mu$ is regular. Also note that $\mu(\{x_j\}^c)=0=m(\{x_j\})$. So $\mu\perp m$. Then
> $$
\begin{aligned}
\left|\frac{H(x+h)-H(x)}{h}\right|
\leq\frac{H(x+h)+H(x)}{|h|}
\leq4\frac{\mu(x-2|h|,x+2|h|)}{m(x-2|h|,x+2|h|)}
\to 0
\end{aligned}$$
> for a.e. $x$ by Theorem 3.22.

<br/><br/>

### 3.5.2 BV functions

$\bf Def/Prop$

Given $F:\mathbb{R}\to\mathbb{C}$, the **total variation function** of $F$, $T_F:\mathbb{R}\to[0,\infty]$ is defined by

$$
T_F(x)=\sup\left\{\sum_{j=1}^{n}|F(x_j)-F(x_{j-1})|:n\in\mathbb{N},-\infty<x_0<\dots<x_n=x\right\}.
$$

We have the following properties.

1. $T_F(x)$ is increasing. Since adding a point to the partition only increases the sum.
2. If $a<b$, then

$$
T_F(b)=T_F(a)+\sup\left\{\sum_{j=1}^{n}|F(x_j)-F(x_{j-1})|:n\in\mathbb{N},a=x_0<\dots<x_n=b\right\}.
$$

If $T_F(\infty)$ is finite, we say $F$ is **of bounded variation on $\mathbb{R}$**. Let $BV$ denote the set of all such functions. One can check $BV$ is a vector space.

If $F:[a,b]\to\mathbb{C}$ and

$$
\sup\left\{\sum_{j=1}^{n}|F(x_j)-F(x_{j-1})|:n\in\mathbb{N},a=x_0<\dots<x_n=b\right\}<\infty,
$$

then we say $F$ is **of bounded variation on $[a,b]$**. Let $BV([a,b])$ denote the set of all such functions.

<br/><br/>

$\bf e.g.$

$f(x)=x^a\sin(x^{-b})$ is not BV on $[0,1]$ when $0<a\leq b$. See the following references [Page75 Problem 7 (2)](https://max.book118.com/html/2019/1128/8102005123002065.shtm) and [when-is-fx-xa-sin-x-b-with-f0-0-of-bounded-variation-on-0-1](https://math.stackexchange.com/questions/1996653/when-is-fx-xa-sinx-b-with-f0-0-of-bounded-variation-on-0-1).

<br/><br/>

$\bf Def/Thm\ 3.26\ (Jordan\ Decomposition)$

If $F\in BV$ is real valued, then $T_F+F$ and $T_F-F$ are increasing and bounded. $F=\frac{1}{2}(T_F+F)-\frac{1}{2}(T_F-F)$ is the **Jordan decomposition** of $F$, and the right hand side is the difference of the **positive variation of $F$** and the **negative variation of $F$**. Hence a real valued function $F$ is BV if and only if $F$ is the difference of two bounded increasing functions.

> $\it Proof$
>
> Fix $x<y$, $\varepsilon>0$ and $x_0<\dots<x_n=x$ such that $\sum_{j=1}^{n}|F(x_j)-F(x_{j-1})|\geq T_F(x)+\varepsilon$. Then $T_F(y)\pm F(y)\geq\sum_{j=1}^{n}|F(x_j)-F(x_{j-1})|+|F(y)-F(x)|\pm F(y)\geq T_F(x)-\varepsilon\pm F(x)$. For boundedness, note that $|T_F|\leq T_F(\infty)<\infty$. Then $|T_F\pm F|=|T_F\pm (F-F(0))\pm F(0)|\leq 2T_F(\infty)+|F(0)|$.

$\bf Cor$

Note that $F\in BV$ if and only if $\mathrm{Re}F,\mathrm{Im}F\in BV$. Suppose that $F\in BV$. Let $G(x)=F(x+)$, then $G\in BV$. Moreover, by Theorem 3.23 we have

1. $D_f=\{x:f\text{ is discontinuous at }x\}$ is countable.
2. $F'$ and $G'$ exist and equal to each other a.e..

<br/><br/>

### 3.5.3 Connections to Complex Measures

Let $NBV$ be the collection of right continuous BV functions with $F(-\infty)=0$ (N stands for normalized) . If $F\in BV$, then $G(x)=F(x+)-F(-\infty)\in NBV$ and $G'=F'$ a.e..

$\bf Lem\ 3.28$

1. If $F\in BV$, then $T_F(-\infty)=0$.
2. If $F\in BV$ is right continuous, then $T_F$ is right continuous.
3. If $F\in NBV$, then $T_F\pm F\in NBV$.

$\bf Thm\ 3.29$

1. If $\mu$ is a complex Borel measure on $\mathbb{R}$, then $F(x)=\mu(-\infty,x]\in NBV$.
2. If $F\in NBV$, then there exists a unique complex Borel measure $\mu_F$ on $\mathbb{R}$ such that $F(x)=\mu(-\infty,x]$ and $|\mu_F|=\mu_{T_F}$.

> $\it Proof$
>
> (2) Let $F_1^\pm=\frac{1}{2}(T_{\mathrm{Re}F}\pm\mathrm{Re}F)$ and $F_2^\pm=\frac{1}{2}(T_{\mathrm{Im}F}\pm\mathrm{Im}F)$. Then $F=(F_1^+-F_1^-)+i(F_2^+-F_2^-)$ where $F_j^\pm\in NBV$ by lemma 3.28. By Theorem 1.16, there are finite positive Borel measures $\mu_j^\pm$ with $\mu_j^\pm(a,b]=F_j^\pm(b)-F_j^\pm(a)$. Since $F_j^\pm\in NBV$, $F_j^\pm(-\infty)=0$. Hence $\mu_j^\pm(-\infty,x]=F_j^\pm(x)$. Let $\mu_F=(\mu_1^+-\mu_1^-)+i(\mu_2^+-\mu_2^-)$, then $\mu_F$ is a complex Borel measure on $\mathbb{R}$ with $F(x)=\mu(-\infty,x]$. Uniqueness follows from the first lemma of this section. For the last assertion, see [HW10, Problem 2: Folland, Section 3.5, Problem 28].

$\bf Prop\ 3.30$

If $F\in NBV$, then $F'\in L^1$. Moreover,

1. $\mu_F\perp m$ if and only if $F'=0$ a.e., and
2. $\mu_F\ll m$ if and only if $F(x)=\int_{-\infty}^x F'(t)dt$.

<br/><br/>

### 3.5.4 Absolutely Continuous Functions

$\bf Def\ (Absolute\ Continuity)$

A function $F:\mathbb{R}\to\mathbb{C}$ is absolutely continuous if for any $\varepsilon>0$, there exists $\delta>0$, such that for any finite disjoint intervals $(a_j,b_j)$, $\sum_{j=1}^{N}(b_j-a_j)<\delta$ implies $\sum_{j=1}^{N}|F(b_j)-F(a_j)|<\varepsilon$.

A function $F:[a,b]\to\mathbb{C}$ is absolutely continuous if the condition holds for intervals $(a_j,b_j)\subset[a,b]$. 

<br/><br/>

$\bf e.g.$

1. $AC\not\Rightarrow BV$. Consider $f(x)=\sin x$.
2. $AC\Rightarrow$ uniform continuity.

<br/><br/>

$\bf Prop\ 3.32$

If $F\in NBV$, then $F\in AC$ if and only if $\mu_F\ll m$.

> $\it Proof$
>
> $(\Leftarrow)$ If $\mu_F\ll m$, by Prop 3.30, $F'\in L^1$ and $F(x)=\int_{-\infty}^x F'(t)dt$. Using Corollary 3.6, we can directly show $F\in AC$ by definition.
>
> $(\Rightarrow)$ Suppose that $F\in NBV\cap AC$. Let $\delta$ be  in the definition of AC. Fix a Borel set $E$ with $m(E)=0$. By regularity of $m$, there is an open set $E\subset U$ with $m(U)<\delta$. By the construction of $\mu_F$ [see theorem 3.29], $\mu_F=(\mu_1^+-\mu_1^-)+i(\mu_2^+-\mu_2^-)$ where $\mu_j^\pm$ is regular [see the proof of the second lemme of section 3.4.4]. So there is an open set $E\subset V$ with $\mu_j^\pm(V)\leq\mu_j^\pm(E)+\varepsilon$. Let $W=U\cap V$. Then $|\mu_F(E)-\mu_F(W)|\leq4\varepsilon$. There is $\{(a_j,b_j)\}_{j=1}^\infty$ such that $W=\bigcup_{j=1}^{\infty}(a_j,b_j)$. Note that for any $N\geq 1$, $\sum_{j=1}^{N}(b_j-a_j)\leq m(U)<\delta$. Hence $\sum_{j=1}^{N}|F(b_j)-F(a_j)|<\varepsilon$. Let $N\to\infty$, we have $\sum_{j=1}^{\infty}|F(b_j)-F(a_j)|<\varepsilon$. Hence $|\mu_F(W)|=|\sum_{j=1}^{\infty}\mu_F(a_j,b_j)|\leq\sum_{j=1}^{\infty}|\mu_F(a_j,b_j)|\leq\sum_{j=1}^{\infty}|F(b_j)-F(a_j)|<\varepsilon$. Hence $|\mu_F(E)|\leq|\mu_F(E)-\mu_F(W)|+|\mu_F(W)|<5\varepsilon$. Since $\varepsilon$ is arbitrary, $\mu_F(E)=0$. So $\mu_F\ll m$.

<br/><br/>

Combining Prop 3.29, Prop 3.30 and 3.32, we obtain the key result in this section.

$\bf Cor\ 3.33$

1. If $f\in L^1(m)$, then the function $F(x)=\int_{-\infty}^x F'(t)dt\in NBV\cap AC$ and $F'=f$ a.e..
2. If $F\in NBV\cap AC$, then $F'\in L^1(m)$ and $F(x)=\int_{-\infty}^xF'(t)dt$.

> $\it Proof$
>
> (1) If $f\in L^1(m)$, then $\mu(E)=\int_E f(t)dt$ is a complex Borel measure. Let $F(x)=\int_{-\infty}^xf(t)dt$. Note that $\mu(-\infty,x]=F(x)$. By Theorem 3.29 (1), $F\in NBV$. Moreover, by the uniqueness in Theorem 3.29 (2), $\mu_F=\mu$. Since $\mu_F=\mu\ll m$, by Theorem 3.32 we have $F\in AC$. For the last assertion, by the first proposition in Section 3.5.1, $F'=\frac{d\mu_F}{dm}$ a.e.. Note that $d\mu_F=fdm$, so $F'=f$ a.e..
> 
> (2) If $F\in NBV\cap AC$, then by Prop 3.30, $F'\in L^1(m)$. By Theorem 3.32, $\mu_F\ll m$. Then by Prop 3.30 (2), $F(x)=\int_{-\infty}^xF'(t)dt$.

<br/><br/>

### 3.5.5 On Bounded Intervals

$\bf Lem\ 3.34$

If $F\in AC[a,b]$, then $F\in BC[a,b]$

$\bf Thm\ 3.35$

If $F\in [a,b]\to\mathbb{C}$, then TFAE.

1. $F\in AC[a,b]$
2. $F(x)-F(a)=\int_a^xf(t)dt$ for some $f\in L^1([a,b],m)$.
3. $F$ is differentiable a.e. on $[a,b]$, $F'\in L^1([a,b],m)$ and $F(x)-F(a)=\int_a^xF'(t)dt$.