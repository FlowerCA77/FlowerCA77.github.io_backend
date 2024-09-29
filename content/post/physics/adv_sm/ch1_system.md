---
title: "热力学系统"
isCJKLanguage: true
description: 高统第一章，单个系统与热力学
date: 2024-09-28T19:56:03+08:00
categories:
    - adv.sm
tags:
    - 量子力学
    - 物理学
math: true
license: 
hidden: false
comments: true
draft: false
---

[返回目录](/p/高等统计物理/)


# 热力学系统 - Thermodynamics System

统计力学旨在以研究分子系统的方式来研究物质的性质，为此我们考虑单个多分子系统的动力学，并与热力学的唯象理论对比。

- 微观态 — 系统的 Schrodinger 方程的解，形如 \( \psi=\psi(\bm r_1,\bm r_2,\cdots,\bm r_N) \) 。
- 宏观态 — 系统的一组可测量的统计学量，例如: 系统的能量 \( E \) ，分子数 \( N \) ，容器的体积 \( V \) 等等
- 状态数 — \( \Omega(N,V,E) \) : 在以 \( (N,V,E) \) 确定的宏观态中允许的微观态数量

## 统计力学基本假设 - 等概率原理

**在以 \( (N,V,E) \) 确定的宏观态中，允许的微观态在热力学极限下以相等的概率出现。**

- 热力学极限 — 在保持分子数密度 \( n=\dfrac{N}{V} \) 不变的情况下让 \( N\to\infty，V\to\infty \)
- 物理无穷小 — 在体积 \( \Delta V \) 内的分子数 \( \Delta N \) 为无穷大，尽管 \( \Delta V \) 为无穷小

## 温度

考虑两个热接触的系统 \( A_{1,2} \) ，两个系统的整体在空间中孤立，因此:
- 物质 — 被困在每个系统中无法交换
- 能量 — 可以在两个系统之间交换，但无法向环境交换

![](figures/fig1-1.svg)
*细线表示导热隔板，粗线表示绝热隔板*

用指标 \( i=1,2 \) 来区分两个系统，设两个系统的总能量(明显恒定)为 \( E^{(0)}=E_1+E_2=\text{const} \)，则总系统的状态数为
\[
    \Omega^{(0)}(E_1,E_2)=\Omega_1(E_1)\Omega_2(E_2)=\Omega_1(E_1)\Omega_2(E^{(0)}-E_1)    
\]
平衡时状态数取极大值，因此对上式微分，我们用 \( \overline{E}_1 \) 来表示取极值时的能量分布，另一边的能量就是 \( \overline{E}_2=E^{(0)}-\overline{E}_1 \) 。 注意到 \( (\partial E_2/\partial E_1)_{E_1=\overline{E}_1}=-1 \)，故能得到
\[
    \left(\frac{\partial\log\Omega_1(E_1)}{\partial E_1}\right)_{E_1=\overline{E}_1}=\left(\frac{\partial\log\Omega_2(E_2)}{\partial E_2}\right)_{E_2=\overline{E}_2}
\]
这说明量 \( \beta=\left(\dfrac{\partial\log\Omega(E)}{\partial E}\right)_{E=\overline{E}} \) 在两个热接触系统中是相等的。 注意到 \( \dfrac{1}{T}=\left(\dfrac{\partial S}{\partial E}\right)_{N,V} \) ，两式近似为有限元差商后相除得到
\[
    \Delta S/\Delta(\log\Omega)\simeq\text{const}
\]
这就是 Boltzmann 关系。值得注意的是，Boltzmann 关系的解是 \( S=S_0+\lambda\log\dfrac{\Omega}{\Omega_0} \)，其中系数 \( \lambda \) 就是差商的渐进值，\( S_0 \) 和 \( \Omega_0 \) 为积分常数。Planck 发展了 Boltamann 关系，指出
\[
    S=k_B\log\Omega
\]
其中系数 \( k_B \) 正是上述的系数 \( \lambda \) , 被称为 Boltzmann 常数。

