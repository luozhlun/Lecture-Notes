#! https://zhuanlan.zhihu.com/p/607507517

![Image](https://pic4.zhimg.com/80/v2-c7f757c1ed2012d47f8af37d1d3f4e31.jpg)

# 偏微分方程PDE笔记整理

## 第二章 波动方程

### 一阶线性方程——特征线法

$$
\begin{cases}
u_t+A(x,t)u_x+B(x,t)u+C(x,t)=0\\[1ex]
u|_{t=0}=\varphi(x)
\end{cases}
$$

**第一步**：特征方程为
$$
\begin{cases}
\dfrac{\mathrm{d}x}{\mathrm{d}t}=A(x,t)\\[1ex]
x(0)=c
\end{cases}
$$
解得特征线为 $x=x(t)$ （含有 $c$ ），并解得 $c=c(x,t)$ 。

**第二步**：设 $U(t)=u(x(t),t)$ ，则
$$
\begin{cases}
\dfrac{\mathrm{d}U(t)}{\mathrm{d}t}+B(x(t),t)U(t)+C(x(t),t)=0\\[1ex]
U(0)=\varphi(c)
\end{cases}
$$
解得 $U(t)$ 的表达式（含有 $c$ ），代入 $c=c(x,t)$ 就得到了原方程的解 $u(x,t)$ 。

<br/><br/>

### 一维初值问题——D'Alembert公式

一维初值问题
$$
\begin{cases}
\Box u=u_{tt}-a^2u_{xx}=f(x,t)&x\in\mathbb{R},t>0\\[1ex]
u|_{t=0}=\varphi(x)&x\in\mathbb{R}\\[1ex]
u_t|_{t=0}=\psi(x)&x\in\mathbb{R}\\[1ex]
\end{cases}
$$
的解为
$$\color{red}{
\begin{aligned}
u(x,t)&=\frac{\varphi(x+at)+\varphi(x-at)}{2}+\frac{1}{2a}\int_{x-at}^{x+at}\psi(\xi)\mathrm{d}\xi\\[1ex]
&+\frac{1}{2a}\int_0^t\mathrm{d}\tau\int_{x-a(t-\tau)}^{x+a(t-\tau)}f(\xi,\tau)\mathrm{d}\xi
\end{aligned}}
$$

**注**： $u_{tt}-a^2u_{xx}=0$ 的通解为 $u=F(x+at)+G(x-at)$ ，即左行波+右行波。

<br/><br/>

### Gronwall不等式与Green公式

$\color{red}{\bf Thm\ (Gronwall不等式的微分形式)}$

设非负函数 $G(x)\in C^1[0,T]$ ， $G(0)=0$ 。非负函数 $F(x)$ 在 $[0,T]$ 上递增可积。若存在 $C>0$ 使得 $G'(x)\leq CG(x)+F(x)$
，则

1. $G(x)\leq\dfrac{\mathrm{e}^{Cx}-1}{C}F(x)$ ；
2. $G'(x)\leq\mathrm{e}^{Cx}F(x)$ 。

$\color{red}{\bf Thm\ (Green公式)}$

$$
\oint_{\partial D}P\mathrm{d}x+Q\mathrm{d}y=\iint_D(Q_x-P_y)\mathrm{d}x\mathrm{d}y
$$

<br/><br/>

### 一维初值问题——能量不等式

设 $Q=\mathbb{R}\times(0,+\infty)$ ， $u\in C(\overline Q)\cap C^{2,1}(Q)$ 满足
$$
\begin{cases}
\Box u=u_{tt}-a^2u_{xx}=f(x,t)&x\in\mathbb{R},t>0\\[1ex]
u|_{t=0}=\varphi(x)&x\in\mathbb{R}\\[1ex]
u_t|_{t=0}=\psi(x)&x\in\mathbb{R}\\[1ex]
\end{cases}
$$
则
$$\color{red}{
\int_{\Omega_\tau}(u_t^2+a^2u_x^2)\mathrm{d}x\leq\mathrm{e}^{t_0}\left[\int_{\Omega_0}(\psi^2+a^2\varphi_x^2)\mathrm{d}x+\iint_{K_\tau}f^2\mathrm{d}x\mathrm{d}t\right]}\\[1ex]
\color{red}{
\iint_{K_\tau}(u_t^2+a^2u_x^2)\mathrm{d}x\leq\mathrm{e}^{t_0}\left[\int_{\Omega_0}(\psi^2+a^2\varphi_x^2)\mathrm{d}x+\iint_{K_\tau}f^2\mathrm{d}x\mathrm{d}t\right]}
$$

![波动方程能量不等式](https://pic4.zhimg.com/80/v2-0d906e51d2ab8c0755dea7ef92cec631.jpg)

**证明思路**：在波动方程两边乘以 $u_t$ 并在 $K_\tau$ 上积分，将等式左边变形并用Green公式，分析其沿着 $K_\tau$ 的边界积分各项的正负，并作放缩，最后用Gronwall不等式。

**注**：用该明思路可直接证明解的唯一性。

<br/><br/>

### 半无界问题——延拓法

#### 第一边值条件

$$
\begin{cases}
\Box u=f(x,t)&x>0,t>0\\[1ex]
u|_{t=0}=\varphi(x)&x\geq0\\[1ex]
u_t|_{t=0}=\psi(x)&x\geq0\\[1ex]
\color{red}{u|_{x=0}=g(t)}&t>0
\end{cases}
$$
令 $v(x,t)=u(x,t)-g(t)$ ，因此不妨设 $g(t)\equiv0$ ，则奇延拓后由D'Alembert公式得，当 $x\geq at$ 时，
$$
\begin{aligned}
u(x,t)&=\frac{\varphi(x+at)+\varphi(x-at)}{2}+\frac{1}{2a}\int_{x-at}^{x+at}\psi(\xi)\mathrm{d}\xi\\[1ex]
&+\frac{1}{2a}\int_0^t\mathrm{d}\tau\int_{x-a(t-\tau)}^{x+a(t-\tau)}f(\xi,\tau)\mathrm{d}\xi
\end{aligned}
$$
当 $x<at$ 时，
$$
\begin{aligned}
u(x,t)&=\frac{\varphi(x+at)-\varphi(at-x)}{2}+\frac{1}{2a}\int_{at-x}^{x+at}\psi(\xi)\mathrm{d}\xi\\[1ex]
&+\frac{1}{2a}\int_0^{t-x/a}\mathrm{d}\tau\int_{a(t-\tau)-x}^{x+a(t-\tau)}f(\xi,\tau)\mathrm{d}\xi\\[1ex]
&+\frac{1}{2a}\int_{t-x/a}^t\mathrm{d}\tau\int_{x-a(t-\tau)}^{x+a(t-\tau)}f(\xi,\tau)\mathrm{d}\xi
\end{aligned}
$$

![波动方程延拓法](https://pic4.zhimg.com/80/v2-c0d803391e0a6cb571b59684fe8ff7ae.jpg)

<br/>

#### 第二边值条件

$$
\begin{cases}
\Box u=f(x,t)&x>0,t>0\\[1ex]
u|_{t=0}=\varphi(x)&x\geq0\\[1ex]
u_t|_{t=0}=\psi(x)&x\geq0\\[1ex]
\color{red}{u_x|_{x=0}=g(t)}&t>0
\end{cases}
$$
令 $v(x,t)=u(x,t)-g(t)x$ ，因此不妨设 $g(t)\equiv0$ ，同理进行偶延拓即可。

<br/><br/>

### 混合问题——分离变量法

以第一边值条件为例
$$
\begin{cases}
\Box u=u_{tt}-a^2u_{xx}=f(x,t)&0<x<l,t>0\\[1ex]
u|_{t=0}=\varphi(x)&0\leq x\leq l\\[1ex]
u_t|_{t=0}=\psi(x)&0\leq x\leq l\\[1ex]
u|_{x=0}=g_1(t)&t>0\\[1ex]
u|_{x=l}=g_2(t)&t>0
\end{cases}
$$
令 $v(x,t)=u(x,t)-\left(1-\dfrac{x}{l}\right)g_1(t)-\dfrac{x}{l}g_2(t)$ ，因此不妨设 $g_1(t)\equiv g_2(t)\equiv 0$ 。

**第一步**：设 $u(x,t)=X(x)T(t)$ 满足相应的齐次方程，则 $XT''-a^2X''T=0$ 。除以 $a^2XT$ ，得到
$$
\frac{T''}{a^2T}=\frac{X''}{X}\equiv-\lambda
$$
再代入边值条件得到S-L问题
$$
\begin{cases}
X''+\lambda X=0\\[1ex]
X(0)=X(l)=0
\end{cases}
$$
由ODE可知，通解为 $X(x)=c_1\sin(\sqrt{\lambda}x)+c_2\cos(\sqrt{\lambda}x)$ 。代入边值条件得到 $c_2=0$ 和 $\sin(\sqrt{\lambda}l)=0$ ，从而所有特征值和相应的特征向量为 $\lambda_n=\left(\dfrac{n\pi}{l}\right)^2,n=1,2,\dots$ 和 $X_n(x)=\sin\left(\dfrac{n\pi x}{l}\right)$ 。

**第二步**：将 $f,\varphi,\psi$ 用特征函数系展开得到
$$
f(x,t)=\sum_{n=1}^\infty f_n(t)X_n(x)\\[1ex]
\varphi(x)=\sum_{n=1}^\infty\varphi_nX_n(x)\\[1ex]
\psi(x)=\sum_{n=1}^\infty\psi_nX_n(x)
$$
其中
$$
\begin{aligned}
f_n(t)&=\frac{\int_0^lf(x,t)X_n(x)\mathrm{d}x}{\int_0^lX^2_n(x)\mathrm{d}x}=\frac{2}{l}\int_0^lf(x,t)X_n(x)\mathrm{d}x\\[1ex]
\varphi_n&=\frac{\int_0^l\varphi(x)X_n(x)\mathrm{d}x}{\int_0^lX^2_n(x)\mathrm{d}x}=\frac{2}{l}\int_0^l\varphi(x)X_n(x)\mathrm{d}x\\[1ex]
\psi_n&=\frac{\int_0^l\psi(x)X_n(x)\mathrm{d}x}{\int_0^lX^2_n(x)\mathrm{d}x}=\frac{2}{l}\int_0^l\psi(x)X_n(x)\mathrm{d}x
\end{aligned}
$$
这里常用 $\displaystyle\int_0^l\sin^2\left(\dfrac{n\pi x}{l}\right)\mathrm{d}x=\frac{l}{2}$ 。

**第三步**：设 $\displaystyle u(x,t)=\sum_{n=1}^\infty T_n(t)X_n(x)$ ，代入波动方程、S-L问题、 $f,\varphi,\psi$ 的展开式和初值条件，得到ODE
$$
\begin{cases}
T_n''(t)+a^2\lambda_nT_n(t)=f_n(t)\\[1ex]
T_n(0)=\varphi_n\\[1ex]
T'_n(0)=\psi_n
\end{cases}
$$
由常数变易法
$$\color{red}{
\begin{aligned}
T_n(t)&=\varphi_n\cos(\sqrt{a^2\lambda_n}t)+\frac{\psi_n}{\sqrt{a^2\lambda_n}}\sin(\sqrt{a^2\lambda_n}t)\\[1ex]
&+\frac{1}{\sqrt{a^2\lambda_n}}\int_0^tf_n(\tau)\sin(\sqrt{a^2\lambda_n}(t-\tau))\mathrm{d}\tau
\end{aligned}}
$$
从而得到 $u$ 的表达式。

**注**：若给的是其他边值条件，化齐次后也可以分离变量，可能会得到不同的S-L问题。

---

## 第三章 热传导方程

### Fourier变换

$\bf Def\ (Fourier变换、逆变换)$

$$
\hat f(\lambda)=\frac{1}{\sqrt{2\pi}}\int_{-\infty}^{+\infty}f(x)\mathrm{e}^{-i\lambda x}\mathrm{d}x\\[2ex]
\check f(\lambda)=\frac{1}{\sqrt{2\pi}}\int_{-\infty}^{+\infty}f(x)\mathrm{e}^{i\lambda x}\mathrm{d}x\\
$$

- 微商性质
- 乘多项式
- 平移性质
- 伸缩性质
- 对称性质
- 卷积性质

<br/><br/>

### 初值问题——Poisson公式

初值问题
$$
\begin{cases}
Lu=u_t-a^2u_{xx}=f(x,t)&x\in\mathbb{R},t>0\\[1ex]
u|_{t=0}=\varphi(x)&x\in\mathbb{R}
\end{cases}
$$
的解为
$$\color{red}{
\begin{aligned}
u(x,t)&=\int_{-\infty}^{+\infty}K(x-\xi,t)\varphi(\xi)\mathrm{d}\xi\\[1ex]
&+\int_0^t\mathrm{d}\tau\int_{-\infty}^{+\infty}K(x-\xi,t-\tau)f(\xi,\tau)\mathrm{d}\xi
\end{aligned}}
$$
其中
$$
K(x,t)=\frac{1}{\sqrt{4a^2t\pi}}\exp\left(\frac{-x^2}{4a^2t}\right)I_{\{t>0\}}(x,t)
$$
称为Poisson核。

<br/><br/>

### 边值条件的物理意义

- 第一边值条件 $u|_\Sigma=g$ ：表示物体边界温度 $g$
- 第二边值条件 $\dfrac{\partial u}{\partial\vec n}\bigg|_\Sigma=g$ ： $g\geq 0$ 表示边界流入热量； $g=0$ 表示绝热
- 第三边值条件 $\left(\dfrac{\partial u}{\partial\vec n}+\alpha u\right)\bigg|_\Sigma=g$ ：边界与周围介质有热交换， $g$ 表示温度， $\alpha$ 表示热交换系数

<br/><br/>

### 半无界问题——延拓法

#### 第一边值条件

$$
\begin{cases}
L_u=u_t-a^2u_{xx}=f(x,t)&x>0,t>0\\[1ex]
u|_{t=0}=\varphi(x)&x\geq0\\[1ex]
\color{red}{u|_{x=0}=g(t)}&t>0
\end{cases}
$$
令 $v(x,t)=u(x,t)-g(t)$ ，因此不妨设 $g(t)\equiv0$ ，则奇延拓后由Poisson公式得
$$
\begin{aligned}
u(x,t)&=\int_0^{+\infty}[K(x-\xi,t)-K(x+\xi,t)]\varphi(\xi)\mathrm{d}\xi\\[1ex]
&+\int_0^t\mathrm{d}\tau\int_0^{+\infty}[K(x-\xi,t-\tau)-K(x+\xi,t-\tau)]f(\xi,\tau)\mathrm{d}\xi
\end{aligned}
$$

<br/>

#### 第二边值条件

$$
\begin{cases}
Lu=u_t-a^2u_{xx}=f(x,t)&x>0,t>0\\[1ex]
u|_{t=0}=\varphi(x)&x\geq0\\[1ex]
\color{red}{u_x|_{x=0}=g(t)}&t>0
\end{cases}
$$
令 $v(x,t)=u(x,t)-g(t)x$ ，因此不妨设 $g(t)\equiv0$ ，则偶延拓后由Poisson公式得
$$
\begin{aligned}
u(x,t)&=\int_0^{+\infty}[K(x-\xi,t)+K(x+\xi,t)]\varphi(\xi)\mathrm{d}\xi\\[1ex]
&+\int_0^t\mathrm{d}\tau\int_0^{+\infty}[K(x-\xi,t-\tau)+K(x+\xi,t-\tau)]f(\xi,\tau)\mathrm{d}\xi
\end{aligned}
$$

<br/><br/>

### 混合问题——分离变量法

以第一边值条件为例
$$
\begin{cases}
Lu=u_t-a^2u_{xx}=f(x,t)&0<x<l,t>0\\[1ex]
u|_{t=0}=\varphi(x)&0\leq x\leq l\\[1ex]
u|_{x=0}=g_1(t)&t>0\\[1ex]
u|_{x=l}=g_2(t)&t>0
\end{cases}
$$
令 $v(x,t)=u(x,t)-\left(1-\dfrac{x}{l}\right)g_1(t)-\dfrac{x}{l}g_2(t)$ ，因此不妨设 $g_1(t)\equiv g_2(t)\equiv 0$ 。

**第一步**：设 $u(x,t)=X(x)T(t)$ 满足相应的齐次方程，则 $XT'-a^2X''T=0$ 。除以 $a^2X(x)T(t)$ ，得到
$$
\frac{T'}{a^2T}=\frac{X''}{X}\equiv-\lambda
$$
再代入边值条件得到S-L问题
$$
\begin{cases}
X''(x)+\lambda X(x)=0\\[1ex]
X(0)=X(l)=0
\end{cases}
$$
由ODE可知，通解为 $X(x)=c_1\sin(\sqrt{\lambda}x)+c_2\cos(\sqrt{\lambda}x)$ 。代入边值条件得到 $c_2=0$ 和 $\sin(\sqrt{\lambda}l)=0$ ，从而所有特征值和相应的特征函数分别为 $\lambda_n=\left(\dfrac{n\pi}{l}\right)^2,n=1,2,\dots$ 和 $X_n(x)=\sin\left(\dfrac{n\pi x}{l}\right)$ 。

**第二步**：将 $f,\varphi$ 用特征函数系展开得到
$$
f(x,t)=\sum_{n=1}^\infty f_n(t)X_n(x)\\[1ex]
\varphi(x)=\sum_{n=1}^\infty\varphi_nX_n(x)
$$
其中
$$
\begin{aligned}
f_n(t)&=\frac{\int_0^lf(x,t)X_n(x)\mathrm{d}x}{\int_0^lX^2_n(x)\mathrm{d}x}=\frac{2}{l}\int_0^lf(x,t)X_n(x)\mathrm{d}x\\[1ex]
\varphi_n&=\frac{\int_0^l\varphi(x)X_n(x)\mathrm{d}x}{\int_0^lX^2_n(x)\mathrm{d}x}=\frac{2}{l}\int_0^l\varphi(x)X_n(x)\mathrm{d}x
\end{aligned}
$$
这里常用 $\displaystyle\int_0^l\sin^2\left(\dfrac{n\pi x}{l}\right)\mathrm{d}x=\frac{l}{2}$ 。

**第三步**：设 $\displaystyle u(x,t)=\sum_{n=1}^\infty T_n(t)X_n(x)$ ，代入热传导方程、S-L问题、 $\varphi,f$ 的展开式和初值条件，得到ODE
$$
\begin{cases}
T_n'(t)+a^2\lambda_nT_n(t)=f_n(t)\\[1ex]
T_n(0)=\varphi_n
\end{cases}
$$
由常数变易法
$$
T_n(t)=\varphi_n\exp\left(-a^2\lambda_nt\right)+\int_0^tf_n(\tau)\exp\left(-a^2\lambda_n(t-\tau)\right)\mathrm{d}\tau
$$
从而得到 $u$ 的表达式。

**注**：若给的是其他边值条件，化齐次后也可以分离变量，可能会得到不同的S-L问题。

<br/><br/>

### 混合问题——极值原理

$\color{red}{\bf Thm\ (弱极值原理)}$

设 $Q=\{(x,t):0<x<l,0<t\leq T\}$ ， $Q$ 的侧面和底边统称为抛物边界 $\Gamma$ 。

设 $u\in C(\overline Q)\cap C^{2,1}(Q)$ ，记 $Lu=u_t-a^2u_{xx}$ 。

1. 若 $Lu=f(x,t)\leq 0$ ，则 $u$ 在 $\overline Q$ 的最大值必在抛物边界 $\Gamma$ 上取到；
2. 若 $Lu=f(x,t)\geq 0$ ，则 $u$ 在 $\overline Q$ 的最小值必在抛物边界 $\Gamma$ 上取到。

**证明**：当 $Lu<0$ 时，分析各偏导的符号容易证明。对于一般的情况，考虑添加扰动，分析 $w=u-\varepsilon t$ 即可。

$\color{red}{\bf Thm\ (弱极值原理推广)}$

设 $Q=\{(x,t):0<x<l,0<t\leq T\}$ ， $Q$ 的侧面和底边统称为抛物边界 $\Gamma$ ， $c(x,t)$ 在 $\overline Q$ 有界非负。

设 $u\in C(\overline Q)\cap C^{2,1}(Q)$ ，记 $Lu=u_t-a^2u_{xx}+c(x,t)u$ 。

1. 若 $Lu=f(x,t)\leq 0$ ，则 $u$ 在 $\overline Q$ 的非负最大值（如果有）必在抛物边界 $\Gamma$ 上取到；
2. 若 $Lu=f(x,t)\geq 0$ ，则 $u$ 在 $\overline Q$ 的非正最小值（如果有）必在抛物边界 $\Gamma$ 上取到；
3. 若 $c(x,t)\equiv 0$ ，则上述“非负最值”可用“最值”代替。

**证明**：当 $Lu<0$ 时，分析各偏导的符号容易证明。对于一般的情况，令 $w=u+\varepsilon\mathrm{e}^{bx}$ 。取充分大的 $b>0$ 可使 $Lw=Lu+\varepsilon\mathrm{e}^{bx}(-a^2b^2+c(x,t))<0$ ，应用前面的结论并令 $\varepsilon\to 0$ 即可。

$\color{red}{\bf Thm\ (比较原理)}$

设 $\alpha_i(t),\beta_i(t)\geq0$ 并且 $\alpha_i(t)+\beta_i(t)\neq 0$ ，若
$$
\begin{cases}
Lu=u_t-a^2u_{xx}\geq 0&(x,t)\in Q\\[1ex]
u|_{t=0}\geq 0&0\leq x\leq l\\[1ex]
[-\alpha_1(t)u_x+\beta_1(t)u]|_{x=0}\geq 0&0<t\leq T\\[1ex]
[\alpha_2(t)u_x+\beta_2(t)u]|_{x=l}\geq 0&0<t\leq T
\end{cases}
$$
则在 $\overline Q$ 上 $u\geq 0$ 。一般令 $w=u-v$ 应用定理。（综合了书上各类边值条件的情况）

**证明**：边值条件严格大于零时利用弱极值原理和各偏导的符号容易证明。对于一般的情况，考虑到辅助函数 $z(x,t)=2a^2t+(x-l/2)^2$ 满足
$$
\begin{cases}
Lz=0&(x,t)\in Q\\[1ex]
z|_{t=0}\geq 0&0\leq x\leq l\\[1ex]
[-\alpha_1(t)z_x+\beta_1(t)z]|_{x=0}>0&0<t\leq T\\[1ex]
[\alpha_2(t)z_x+\beta_2(t)z]|_{x=l}>0&0<t\leq T
\end{cases}
$$
令 $w=u+\varepsilon z$ ，应用前面的结论并令 $\varepsilon\to 0$ 即可。

<br/><br/>

### 混合问题——最大模估计

#### 第一边值条件

$$
\begin{cases}
Lu=u_t-a^2u_{xx}=f(x,t)&(x,t)\in Q\\[1ex]
u|_{t=0}=\varphi(x)&0\leq x\leq l\\[1ex]
u|_{x=0}=g_1(t)&0<t\leq T\\[1ex]
u|_{x=l}=g_2(t)&0<t\leq T
\end{cases}
$$
则 $\max_{\overline Q}|u|\leq FT+B$ ，其中
$$
F=\sup_Q|f|\\[1ex]
B=\max\left\{\sup_{[0,l]}|\varphi|,\sup_{[0,T]}|g_1|,\sup_{[0,T]}|g_2|\right\}
$$

<br/>

#### 第二、三边值条件

$$
\begin{cases}
Lu=u_t-a^2u_{xx}=f(x,t)&(x,t)\in Q\\[1ex]
u|_{t=0}=\varphi(x)&0\leq x\leq l\\[1ex]
[-u_x+\alpha(t)u]|_{x=0}=g_1(t)&0<t\leq T\\[1ex]
[u_x+\beta(t)u]|_{x=l}=g_2(t)&0<t\leq T
\end{cases}
$$
则 $\max_{\overline Q}|u|\leq C(F+B)$ ，其中 $C$ 与 $a,l,T$ 有关，
$$
F=\sup_Q|f|\\[1ex]
B=\max\left\{\sup_{[0,l]}|\varphi|,\sup_{[0,T]}|g_1|,\sup_{[0,T]}|g_2|\right\}
$$

**注**：解的唯一性。

---

## 第四章 Poisson方程

### 极值原理

$\color{red}{\bf Thm\ (弱极值原理)}$

设 $\Omega$ 是 $\mathbb{R^n}$ 中的有界开区域， $c(x)$ 在 $\Omega$ 有界非负。

设 $u\in C(\overline Q)\cap C^2(Q)$ ，记 $Lu=-\Delta u+c(x)u$ 。

1. 若 $Lu=f(x)\leq 0$ ，则 $u$ 在 $\overline Q$ 的非负最大值（如果有）必在 $\partial Q$ 上取到；
2. 若 $Lu=f(x)\geq 0$ ，则 $u$ 在 $\overline Q$ 的非正最小值（如果有）必在 $\partial Q$ 上取到；
3. 若 $c(x)\equiv 0$ ，上述“非负最值”可用“最值”代替。

**证明**：当 $Lu<0$ 时，分析各偏导的符号容易证明。对于一般的情况，令 $w=u+\varepsilon\mathrm{e}^{bx}$ 。取充分大的 $b>0$ 可使 $Lw=Lu+\varepsilon\mathrm{e}^{bx}(-b^2+c(x))<0$ ，应用前面的结论并令 $\varepsilon\to 0$ 即可。

$\color{red}{\bf Thm\ (强极值原理)}$

设 $\Omega$ 是 $\mathbb{R^n}$ 中的有界开区域， $c(x)$ 在 $\Omega$ 有界非负。设 $u\in C(\overline Q)\cap C^2(Q)$ ， $Lu=-\Delta u+c(x)u\leq 0$ 。则如果 $u$ 在 $\Omega$ 内取到了非负最大值，则 $u$ 恒为常数。


$\color{red}{\bf Thm\ (第一边值条件的比较原理)}$

设 $c(x)$ 在 $\Omega$ 有界非负
$$
\begin{cases}
Lu=-\Delta u+c(x)u\geq 0&x\in\Omega\\[1ex]
u|_{\partial\Omega}\geq 0
\end{cases}
$$
则在 $\Omega$ 上 $u\geq 0$ 。一般令 $w=u-v$ 应用定理。

**证明**：若不然，由弱极值原理可知 $u$ 在 $\partial Q$ 取到负的最小值，这与 $u|_{\partial\Omega}\geq 0$ 矛盾。

$\color{red}{\bf Thm\ (第三边值条件的比较原理)}$

设 $c(x)$ 在 $\Omega$ 有界非负， $\alpha(x)>0$
$$
\begin{cases}
Lu=-\Delta u+c(x)u\geq 0&x\in\Omega\\[1ex]
\left(\dfrac{\partial u}{\partial\vec n}+\alpha(x)u\right)\bigg|_{\partial\Omega}\geq 0
\end{cases}
$$
则在 $\Omega$ 上 $u\geq 0$ 。一般令 $w=u-v$ 应用定理。

**证明**：若不然，由弱极值原理可知 $u$ 在 $x_0\in\partial Q$ 取到负的最小值。从而外法线方向导数 $\dfrac{\partial u}{\partial\vec n}\bigg|_{x_0}\leq 0$ ，从而 $\left(\dfrac{\partial u}{\partial\vec n}+\alpha(x)u\right)\bigg|_{x_0}\leq\alpha(x_0)u(x_0)<0$ ，矛盾。

<br/><br/>

### 最大模估计

#### 第一边值条件

设 $c(x)$ 在 $\Omega$ 有界非负
$$
\begin{cases}
Lu=-\Delta u+c(x)u=f(x),x\in\Omega\\[1ex]
u|_{\partial\Omega}=\varphi(x)
\end{cases}
$$
则 $\max_{\overline Q}|u|\leq CF+\Phi$ ，其中 $C$ 与 $n$ 、 $\Omega$ 的直径 $d$ 有关，
$$
F=\sup_\Omega|f|\\[1ex]
\Phi=\sup_{\partial\Omega}|\varphi|\\[1ex]
$$

**证明**：不妨设 $\Omega$ 包含坐标原点。注意到 $z(x)=\frac{F}{2n}(d^2-|x|^2)+\Phi\geq 0$ 满足
$$
\begin{cases}
Lz=F+c(x)z\geq F&x\in\Omega\\[1ex]
z|_{\partial\Omega}\geq\Phi
\end{cases}
$$
令 $w=z\pm u$ ，则
$$
\begin{cases}
Lw\geq F\pm f\geq 0&x\in\Omega\\[1ex]
w|_{\partial\Omega}\geq\Phi\pm\varphi\geq 0
\end{cases}
$$
应用比较原理即可。

<br/>

#### 第三边值条件

设 $c(x)$ 在 $\Omega$ 有界非负， $\alpha(x)\geq\alpha_0>0$
$$
\begin{cases}
Lu=-\Delta u+c(x)u=f(x)&x\in\Omega\\[1ex]
\left(\dfrac{\partial u}{\partial\vec n}+\alpha(x)u\right)\bigg|_{\partial\Omega}=\varphi(x)
\end{cases}
$$
则 $\max_{\overline Q}|u|\leq C(F+\Phi)$ ，其中 $C$ 与 $\alpha_0,n,d$ 有关，
$$
F=\sup_\Omega|f|\\[1ex]
\Phi=\sup_{\partial\Omega}|\varphi|\\[1ex]
$$

**证明**：不妨设 $\Omega$ 包含坐标原点。注意到
$$
z(x)=\frac{F}{2n}\left(\frac{1+d^2}{\alpha_0}+d^2-|x|^2\right)+\frac{\Phi}{\alpha_0}\geq 0
$$
满足 $Lz=F+c(x)z\geq F$ 。记 $\partial\Omega$ 的单位外法向量为 $(\beta_1(x),\dots,\beta_n(x))$ ，则 $\sum\beta_i^2(x)=1$ ，于是
$$
\begin{aligned}
\left(\dfrac{\partial z}{\partial\vec n}+\alpha(x)z\right)\bigg|_{\partial\Omega}&=-\frac{F}{n}\sum_{i=1}^nx_i\beta_i(x)+\alpha(x)z(x)\\[1ex]
&\geq-\frac{F}{2n}\left(\sum_{i=1}^nx_i^2+\sum_{i=1}^n\beta_i^2(x)\right)+\alpha_0z(x)\\[1ex]
&\geq-\frac{F}{2n}(|x|^2+1)+\frac{F}{2n}(1+d^2)+\Phi\geq\Phi\\[1ex]
\end{aligned}
$$
令 $w=z\pm u$ ，同理可证。

**注**：解的唯一性。

<br/><br/>

### 能量模估计

设 $c(x)$ 在 $\Omega$ 有界非负， $c(x)\geq c_0>0$
$$
\begin{cases}
-\Delta u+c(x)u=f(x)&x\in\Omega\\[1ex]
u|_{\partial\Omega}=0
\end{cases}
$$
在Poisson方程两边乘以 $u$ 并在 $\Omega$ 上积分得到
$$
-\int_{\Omega}u\Delta u\mathrm{d}x+\int_{\Omega}c(x)u^2\mathrm{d}x=\int_{\Omega}fu\mathrm{d}x
$$
其中右边
$$
\int_{\Omega}fu\mathrm{d}x\leq\frac{c_0}{2}\int_{\Omega}u^2\mathrm{d}x+\frac{1}{2c_0}\int_{\Omega}f^2\mathrm{d}x
$$
而由Green公式 $\iint_\Omega\nabla\cdot\vec  A\mathrm{d}S=\oint_{\partial\Omega}\vec A\cdot\vec n\mathrm{d}s$ ，令 $A=u\nabla u$ 得到
$$
\int_{\Omega}(|\nabla u|^2+u\Delta u)\mathrm{d}x=\oint_{\partial\Omega}u\nabla u\cdot\vec n\mathrm{d}x=0
$$
即
$$
-\int_{\Omega}u\Delta u\mathrm{d}x=\int_{\Omega}|\nabla u|^2\mathrm{d}x
$$
从而有能量模估计
$$
\int_{\Omega}|\nabla u|^2\mathrm{d}x+\frac{c_0}{2}\int_\Omega u^2\mathrm{d}x\leq\frac{1}{2c_0}\int_\Omega f^2\mathrm{d}x
$$

**注**：证明方法有用。

---