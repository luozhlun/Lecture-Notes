
- [Chapter 1 Measure Theory](#chapter-1-measure-theory)
  - [1.1 Probability space](#11-probability-space)


# Chapter 1 Measure Theory

## 1.1 Probability space

$\bf Def\ (\sigma-field)$

$\mathcal{F}$ is called a **$\sigma$-field** if $\mathcal{F}$ is a non-empty collection of subsets of $\Omega$ s.t.

1. (closed under complement) $A\in\mathcal{F}\Rightarrow A^c\in\mathcal{F}$
2. (closed under countable union) countably many $A_i\in\mathcal{F}\Rightarrow \cup_iA_i\in\mathcal{F}$

$(\Omega,\mathcal{F})$ is called a **measurable space**. If replace 2. with *(closed under finite union)*, call it an algebra. $\sigma$-field is **algebra**. Converse is false. (EX 1.1.6)

$\bf Cor$

1. (closed under countable intersection) countably many $A_i\in\mathcal{F}\Rightarrow \cap_iA_i\in\mathcal{F}$
2. $\varnothing,\Omega\in\mathcal{F}$

<br/><br/>

$\bf Def\ (Measure)$

A **measure** on $(\Omega,\mathcal{F})$ is a function $\mu:\mathcal{F}\to[0,\infty]$ s.t.

1. (countable additivity) countably many disjoint $A_i\in\mathcal{F}\Rightarrow\mu(\cup_iA_i)=\sum_i\mu(A_i)$
2. $\mu(\varnothing)=0$

If $\mu(\Omega)=1$, then it's called a **probability measure**, usually denoted by $P$. $(\Omega,\mathcal{F},P)$ is called a probability space, where $A\in \mathcal{F}$ are called **events**. $\Omega$ is called the set of outcomes or **sample set**.

<br/><br/>

$\bf Thm 1.1.1$

Let $\mu$ be a measure on $(\Omega,\mathcal{F})$, then
1. (monotonicity) If $A\subset B$, then $\mu(A)\leq\mu(B)$
2. (subadditivity) If $A\subset\cup_iA_i$ countable, then $\mu(A)\leq\sum_i\mu(A_i)$
3. (Continuity from below) If $A_i\uparrow A$ (i.e., $A_i\subset A_2\subset\dots$ and $\cup_iA_i=A$) then $\mu(A_i)\uparrow\mu(A)$
4. (Continuity from above) $A_i\downarrow A$ (i.e., $A_i\supset A_2\supset\dots$ and $\cap_iA_i=A$) and $\mu(A_1)<\infty$ then $\mu(A_i)\downarrow\mu(A)$

> $\it Proof$
>
> 1. $B=A\sqcup (B-A)$
> 2. Consider $B_n=A_n-(A_1\cup\dots\cup A_{n-1})$, disjoint s.t. $\cup_n B_n=\cup_n A_n$
> 3. Also $B_n=A_n-(A_1\cup\dots\cup A_{n-1})$
> 4. Consider $B_n=A_1-A_n$, increasing to $A_1-A$

<br/><br/>

$\bf e.g.\ (Discrete\ probability\ space)$

$\Omega$ countable, $\mathcal{F}=2^\Omega$. Suppose we have a function $P:\Omega\to[0,\infty)$ s.t. $\forall w\in\Omega,P(w)\geq0$, we define $\mu(A):=\sum_{w\in A}P(w)$. Then $(\Omega,\mathcal{F},\mu)$ is a measure space.

<br/><br/>

$\bf e.g.\ (Continuous\ probability\ space)$

Given a **Stieltjes measure function** $F$ on $\mathbb{R}$, which means it satisfies

1. $F$ is non-decreasing.
2. $F$ is right continuous, that is, $\lim_{y\downarrow x}F(y)=F(x)$

then there's a unique measure $\mu$ on $(\mathbb{R},\mathcal{B})$ with $\mu((a,b])=F(b)-F(a)$. When $F(x)=x$, $\mu$ is called **Lebesgue measure**.