为了理解 Planck 的假设，我们注意到这相当于令 \( \Omega_0=1, S_0=0 \) 。回到温度的定义
\[
    \begin{split}
    \beta=\frac{1}{k_BT} &= \left(\frac{\partial}{\partial E}\frac{S}{k_B}\right)_{N,V} \\
    &= \left(\frac{\partial}{\partial E}\left(\frac{S_0}{k_B}+\log\frac{\Omega}{\Omega_0}\right)\right)_{N,V} \\
    &=\left(\frac{\partial}{\partial E}\log \Omega\right)_{N,V}=\frac{1}{\Omega}\left(\frac{\partial\Omega}{\partial E}\right)_{N,V}
    \end{split}
\]
可以看到温度并不依赖于积分常数 \( S_0 \) 和 \( \Omega_0 \) ，能够看出 **以 \( \beta \) 参数表示的温度的统计意义是状态数随能量增大的相对增长率** 。现在我们考虑低温极限，此时 \( \beta\to+\infty \) ，即随温度升高时 \( \Omega \) 以无穷大的速度增长，为了避免发散我们需要让此时状态数为 \( \Omega_0=1 \) ，因为 1 的任意指数都是 1 ，这种状态对应的熵为 \( S=S_0+k_B\log\dfrac{\Omega(=1)}{\Omega_0(=1)}=S_0 \)，我们规定为 0 。规定 \( \Omega=1 \) 时的熵 \( S_0=0 \) ，这是因为只有一种状态的系统就是纯粹的力学系统，熵是不应该存在的。

在这里我们可以看到，低温极限 \( \beta\to+\infty \) 时，状态数会自然回落到 \( \Omega\to 1 \) ，此时熵 \( S\to 0 \) ，因此我们说：**零温度系统 \(\Longleftrightarrow\) 纯力学系统** ，换句话说纯力学系统正是 \( T=0{\rm K} \) 的热力学系统。

## 热力学
我们类似的可以引入
\[
    \beta=\left(\dfrac{\partial\log\Omega(N,V,E)}{\partial E}\right)_{N,V}
\]
\[
    \eta=\left(\dfrac{\partial\log\Omega(N,V,E)}{\partial V}\right)_{N,E}
\]
\[
    \zeta=\left(\dfrac{\partial\log\Omega(N,V,E)}{\partial N}\right)_{V,E}
\]
这意味着存在全微分关系
\[
    d\log\Omega(N,V,E)=\beta dE+\eta dV+\zeta dN
\] 或 \[
    dS=k_B d(\log\Omega)=k_B\beta dE+k_B\eta dV+k_B\zeta dN
\] 或 \[
    dE=\frac{1}{k_B\beta}dS-\frac{\eta}{\beta}dV-\frac{\zeta}{\beta}dN
\]
如果我们认为这里的 \( E \) 为热力学能(内能)，则对比热力学第二定律
\[
    dE=TdS-PdV+\mu dN
\]
我们立马可以得到
\[
    \beta=\frac{1}{k_B T},\qquad\eta=\frac{P}{k_B T},\qquad\zeta=-\frac{\mu}{k_B T}
\]
这就从熵出发推出了全部热力学关系。

## 理想气体

在初步的模型中，我们认为理想气体 \( \Omega\propto V^N \) ，由此立刻可以得到 \( \dfrac{P}{T}=k_B\left(\dfrac{\partial\log\Omega}{\partial V}\right)_{N,E}=k_B\dfrac{N}{V} \)，即理想气体状态方程
\[ PV=Nk_BT \]

我们引入
- \( \Omega_N(E^*) \) : 半径 \( \sqrt{E^*} \) 的 \( 3N \) 维球面上的整数格点数
- \( \Sigma_N(E^*) \) : 半径 \( \sqrt{E^*} \) 的 \( 3N \) 维球面内(含球面)的整数格点数

则
\[
    \Sigma_N(E^*)=\sum_{E'\leq E^*}\Omega_N(E')\simeq\int_{E'\leq E^*} \frac{\partial\Omega_N(E')}{\partial E'}dE'
\]

考虑理想气体，\( \Omega(N,V,E) \) 事实上为满足 \( \sum_{r=1}^{3N}\varepsilon_r=E \) 的解的数量，其中每一个 \( \varepsilon_r \) 都是
\[
    \varepsilon(n_x,n_y,n_z)=\frac{h^2}{8mL^2}(n_x^2+n_y^2+n_z^2)\Longrightarrow(n_x^2+n_y^2+n_z^2)=\frac{8mV^{2/3}\varepsilon}{h^2}=\varepsilon^*
\]
这就将能量满足的方程化简为了 \( \sum_{r=1}^{3N}n_r^2=\dfrac{8mV^{2/3}E}{h^2}=E^* \) 的解数量，即 \( \Omega_N(E^*) \) 。

