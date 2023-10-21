- [Chapter 2 Laws of Large Numbers](#chapter-2-laws-of-large-numbers)
  - [2.1 Independence](#21-independence)
    - [2.1.1 Definition](#211-definition)
    - [2.1.2 Independence of Random Variables](#212-independence-of-random-variables)
  - [2.2 Weak Laws of Large Numbers](#22-weak-laws-of-large-numbers)
    - [2.2.1 $L^2$ Weak Laws](#221-l2-weak-laws)
    - [2.2.3 Truncation (without second moment)](#223-truncation-without-second-moment)
  - [2.3 Borel-Cantelli Lemmas](#23-borel-cantelli-lemmas)

# Chapter 2 Laws of Large Numbers

## 2.1 Independence

### 2.1.1 Definition

Fix a probability space $(\Omega,\mathcal{F},P)$

$\bf Def\ (Independence)$

1. **Events** $A_1,\dots,A_n$ are independent if $\forall I\subset\{1,2,\dots,n\}$, $P(\bigcap_{i\in I}A_i)=\prod_{i\in I}P(A_i)$.
2. **R.v.s** $X_1,\dots,X_n$ are independent if $\forall B_i\in\mathcal{B}$, $P(\bigcap_{i=1}^n\{X_i\in B_i\})=\prod_{i=1}^nP(X_i\in B_i)$.
3. **$\sigma$-fields** $\mathcal{F_1},\dots,\mathcal{F_n}$ are independent if $\forall A_i\in\mathcal{F_i}$, $P(\bigcap_{i=1}^nA_i)=\prod_{i=1}^nP(A_i)$.

$\bf Thm\ 2.1.1$

1. If $X_1,\dots,X_n$ are independent r.v.s, then $\sigma(X_1),\dots,\sigma(X_n)$ are independent $\sigma$-fields.
2. If $\mathcal{F_1},\dots,\mathcal{F_n}$ are independent $\sigma$-fields, then $\forall X_i\in\mathcal{F_i}$, $X_1,\dots,X_n$ are independent r.v.s.

Hence $X_1,\dots,X_n$ are independent r.v.s if and only if $\sigma(X_1),\dots,\sigma(X_n)$ are independent $\sigma$-fields.

$\bf Thm\ 2.1.2$

1. If $A_1,\dots,A_n$ are independent events, then so are $A_1^c,\dots,A_n$.
2. $A_1,\dots,A_n$ are independent events if and only if $1_{A_1},\dots,1_{A_n}$ are independent r.v.s.

> $\it Proof$
>
> For (2), note that $\sigma(1_{A_i})=\{\varnothing,A_i,A_i^c,\Omega\}$ and use Thm 2.1.

<br/><br/>

### 2.1.2 Independence of Random Variables

$\bf Thm\ (Key\ result)$

Let $X_1,\dots,X_n$ be random variables, then TFAE

1. $X_1,\dots,X_n$ are **independent**. That is, for all Borel sets $A_i\subset\mathbb{R}$,

$$
P(X_1\in A_1,\dots,X_n\in A_n)=\prod_{i=1}^nP(X_i\in A_i).
$$

2. (Thm 2.1.8) For all $x_1,\dots,x_n\in(-\infty,\infty]$, the **joint distribution function**

$$
P(X_1\leq x_1,\dots,X_n\leq x_n)=\prod_{i=1}^{n}P(X_i\leq x_i).
$$

3. (Thm 2.1.11) Let $\mu$ be the **distribution** of the $(X_1,\dots,X_n)$, and $\mu_i$ the distribution of $X_i$, then

$$
\mu=\mu_1\times\dots\times\mu_n.
$$

4. (Thm 2.1.12) Any Borel measurable function $g_i:\mathbb{R}\to\mathbb{R}$, then **expectations**

$$
E[g_1(X_1)\dots g_n(X_n)]=\prod_{i=1}^{n}E[g_i(X_i)].
$$

5. (EX 2.1.1) **(Continuous case)** Let $f_i$ be the density function of $X_i$. The joint density function

$$
f(x_1,\dots,x_n)=\prod_{i=1}^nf(x_i).
$$

6. (EX 2.1.2) **(Discrete case)**

$$
P(X_1=x_1,\dots,X_n=x_n)=\prod_{i=1}^{n}P(X_i=x_i).
$$

<br/><br/>

## 2.2 Weak Laws of Large Numbers

### 2.2.1 $L^2$ Weak Laws

$\bf Def\ (Uncorrelated)$

Let $\{X_i\}_{i\in I}$ be a family of r.v.s with $EX_i^2<\infty$. They are said to be **uncorrelated** if $\forall i\neq j, E(X_iX_j)=EX_iEX_j$. By Theorem 2.12, independence implies uncorrelatedness.

$\bf Thm\ 2.2.1$

Let $X_1,\dots,X_n$ be uncorrelated r.v.s, then $Var(\sum_{i=1}^{n}X_i)=\sum_{i=1}^{\infty}Var(X_i)$.

<br/><br/>

$\bf Thm\ 2.2.3 (L^2\ weak\ law\ of\ large\ number)$

Let $X_1,X_2,\dots$ be uncorrelated r.v.s with $EX_i=\mu$ and $VarX_i\leq C<\infty$. Then $S_n/n\to\mu$ in $L^2$.

> $\it Proof$
>
> Note that $E(S_n/n)=\mu$,
> $$
E\left[\left(\frac{S_n}{n}-\mu\right)^2\right]
=Var\left(\frac{S_n}{n}\right)=\frac{Var(S_n)}{n^2}
=\frac{\sum_{i=1}^{\infty}Var(X_i)}{n^2}
\leq\frac{C}{n}\to0.$$

<br/><br/>

### 2.2.3 Truncation (without second moment)

$\bf Lem\ 2.2.13$

If $Y\geq 0$ and $p>0$, then $E(Y^p)=\int_0^\infty py^{p-1}P(Y>y)dy$.

> $\it Proof$
>
> By Fubini's theorem
> $$
\begin{aligned}
\int_0^\infty py^{p-1}P(Y>y)dy
&=\int_0^\infty\int_\Omega py^{p-1}1_{Y>y}(w)dPdy\\
&=\int_\Omega\int_0^Y py^{p-1}dydP\\
&=\int_\Omega Y^{p}dP=EY^p
\end{aligned}$$

<br/><br/>

$\bf Thm\ 2.2.11\ (Weak\ law\ of\ large\ number\ for\ triangular\ arrays)$

$$
\begin{array}{cc}
X_{11}&&&\\
X_{21}&X_{22}&&\\
\vdots&\vdots&\ddots&\\
X_{n1}&X_{n2}&\dots&X_{nn}
\end{array}
$$

Assume each row are independent. Let $b_n>0$ with $b_n\to\infty$ and $\overline X_{n,k}=X_{n,k}1_{|X_{n,k}|\leq b_n}$. Suppose that as $n\to\infty$

1. $\sum_{k=1}^{n}P(|X_{n,k}|> b_n)\to 0$, and
2. $\dfrac{\sum_{k=1}^{n}E\overline X_{n,k}^2}{b_n}\to 0$.

Then $\dfrac{S_n-a_n}{b_n}\to 0$ in probability, where $a_n=\sum_{k=1}^{n}E\overline X_{n,k}$ and $S_n=\sum_{k=1}^{n}X_{n,k}$.

> $\it Proof$
>
> Let $\overline S_n=\sum_{k=1}^{n}\overline X_{n,k}$. Note that
> $$
P\left(\left|\frac{S_n-a_n}{b_n}\right|>\varepsilon\right)\leq P(S_n\neq\overline S_n)+P\left(\left|\frac{\overline S_n-a_n}{b_n}\right|>\varepsilon\right).$$
> Note that
> $$
P(S_n\neq\overline S_n)\leq P\left(\bigcup_{k=1}^{n}\{X_{n,k}\neq\overline X_{n,k}\}\right)\leq\sum_{k=1}^{n}P(|X_{n,k}|>b_n)\to 0,$$
> and
> $$
P\left(\left|\frac{\overline S_n-a_n}{b_n}\right|>\varepsilon\right)
\leq\frac{E(\overline S_n-a_n)^2}{\varepsilon^2b_n^2}
=\frac{Var(\overline S_n)}{\varepsilon^2b_n^2}
=\frac{\sum_{k=1}^{n} Var(\overline X_{n,k})}{\varepsilon^2b_n^2}
\leq\frac{\sum_{k=1}^{n} E(\overline X_{n,k})^2}{\varepsilon^2b_n^2}\to0.$$

<br/><br/>

$\bf Thm\ (Weak\ law\ of\ large\ number)$

Let $X_1,X_2,\dots$ be i.i.d. and $S_n=\sum_{k=1}^{n}X_{n,k}$.

1. (Thm 2.2.12) If $xP(|X_i|>x)\to 0$ as $x\to\infty$, then $S_n/n-\mu_n\to 0$ in probability, where $\mu_n=E(X_i1_{|X_i|\leq n})$.
2. (Thm 2.2.14) If $E|X_i|<\infty$, then $S_n/n\to \mu$ in probability, where $\mu=EX_i$. 

> $\it Proof$
>
> (1) Choose $X_{n,k}:=X_k$ and $b_n=n$ in Theorem 2.2.11. Clearly the first requirement is satisfied. To check the second requirement, apply Lemma 2.2.13 and DCT, then
> $$
\frac{\sum_{k=1}^{n}E\overline X_{n,k}^2}{n^2}
=\frac{E\overline X_{n,i}^2}{n}
=\frac{1}{n}\int_0^n2yP(|X_{i}|>y)dy
=\int_0^12ntP(|X_{i}|>nt)dt\to 0.$$
> (2) By DCT, as $x\to\infty$,
> $$
xP(|X_i|>x)=E(x1_{|X_i|>x})\leq E(|X_i|1_{|X_i|>x})\to 0.$$
> Also note that $\mu_n\to \mu$ when $n\to\infty$.

<br/><br/>

## 2.3 Borel-Cantelli Lemmas