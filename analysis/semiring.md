$\bf Definition$ Let $X$ be a set, $\mathcal{J}\subset\mathcal{P}(X)$. We say $\mathcal{J}$  is a semi-ring, if

1. $\varnothing\in\mathcal{J}$
2. $A,B\in\mathcal{J}\Rightarrow A\cap B\in\mathcal{J}$
3. $\forall A,B\in\mathcal{J}$, $A-B$ can be written as a disjoint finite union of sets in $\mathcal{J}$.

$\bf Lemma$ Let $\mathcal{J}$ be a semi-ring of $X$, and let $\mathcal{A}=\{\text{all disjoint finite unions of sets in }\mathcal{J}\}$, then $\forall E,F\in \mathcal{A},E\cap F,E-F,E\cup F\in \mathcal{A}$.

$\bf Proof$ Assume $E=\bigsqcup_{i=1}^nE_i,F=\bigsqcup_{j=1}^mF_j\in \mathcal{A}$.

$E\cap F=(\bigsqcup_{i=1}^nE_i)\cap(\bigsqcup_{j=1}^mF_j)=\bigcup_{i,j}(E_i\cap F_j)$. Since $E_i,F_j\in\mathcal{J}$ and by the second property of semi-ring, $E_i\cap F_j\in\mathcal{J}$. Moreover, since both $\{E_i\}_{i=1}^n$ and $\{F_j\}_{j=1}^m$ are disjoint, $\{E_i\cap F_j\}$ is disjoint. Thus $E\cap F$ is a disjoint finite union of sets in $\mathcal{J}$, i.e. $E\cap F\in \mathcal{A}$.

For a special case, if $E\cap F=\varnothing$, then $E\sqcup F=\bigsqcup_{i=1}^nE_i\bigsqcup \bigsqcup_{j=1}^mF_j$ is a disjoint finite union of sets in $\mathcal{J}$, i.e. $E\sqcup F\in \mathcal{A}$. For general $E,F\in \mathcal{A}$, $E-F=(\bigsqcup_{i=1}^nE_i)-(\bigsqcup_{j=1}^mF_j)=\bigsqcup_{i=1}^n(E_i-\bigcup_{j=1}^mF_j)=\bigsqcup_{i=1}^n(\bigcap_{j=1}^m(E_i-F_j))$. Note that by the third property of semi-ring, each $E_i-F_j\in \mathcal{A}$. Then, by the result above, each $\bigcap_{j=1}^m(E_i-F_j)\in \mathcal{A}$. Hence their finite disjoint union $E-F=\bigsqcup_{i=1}^n(\bigcap_{j=1}^m(E_i-F_j))\in \mathcal{A}$.

By the result above, $E\cup F=(E-F)\sqcup F\in\mathcal{A}$.