一方面，我们注意到 \( V, E \) 是以 \( V^{2/3}E \) 的整体出现在 \( \Omega \) 中的，因此 \( S(N,V,E)=S(N,V^{2/3}E) \) 。 \( V^{2/3}E=\text{const} \) 的过程在分子数不变时定义了等熵过程，即可逆绝热过程，容易得到 \( P=-\left(\dfrac{\partial E}{\partial V}\right)_{N,S}=\dfrac{2}{3}\dfrac{E}{V} \)，因此 \( PV^{5/3}=\text{const} \) ，即绝热指数为 \( 5/3 \) 。

由于 \( V, E \) 是以 \( V^{2/3}E \) 的整体出现在 \( \Omega \) 中的，因此我们将能量 \( E \) 改写为 \( E^*=\dfrac{8mV^{2/3}E}{h^2} \)
，等效的值 \( E^* \) 依赖于体积 \( V \)，此后我们可以将形如 \( \Omega(N,V,E) \) 的量记作 \( \Omega_N(E^*) \) ，这两种记号混用时应该记得这点。

我们知道
\[
    \Sigma_N(E^*)=\sum_{E'\leq E^*}\Omega_N(E')\simeq\int_{E'\leq E^*} \frac{\partial\Omega_N(E')}{\partial E'}dE'
\]
为此定义 \( \displaystyle{\Gamma}(N,V,E;\Delta)=\int\limits_{E-\frac{1}{2}\Delta< E < E+\frac{1}{2}\Delta}\Sigma_N(E^*)dE^* \) 为能量范围 \( \left(E-\dfrac{1}{2}\Delta，E+\dfrac{1}{2}\Delta\right) \) 内的状态数，因此在 \( \Delta\ll E \) 时
\[
    \Gamma(N,V,E;\Delta)\simeq\Delta\frac{\partial\Sigma(N,V,E)}{\partial E}
\]
我们用体积来渐进
\[
    \Sigma_N(E^*)\simeq\frac{1}{2^{3N}}\left\{\frac{\pi^{3N/2}}{(3N/2)!}{E^*}^{3N/2}\right\}    
\]
式中大括号内为 \( 3N \) 维空间中半径 \( \sqrt{E^*} \) 的球的体积，\( 2^{3N} \) 为 \( 3N \) 维空间的卦限数，相当于取坐标轴正轴的卦限。在上式利用 Striling 公式将阶乘化为对数，代入计算，最终可以得到
\[
    \log\Gamma(N,V,E;\Delta)\simeq N\log\left[\frac{V}{h^3}\left(\frac{4\pi mE}{3N}\right)^{3/2}\right]+\frac{3}{2}N
\]
我们可以看到，很奇怪但又的确是这样的是，宽度 \( \Delta \) 对 \( \Omega \) 没有贡献，这说明仅有 \( E \) 附近的很小的区域对状态数才有贡献。 将上式乘以 Boltzmann 常数，就得到了理想气体的熵
\[
    S(N,V,E)\simeq Nk_B\log\left[\frac{V}{h^3}\left(\frac{4\pi mE}{3N}\right)^{3/2}\right]+\frac{3}{2}Nk_B
\]

## Gibbs 计数修正

我们来考虑气体的混合问题。

![](figures/fig1-2.svg)

图中两种气体被导热隔板隔开，令 \( N=N_1+N_2 \) , \( V=V_1+V_2 \) ，热平衡时，其熵为两者之和，分别为

\[ S_i=N_i k_B\log V_i+\frac{3}{2} N_i k_B\left[1+\log\left(\frac{2\pi m_i k_B T}{h^2}\right)\right]\qquad (i=1,2)\]

混合后，其熵变为

\[ S_T=\sum_{i=1,2}\left\{N_i k_B\log V+\frac{3}{2} N_i k_B\left[1+\log\left(\frac{2\pi m_i k_B T}{h^2}\right)\right]\right\}\]

两者差值被定义为 **混合熵** ，即

