
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


# Chapter 2 Laws of Large Numbers

## 2.1 Independence

### 2.2.1 Definition

Fix a probability space $(\Omega,\mathcal{F},P)$

$\bf Def\ (Independence)$

1. **Events** $A_1,\dots,A_n$ are independent if $\forall I\subset\{1,2,\dots,n\}$, $P(\bigcap_{i\in I}A_i)=\prod_{i\in I}P(A_i)$.
2. **R.v.s** $X_1,\dots,X_n$ are independent if $\forall B_i\in\mathcal{B}$, $P(\bigcap_{i=1}^n\{X_i\in B_i\})=\prod_{i=1}^nP(X_i\in B_i)$.
3. **$\sigma$-fields** $\mathcal{F_1},\dots,\mathcal{F_n}$ are independent if $\forall A_i\in\mathcal{F_i}$, $P(\bigcap_{i=1}^nA_i)=\prod_{i=1}^nP(A_i)$.

$\bf Thm\ 2.1$

1. If $X_1,\dots,X_n$ are independent r.v.s, then $\sigma(X_1),\dots,\sigma(X_n)$ are independent $\sigma$-fields.
2. If $\mathcal{F_1},\dots,\mathcal{F_n}$ are independent $\sigma$-fields, then $\forall X_i\in\mathcal{F_i}$, $X_1,\dots,X_n$ are independent r.v.s.

Hence $X_1,\dots,X_n$ are independent r.v.s if and only if $\sigma(X_1),\dots,\sigma(X_n)$ are independent $\sigma$-fields.

$\bf Thm\ 2.2$

1. If $A_1,\dots,A_n$ are independent events, then so are $A_1^c,\dots,A_n$.
2. $A_1,\dots,A_n$ are independent events if and only if $1_{A_1},\dots,1_{A_n}$ are independent r.v.s.

> $\it Proof$
>
> For (2), note that $\sigma(1_{A_i})=\{\varnothing,A_i,A_i^c,\Omega\}$ and use Thm 2.1.

<br/><br/>

### 2.2.2 Independence of random variables

$\bf Thm\ (Key\ result)$

Let $X_1,\dots,X_n$ be random variables, then TFAE

1. $X_1,\dots,X_n$ are **independent**. That is, for all Borel sets $A_i\subset\mathbb{R}$,

$$
P(X_1\in A_1,\dots,X_n\in A_n)=\prod_{i=1}^nP(X_i\in A_i).
$$

2. (Thm 2.8) For all $x_1,\dots,x_n\in(-\infty,\infty]$, the **joint distribution function**

$$
P(X_1\leq x_1,\dots,X_n\leq x_n)=\prod_{i=1}^{n}P(X_i\leq x_i).
$$

3. (Thm 2.11) Let $\mu$ be the **distribution** of the $(X_1,\dots,X_n)$, and $\mu_i$ the distribution of $X_i$, then

$$
\mu=\mu_1\times\dots\times\mu_n.
$$

4. (Thm 2.12) Any Borel measurable function $g_i:\mathbb{R}\to\mathbb{R}$, then **expectations**

$$
E[g_1(X_1)\dots g_n(X_n)]=\prod_{i=1}^{n}E[g_i(X_i)].
$$

5. (EX 2.1) **(Continuous case)** Let $f_i$ be the density function of $X_i$. The joint density function

$$
f(x_1,\dots,x_n)=\prod_{i=1}^nf(x_i).
$$

6. (EX 2.2) **(Discrete case)**

$$
P(X_1=x_1,\dots,X_n=x_n)=\prod_{i=1}^{n}P(X_i=x_i).
$$