
- [Chapter 1 Measure Theory](#chapter-1-measure-theory)
  - [1.1 Probability space](#11-probability-space)
    - [1.1.1 Algebra](#111-algebra)
    - [1.1.2 Measures](#112-measures)
    - [1.1.3 Lebesgue-Stieltjes measures](#113-lebesgue-stieltjes-measures)
  - [1.2 Distributions](#12-distributions)
    - [1.2.1 Distributions](#121-distributions)
    - [1.2.2 Distribution functions](#122-distribution-functions)
    - [1.2.3 Density functions](#123-density-functions)
  - [1.3 Random Variables](#13-random-variables)


# Chapter 1 Measure Theory

## 1.1 Probability space

### 1.1.1 Algebra

$\bf Def\ (\sigma-algebras)$

Assume $\Omega$ is a set. $\mathcal{F}\subset\mathcal{P}(\Omega)$ is non-empty.

1. $\mathcal{F}$ is called a **algebra** on $\Omega$ if
   1. $A\in\mathcal{F}\Rightarrow A^c\in\mathcal{F}$
   2. finitely many $A_i\in\mathcal{F}\Rightarrow \bigcup_iA_i\in\mathcal{F}$
2. $\mathcal{F}$ is called a **$\sigma$-algebra** on $\Omega$ if
   1. $A\in\mathcal{F}\Rightarrow A^c\in\mathcal{F  }$
   2. countably many $A_i\in\mathcal{F}\Rightarrow \bigcup_iA_i\in\mathcal{F}$

$\bf Rmk$

Assume $\mathcal{A}\subset P(\Omega)$. The smallest $\sigma$-algebra that contains $\mathcal{A}$ is denoted by $\sigma(\mathcal{A})$.

<br/><br/>

### 1.1.2 Measures

$\bf Def\ (Measures)$

A **measure** on a $\sigma$-algebra $\mathcal{F}$ is a function $\mu:\mathcal{F}\to[0,\infty]$ s.t.

1. $\forall A\in\mathcal{A},\mu(A)\geq\mu(\varnothing)=0$
2. countably many disjoint $A_i\in\mathcal{F}\Rightarrow\mu(\bigcup_iA_i)=\sum_i\mu(A_i)$

<br/><br/>

$\bf Def\ (Probability\ spaces)$

$(\Omega,\mathcal{F},\mu)$ is called a **measure space** if $\mathcal{F}$ is a $\sigma$-algebra on $\Omega$, and $\mu$ is a measure on $(\Omega,\mathcal{F})$. If $\mu(\Omega)=1$, then $\mu$ called a **probability measure**, usually denoted by $P$. $(\Omega,\mathcal{F},P)$ is called a **probability space**, where $A\in \mathcal{F}$ are called **events**. $\Omega$ is called the set of outcomes or **sample set**.

<br/><br/>

$\bf Thm\ 1.1.1$

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

$\Omega$ countable, $\mathcal{F}=2^\Omega$. Suppose we have a function $P:\Omega\to[0,\infty)$ s.t. $\forall w\in\Omega,P(w)\geq0$, we define $\mu(A):=\sum_{w\in A}P(w)$. Then $(\Omega,\mathcal{F},\mu)$ is a measure space, called the **discrete probability space**.

<br/><br/>

### 1.1.3 Lebesgue-Stieltjes measures

$\bf Def\ (Stieltjes\ functions)$

$F$ is said to be a **Stieltjes function** on $\mathbb{R}$ if $F$ is increasing and right continuous.

<br/><br/>

$\bf Thm\ 1.1.4\ (Lebesgue-Stieltjes\ measures)$

Given any Stieltjes function $F$, there's a unique complete measure $\mu$ on $(\mathbb{R},\mathcal{B})$ with $\mu((a,b])=F(b)-F(a)$, called the **Lebesgue-Stieltjes measure**. When $F(x)=x$, $\mu$ is called **Lebesgue measure**.

> $\it Idea$
>
> See Real analysis 1.5.1.

<br/><br/>

## 1.2 Distributions

$\bf Def\ (Random\ variables)$

$(\Omega,\mathcal{F},P)$ probability space. A set function $X:\Omega\to\mathbb{R}^n$ is said to be a **random variable** if it's $\mathcal{F}$ measurable, i.e. for any Borel set $B\in\mathcal{B}^n$, $X^{-1}(B)=\{w\in\Omega:X(w)\in B\}\in\mathcal{F}$. In particular, if $n>1$, $X$ is also called **random vector**.

<br/><br/>

### 1.2.1 Distributions

$\bf Def\ (Distributions)$

A r.v. $X$ on $(\Omega,\mathcal{F},P)$ induces a probability measure $\mu$, called the **distribution** of $X$ on $(\mathbb{R},\mathcal{B})$ with $\forall B\in\mathcal{B}$

$$
\mu(B):=P(X\in A):=P(X^{-1}(A)).
$$

<br/><br/>

### 1.2.2 Distribution functions

$\bf Def\ (Distribution\ functions)$

Given a r.v. $X$, define the **distribution function** $F:\mathbb{R}\to[0,1]$ as $F(x):=P(X\leq x)$.

$\bf Thm\ 1.2.1$

Any distribution function $F$ satisfies

1. $F$ is increasing;
2. $F(\infty)=1$, $F(-\infty)=0$;
3. $\forall x\in\mathbb{R},F(x+)=F(x)$, i.e. $F$ is right continuous.
4. $\forall x,\in\mathbb{R}F(x-)=F(x)$;
5. $P(X=x)=F(x)-F(x-)$.

$\bf Thm\ 1.2.2$

If a function $F$ satisfies property 1-3 mentioned above, then $F$ is the distribution function of some random variable.

> $\it Proof$
>
> Let $\Omega=(0,1)$, $\mathcal{F}=$ the Borel sets, $P=$ Lebesgue measure. $X:\Omega\to\mathbb{R}$ is defined as $X(w)=\sup\{y:F(y)<w\}$.
>
> It suffices to show $\{w:X(w)\leq x\}=\{w:w\leq F(x)\}$. In which case, apply $F$ on both sides and note that $P$ is the Lebesgue measure, we get $P(X\leq x)=F(x)$.
>
> If $w\in LHS$, then $X(w)=\sup\{y:F(y)<w\}\leq x$, i.e. $x$ is an upper boundary of $\{y:F(y)<w\}$. Suppose $w>F(x)$, since $F$ is right continuous, $\exists\varepsilon>0$ s.t. $F(x+\varepsilon)<w$, thus $x+\varepsilon\in\sup\{y:F(y)<w\}\Rightarrow x+\varepsilon\leq x$. Contradiction. Hence $w\leq F(x)$, $w\in RHS$.
>
> If $w\in RHS$, i.e. $w\leq F(x)$. Since $F$ is increasing, $\forall z\geq x, F(z)\geq w$, $z\notin\{y:F(y)<w\}$. Hence $X(w)=\sup\{y:F(y)<w\}\leq x$, $w\in LHS$.

<br/><br/>

$\bf Def\ (Equal\ in\ distribution)$

If r.v.s $X,Y$ induce the same probability measures on $\mathbb{R}$, i.e. they have the same distribution, then we say they are **equal in distribution**, denoted by $X=_dY$

$\bf Prop$

Suppose $X,Y$ are r.v.s, then TFAE.

1. $X=_dY$
2. $P(X\leq a)=P(Y\leq a)$ for any $a\in\mathbb{R}$.
3. $X,Y$ has the same distribution functions.

> $\it Proof$
> 
> (2) and (3) are equivalent by definition of distribution function. From (1) to (2) is trivial by the definition of the probability measure induced by r.v..
>
> Getting from (3) to (1) follows from Thm 1.1.4. The distribution $F$ is increasing and right continuous, then there is a unique measure $\mu$ on $(\mathbb{R},\mathcal{B})$ s.t. $\mu(a,b]=F(b)-F(a)$. Since $\mu_X$ and $\mu_Y$ also have this property, we obtain $\mu_X=\mu=\mu_Y$.

<br/><br/>

### 1.2.3 Density functions

$\bf Def\ (Density\ functions)$

Let $F(x)$ be the distribution function of r.v. $X$. If $F(x)=\int_{-\infty}^x f(y)dy$ for some Lebesgue measurable function $f$, we say $f$ is the **density function** of $X$.

$\bf Rmk$

Intuitively, we can regard $f$ as the probability of $\{X=y\}$, or $\mu(\{y\})$.

---

## 1.3 Random Variables

The following results follow from some basic facts of measurable functions in real analysis.

$\bf Prop$

Let $f:(X,\mathcal{M})\to (Y,\mathcal{N})$ be a measurable map. Then $\{f^{-1}(A):A\in\mathcal{N}\}\subset\mathcal{M}$ is a $\sigma$-algebra on $X$, and it is the smallest $\sigma$-algebra on $X$ that makes $f$ a measurable map. It is called the **$\sigma$-algebra generated by $f$**, denoted by $\sigma(f)$.

$\bf Prop$

Let $X_1,\dots,X_n$ be r.v.s on the same probability space $(\Omega,\mathcal{F},P)$.

1. (Thm 1.3.5) If $f:(\mathbb{R}^n,\mathcal{B}^n)\to(\mathbb{R}^n,\mathcal{B}^n)$ is measurable, then $(X_1,\dots,X_n)$ is a random vector, and $f(X_1,\dots,X_n)$ is a random vector.
2. (Thm 1.3.7) Then $\inf_n X_n,\sup_n X_n,\liminf_n X_n,\limsup_n X_n$ are also r.v.s.

$\bf Def$

