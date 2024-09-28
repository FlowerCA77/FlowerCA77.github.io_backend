---
title: "热力学系统"
isCJKLanguage: true
description: 存放高统笔记
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

# 热力学系统 - Thermodynamics System

统计力学旨在以研究分子系统的方式来研究物质的性质, 为此我们考虑单个多分子系统的动力学, 并与热力学的唯象理论对比.

- 微观态: 系统的 Schrodinger 方程的解, 形如 \( \psi=\psi(\bm r_1,\bm r_2,\cdots,\bm r_N) \) .
- 宏观态: 系统的一组可测量的统计学量, 例如: 系统的能量 \( E \) , 分子数 \( N \) , 容器的体积 \( V \) 等等
- 状态数 \( \Omega(N,V,E) \) : 在以 \( (N,V,E) \) 确定的宏观态中允许的微观态数量

## 统计力学基本假设 - 等概率原理

**在以 \( (N,V,E) \) 确定的宏观态中, 允许的微观态在热力学极限下以相等的概率出现.**

- 热力学极限: 在保持分子数密度 \( n=\dfrac{N}{V} \) 不变的情况下让 \( N\to\infty, V\to\infty \)
- 物理无穷小: 在体积 \( \Delta V \) 内的分子数 \( \Delta N \) 为无穷大, 尽管 \( \Delta V \) 为无穷小

## 温度

考虑两个热接触的系统 \( A_{1,2} \) , 两个系统的整体在空间中孤立, 因此:
- 物质: 被困在每个系统中无法交换
- 能量: 可以在两个系统之间交换, 但无法向环境交换
用指标 \( i=1,2 \) 来区分两个系统, 设两个系统的总能量(明显恒定)为 \( E^{(0)}=E_1+E_2=const. \), 则总系统的状态数为
\[
    \Omega^{(0)}(E_1,E_2)=\Omega_1(E_1)\Omega_2(E_2)=\Omega_1(E_1)\Omega_2(E^{(0)}-E_1)    
\]
平衡时状态数取极大值, 因此对上式微分, 我们用 \( \overline{E}_1 \) 来表示取极值时的能量分布, 另一边的能量就是 \( \overline{E}_2=E^{(0)}-\overline{E}_1 \) . 注意到 \( (\partial E_2/\partial E_1)_{E_1=\overline{E}_1}=-1 \), 故能得到
\[
    \left(\frac{\partial\log\Omega_1(E_1)}{\partial E_1}\right)_{E_1=\overline{E}_1}=\left(\frac{\partial\log\Omega_2(E_2)}{\partial E_2}\right)_{E_2=\overline{E}_2}
\]
这说明量 \( \beta=\left(\dfrac{\partial\log\Omega(E)}{\partial E}\right)_{E=\overline{E}} \) 在两个热接触系统中是相等的. 注意到 \( \frac{1}{T}=\left(\frac{\partial S}{\partial E}\right)_{N,V} \) , 两式相除得到
\[
    \Delta S/\Delta(\log\Omega)=const.
\]
这就是 Boltamann 关系. Planck 发展了 Boltamann 关系, 指出
\[
    S=k_B\log\Omega
\]
其中系数 \( k_B \) 被称为 Boltzmann 常数.

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
    d[\log\Omega(N,V,E)]=\beta dE+\eta dV+\zeta dN
\]
\[
    \Rightarrow dS=k_B d(\log\Omega)=k_B\beta dE+k_B\eta dV+k_B\zeta dN
\]
\[
    \Rightarrow dE=\frac{1}{k_B\beta}dS-\frac{\eta}{\beta}dV-\frac{\zeta}{\beta}dN
\]
如果我们认为这里的 \( E \) 为热力学能(内能), 则对比热力学第二定律
\[
    dE=TdS-PdV+\mu dN
\]
我们立马可以得到
\[
    \beta=\frac{1}{k_B T},\qquad\eta=\frac{P}{k_B T},\qquad\zeta=-\frac{\mu}{k_B T}
\]
这就从熵出发推出了全部热力学关系.

## 理想气体

