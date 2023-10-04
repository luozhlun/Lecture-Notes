- [Chapter 2 Integration](#chapter-2-integration)
  - [2.1 Measurable functions](#21-measurable-functions)

# Chapter 2 Integration

## 2.1 Measurable functions

$\bf Def$

If $(X,\mathcal{M})$ and $(Y,\mathcal{N})$ are measurable spaces, a map $f:X\to Y$ is **$(\mathcal{M},\mathcal{N})$-measurable** if $f^{-1}(E)\in\mathcal{M}$ for all $E\in\mathcal{N}$.

Let $\overline{\mathbb{R}}=\mathbb{R}\cup\{\pm\infty\}$ with the topology making $F(x)=\tan(x),x\in[-\pi/2,\pi/2]$ a homeomorphism $[-\pi/2,\pi/2]\cong\overline{\mathbb{R}}$. If $Y\in\{\mathbb{R},\overline{\mathbb{R}},\mathbb{C}\}$ and $\mathcal{N}=\mathcal{B}_Y$ is the Borel $\sigma$-algebra. Then a $(\mathcal{M},\mathcal{B}_Y)$-measurable function $f:X\to Y$ is called **measurable** or **$\mathcal{M}$-measurable**. In particular, if $X$ is a topological space and $\mathcal{M}=\mathcal{B}_X$, then $f$ is called **Borel measurable**. If $(X,\mathcal{M})=(\mathbb{R},\mathcal{L})$, then $f$ is called **Lebesgue measurable**.

$\bf Rmk$

We always assume $f$ maps into $Y\in\{\mathbb{R},\overline{\mathbb{R}},\mathbb{C}\}$ with Borel $\sigma-$algebra unless specified.
