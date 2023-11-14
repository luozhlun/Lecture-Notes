- [Chapter 3 Signed Measures and Differentiation](#chapter-3-signed-measures-and-differentiation)
  - [3.1 Signed Measures](#31-signed-measures)
    - [3.1.1 Hahn Decomposition](#311-hahn-decomposition)
    - [3.1.2 Jordan Decomposition](#312-jordan-decomposition)
  - [3.2 Lebesgue-Radon-Nikodym Theorem](#32-lebesgue-radon-nikodym-theorem)
    - [3.2.1 Absolute continuity](#321-absolute-continuity)
    - [3.2.2 The L-R-N Theorem](#322-the-l-r-n-theorem)
- [3.3 Complex Measures](#33-complex-measures)
- [3.4 Differentiation on Euclidean Spaces](#34-differentiation-on-euclidean-spaces)

# Chapter 3 Signed Measures and Differentiation

## 3.1 Signed Measures

$\bf Def$

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

$\bf Def$

Two signed measures $\mu$ and $\nu$ on $(X,\mathcal{M})$ are **mutually singular**, denoted by $\mu\perp\nu$, if there exist $E,F\in\mathcal{M}$ such that $X=E\sqcup F$ such that $E$ is $\mu$-null and $F$ is $\nu$-null.

<br/><br/>

$\bf Thm/Def\ 3.4\ (Jordan\ Decomposition)$

Let $\nu$ be a signed measure, then there exist unique positive measures $\nu^+$ and $\nu^-$ on $\mathcal{M}$ such that $\nu=\nu^+-\nu^-$ and $\nu^+\perp\nu^-$. The $\nu^+$, $\nu^-$ are called the **positive, negative variations** of $\nu$. And $\nu=\nu^+-\nu^-$ is called the **Jordan decomposition** of $\nu$. Then **total variation** of $\nu$ is $|\nu|=\nu^++\nu^-$.

1. Let $L^1(\nu)=L^1(\nu^+)\cap L^1(\nu^-)$ and for $f\in L^1(\nu)$ define $\int fd\nu=\int fd\nu^+-\int fd\nu^-$.
2. We say $\nu$ is **finite** (respectively **$\sigma$-finite**) if $|\nu|$ is finite (respectively $\sigma$-finite). Clearly, $\nu$ is finite (i.e. $|\nu|(X)<\infty$) if and only if $\nu$ omits $\infty$ and $-\infty$ values.

<br/><br/>

$\bf Prop$

Let $\nu$ be a signed measure on $(X,\mathcal{M})$. 

1. $E$ is $\nu$-null $\Leftrightarrow$ $|\nu|(E)=0$.
2. $\nu\perp\mu$ $\Leftrightarrow$ $|\nu|\perp\mu$ $\Leftrightarrow$ $\nu^+\perp\mu$ and $\nu^-\perp\mu$.
3. $L^1(\nu)=L^1(|\nu|)$, and if $f\in L^1(\nu)$, then $|\int fd\nu|\leq\int |f|d|\nu|$.

<br/><br/>

## 3.2 Lebesgue-Radon-Nikodym Theorem

### 3.2.1 Absolute continuity

$\bf Def\ (Absolute\ Continuity)$

Suppose $\nu$ is a signed measure and $\mu$ is a positive measure on $(X,\mathcal{M})$. We say $\nu$ is **absolutely continuous** w.r.t. $\mu$, denoted by $\nu\ll\mu$, if $\nu(E)=0$ for every $E\in\mathcal{M}$ with $\mu(E)=0$.

<br/><br/>

$\bf Prop$

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

Suppose $\nu$ is a $\sigma$-finite signed measure and $\mu$, $\lambda$ are $\sigma$-finite signed positive measures on $(X,\mathcal{M})$ such that $\nu\ll\mu\ll\lambda$.

1. If $g\in L^1(\nu)$, then $g\frac{d\nu}{d\mu}\in L^1(\mu)$ and

$$
\int gd\nu=\int g\frac{d\nu}{d\mu}d\mu.
$$

2. $\nu\ll\lambda$ and for a.e. $x\in X$,

$$
\frac{d\nu}{d\lambda}=\frac{d\nu}{d\mu}\frac{d\mu}{d\lambda}.
$$

<br/><br/>

# 3.3 Complex Measures

$\bf Def\ (Complex\ Measures)$

A complex measure on $(X,mathcal{M})$ is a function $\nu:\mathcal{M}\to \mathbb{C}$ such that

1. $\nu(\varnothing)=0$.
2. If $\{E_j\}\subset\mathcal{M}$ are disjoint, then $\nu(\bigcup_{j=1}^{\infty}E_j)=\sum_{j=1}^{\infty}\nu(E_j)$.

Moreover, $\nu_r=\mathrm{Re}(\nu)$ and $\nu_i=\mathrm{Im}(\nu)$ are finite signed measures. Define $L^1(\nu)=L^1(\nu_r)\cap L^1(\nu_i)$ and for $f\in L^1(\nu)$ define $\int fd\nu=\int fd\nu_r+i\int fd\nu_i$.

$\bf Prop$

If $\mu$ is a positive measure and $f\in L^1(\mu)$, then $\nu(E)=\int_E fd\mu$ defines a complex measure. In this case, we write $d\nu=fd\mu$.

<br/><br/>

$\bf Thm\ 3.12\ (Lebesgue-Radon-Nikodym\ Theorem\ for\ Complex\ Measures)$

Let $\nu$ be a complex measure and $\mu$ a $\sigma$-finite positive measure on $(X,\mathcal{M})$. Then there exists a unique complex measure $\lambda$ and a unique $f\in L^1(\mu)$ such that $d\nu=d\lambda+fd\mu$. Moreover, if $\nu\ll\mu$, then $f$ is denoted by $\frac{d\nu}{d\mu}$. In particular $\frac{d\nu}{d\mu}=\frac{d\nu_r}{d\mu}+i\frac{d\nu_i}{d\mu}$.

<br/><br/>

$\bf Prop/Def\ (Total\ Variation)$

If $\nu$ is a complex measure, then there is a unique positive measure, denoted by $|\nu|$ and called the **total variation** of $\nu$, such that $d|\nu|=|\frac{d\nu}{d\mu}|d\mu$ whenever $\nu\ll\mu$ and $\mu$ is positive $\sigma$-finite. Moreover, if $\nu$ is real-valued, then $|\nu|=\nu^++\nu^-$.

<br/><br/>

$\bf Prop\ 3.13$

Let $\nu$ be a complex measure.

1. $|\nu(E)|\leq|\nu|(E)|$ fo all $E\in\mathcal{M}$.
2. $\nu\ll|\nu|$ and $|\frac{d\nu}{d|\nu|}|=1$ $|\nu|$-a.e.
3. $L^1(\nu)=L^1(|\nu|)$, and if $f\in L^1(\nu)$, then $|\int fd\nu|\leq\int |f|d|\nu|$.

$\bf Prop\ 3.14$

If $\nu_1$ and $\nu_2$ are complex measures, then $|\nu_1+\nu_2|\leq|\nu_1|+|\nu_2|$

<br/><br/>

# 3.4 Differentiation on Euclidean Spaces