\[
    \Delta S=S_T-\sum_{i=1,2}S_i=k_B\left(N_1\log\frac{V}{V_1}+N_2\log\frac{V}{V_2}\right)
\]

容易看到 \( \Delta S>0 \) ，这与熵增加原理一致。

我们用星号来表示气体分子数密度相同时的混合熵，用角标 \( 1\equiv 2 \) 表示同种分子的混合熵，因此

\[\begin{split}
    (\Delta S) &= k_B\left(N_1\log\frac{V}{V_1}+N_2\log\frac{V}{V_2}\right) > 0\\
    (\Delta S)^* &= k_B\left(N_1\log\frac{N}{N_1}+N_2\log\frac{N}{N_2}\right) > 0
\end{split}\]

注意到 \( \Delta S \) 不依赖于 \( m_i \) ，因此

\[ (\Delta S)_{1\equiv 2}=(\Delta S)>0,\qquad (\Delta S)^*_{1\equiv 2}=(\Delta S)^*>0 \]

但值得注意的是，混合熵 \( (\Delta S)^*_{1\equiv 2} \) 描述的混合过程是两边完全全等的气体的混合，因此应该有 \( (\Delta S)^*_{1\equiv 2}=0 \) 。

注意到，利用 Striling 公式，反过来有

\[ \begin{split}
    (\Delta S)^*_{1\equiv 2}=(\Delta S)^*
    &= k_B\left[N_1\log\frac{N}{N_1}+N_2\log\frac{N}{N_2}\right] \\
    &= k_B\left[(N_1+N_2)\log N-(N_1\log N_1+N_2\log N_2)\right] \\
    &= k_B(N\log N) - \left[ k_B(N_1\log N_1) + k_B(N_2\log N_2) \right] \\
    &\simeq k_B\log(N!) - \left[ k_B\log(N_1!) + k_B\log(N_2!) \right]
\end{split} \]

由此可见修正上述问题的方法就是在上述计算中令 \( S\leftarrow S-k_B\log(N!) \) 使 \( (\Delta S)^*_{1\equiv 2}=0 \) ，这样得出的熵叫做 **Sackur-Tetrode 方程** ，即
\[\begin{split}
    S(N,V,E) &= Nk_B\log\left[\frac{V}{h^3}\left(\frac{4\pi mE}{3N}\right)^{3/2}\right]+\frac{3}{2}Nk_B - k_B(N\log N-N)\\
    &= Nk_B\log\left[\frac{V}{Nh^3}\left(\frac{4\pi mE}{3N}\right)^{3/2}\right]+\frac{5}{2}Nk_B\\
    &= Nk_B\log\frac{V}{N}+\frac{3}{2}Nk_B\left[\frac{5}{3}+\log\left(\frac{2\pi mk_B T}{h^2}\right)\right]
\end{split}\]

注意到 \( S=k_B\log\Omega \) ，这一修正就等价于 \( \Omega\leftarrow\dfrac{1}{N!}\Omega \) ，我们称为 **Gibbs 计数修正** 。

事实上，经典理想气体分子不仅仅是全同的，更是不可分辨的。我们考虑全部可能的排列数
\[
    \frac{N!}{n_1!n_2!\cdots}    
\]
这些排列，任意对换都很大概率会导致 \( N,V,E \) 宏观态的改变，因此符合 \( N,V,E \) 宏观态的系统在上述排列中往往占极少数，在最极端的情况下仅占上述排列的一种，因此我们需要除掉上述排列中不符合 \( N,V,E \) 宏观态的排列个数。

Gibbs 的方案是只除掉分子 \( N! \) ，这不依赖于具体的排列细节 \( \{n_i\} \) 。这样的作法相当于对分布作了一个虚假的排列因子
\[ W\{n_i\}=\frac{1}{n_1!n_2!\cdots} \]
事实上我们应该直接令 \( W\{n_i\}=1 \) 才能得到正确的结果。我们可以看到， Gibbs 的方案导出经典统计的结论，这要求
\[ \langle n_i\rangle\ll 1 \]
以保证对换尽可能不破坏 \( N,V,E \) 宏观态条件，这个要求往往适用于温度充分高、密度充分低的气体。在极低温或极高密度情况下，我们需要让 \( W\{n_i\}=1 \) ，在后面我们看到这个要求导出的结果正是量子统计的结论。