在初步的模型中, 我们认为理想气体 \( \Omega\propto V^N \) , 由此立刻可以得到 \( \dfrac{P}{T}=k_B\left(\dfrac{\partial\log\Omega}{\partial V}\right)_{N,E}=k_B\dfrac{N}{V} \), 即理想气体状态方程
\[ PV=Nk_BT \]

我们引入
- \( \Omega_N(E^*) \) : 半径 \( \sqrt{E^*} \) 的 \( 3N \) 维球面上的整数格点数
- \( \Sigma_N(E^*) \) : 半径 \( \sqrt{E^*} \) 的 \( 3N \) 维球面内(含球面)的整数格点数

则
\[
    \Sigma_N(E^*)=\sum_{E'\leq E^*}\Omega_N(E')\simeq\int_{E'\leq E^*} \frac{\partial\Omega_N(E')}{\partial E'}dE'
\]

考虑理想气体, \( \Omega(N,V,E) \) 事实上为满足 \( \sum_{r=1}^{3N}\varepsilon_r=E \) 的解的数量, 其中每一个 \( \varepsilon_r \) 都是
\[
    \varepsilon(n_x,n_y,n_z)=\frac{h^2}{8mL^2}(n_x^2+n_y^2+n_z^2)\Longrightarrow(n_x^2+n_y^2+n_z^2)=\frac{8mV^{2/3}\varepsilon}{h^2}=\varepsilon^*
\]
这就将能量满足的方程化简为了 \( \sum_{r=1}^{3N}n_r^2=\dfrac{8mV^{2/3}E}{h^2}=E^* \) 的解数量, 即 \( \Omega_N(E^*) \) .

一方面, 我们注意到 \( V, E \) 是以 \( V^{2/3}E \) 的整体出现在 \( \Omega \) 中的, 因此 \( S(N,V,E)=S(N,V^{2/3}E) \) . \( V^{2/3}E=const. \) 的过程在分子数不变时定义了等熵过程, 即可逆绝热过程, 容易得到 \( P=-(\frac{\partial E}{\partial V})_{N,S}=\frac{2}{3}\frac{E}{V} \), 因此 \( PV^{5/3}=const \) , 即绝热指数为 \( 5/3 \) .

我们知道
\[
    \Sigma_N(E^*)=\sum_{E'\leq E^*}\Omega_N(E')\simeq\int_{E'\leq E^*} \frac{\partial\Omega_N(E')}{\partial E'}dE'
\]
为此定义 \( \displaystyle{\Gamma}(N,V,E;\Delta)=\int\limits_{(E-\frac{1}{2}\Delta, E+\frac{1}{2}\Delta)}\Sigma_N(E)dE \) 为能量范围 \( \left(E-\dfrac{1}{2}\Delta, E+\dfrac{1}{2}\Delta\right) \) 内的状态数, 因此在 \( \Delta\ll E \) 时
\[
    \Gamma(N,V,E;\Delta)\simeq\Delta\frac{\partial\Sigma(N,V,E)}{\partial E}
\]
我们用体积来渐进
\[
    \Sigma_N(E^*)\simeq\frac{1}{2^{3N}}\left\{\frac{\pi^{3N/2}}{(3N/2)!}{E^*}^{3N/2}\right\}    
\]
式中大括号内为 \( 3N \) 维空间中半径 \( \sqrt{E^*} \) 的球的体积, \( 2^{3N} \) 为 \( 3N \) 维空间的卦限数, 相当于取坐标轴正轴的卦限. 通过计算, 最终可以得到
\[
    \log\Gamma(N,V,E;\Delta)\simeq N\log\left[\frac{V}{h^3}\left(\frac{4\pi mE}{3N}\right)^{3/2}\right]+\frac{3}{2}N
\]
我们可以看到, 宽度 \( \Delta \) 对 \( \Omega \) 没有贡献, 这说明仅有 \( E \) 附近的很小的区域对状态数才有贡献. 将上式乘以 Boltzmann 常数, 就得到了理想气体的熵
\[
    S(N,V,E)\simeq Nk_B\log\left[\frac{V}{h^3}\left(\frac{4\pi mE}{3N}\right)^{3/2}\right]+\frac{3}{2}Nk_B
\]