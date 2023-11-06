- [Chapter 3 Signed Measures and Differentiation](#chapter-3-signed-measures-and-differentiation)
  - [3.1 Signed Measures](#31-signed-measures)
    - [3.1.1 Hahn Decomposition](#311-hahn-decomposition)
    - [3.1.2 Jordan Decomposition](#312-jordan-decomposition)
  - [3.2 Lebesgue-Radon-Nikodym Theorem](#32-lebesgue-radon-nikodym-theorem)

# Chapter 3 Signed Measures and Differentiation

## 3.1 Signed Measures

$\bf Def$

Let $(X,\mathcal{M})$ be a measurable space. A **signed measure** on $(X,\mathcal{M})$ is a function $\nu:\mathcal{M}\to[-\infty,\infty]$ such \theta 

1. $\nu(\varnothing)=0$
2. $\nu$ maps to $(-\infty]$ or $[-\infty,\infty)$
3. If $\{E_j\}\subset\mathcal{M}$ are disjoint, then $\nu(\bigcup_{j=1}^{\infty}E_j)=\sum_{j=1}^{\infty}\nu(E_j)$. Moreover, if $\sum_{j=1}^{\infty}\nu(E_j)<\infty$, then it converges absolutely.

$\bf Prop\ 3.1$

Suppose $\nu$ is a signed measure on $(X,\mathcal{M})$.

**[Continuity from below]** If $E_1\subset E_2\subset\dots$, then $\nu(\bigcup_{j=1}^\infty E_j)=\lim_{j\to\infty}\nu(E_j)$.

**[Continuity from above]** If $E_1\supset E_2\supset\dots$ and $\nu(E_1)$ is finite, then $\nu(\bigcap_{j=1}^\infty E_j)=\lim_{j\to\infty}\nu(E_j)$.

<br/><br/>

### 3.1.1 Hahn Decomposition

$\bf Def$

A set $E\in\mathcal{M}$ is called **positive** (respectively **negative**, **null**) for $\nu$ if $\nu(F)\geq 0$ (respectively $\nu(F)\leq 0$, $\nu(F)=0$) whenever $F\in\mathcal{M}$ and $F\subset E$.

$\bf Thm\ 3.3\ (Hahn\ Decomposition)$

There exist a positive set $P$ and a negative set $N$ for $\nu$ such that $X=P\sqcup N$. Moreover, if $P',N'$ is another such pair, then $P\triangle P'=N\triangle N'$ is null for $\nu$. $X=P\sqcup N$ is called a Hahn decomposition. (Not unique)

<br/><br/>

### 3.1.2 Jordan Decomposition

$\bf Def$

Two signed measures $\mu$ and $\nu$ on $(X,\mathcal{M})$ are **mutually singular**, denoted by $\mu\perp\nu$, if there exist $E,F\in\mathcal{M}$ such that $X=E\sqcup F$ such that $E$ is $\mu$-null and $F$ is $\nu$-null.

$\bf Thm/Def\ 3.4\ (Jordan\ Decomposition)$

If $\nu$ is a signed measure, then there exist unique positive measures $\nu^+$ and $\nu^-$ on $\mathcal{M}$ such that $\nu=\nu^+-\nu^-$ and $\nu^+\perp\nu^-$.

The $\nu^+$, $\nu^-$ are called the **positive, negative variations** of $\nu$. And $\nu=\nu^+-\nu^-$ is called the **Jordan decomposition** of $\nu$. Then **total variation** of $\nu$ is $|\nu|=\nu^++\nu^-$. Let $L^1(\nu)=L^1(\nu^+)\cap L^1(\nu^-)$, and for $f\in L^1(\nu)$ define $\int fd\nu=\int fd\nu^+-\int fd\nu^-$. Say $\nu$ is **finite** (respectively **$\sigma$-finite**) if $|\nu|$ is finite (respectively $\sigma$-finite).

<br/><br/>

$\bf Prop$

1. $E$ is $\nu$-null $\Leftrightarrow$ $|\nu|(E)=0$.
2. $\nu\perp\mu$ $\Leftrightarrow$ $|\nu|\perp\mu$ $\Leftrightarrow$ $\nu^+\perp\mu$ and $\nu^-\perp\mu$.

<br/><br/>

## 3.2 Lebesgue-Radon-Nikodym Theorem

$\bf Def\ (absolute\ Continuity)$

Suppose $\nu$ is a signed measure and $\mu$ is a positive measure on $(X,\mathcal{M})$. We say $\nu$ is **absolutely continuous** w.r.t. $\mu$, denoted by $\nu\ll\mu$, if $\nu(E)=0$ for every $E\in\mathcal{M}$ with $\mu(E)=0$.

$\bf Prop$

1. $\nu\ll\mu$ and $\nu\perp\mu$ $\Leftrightarrow$ $\nu\equiv0$
2. $\nu\ll\mu$ $\Leftrightarrow$ $|\nu|\ll\mu$ $\Leftrightarrow$ $\nu^+\ll\mu$ and $\nu^-\ll\mu$.
