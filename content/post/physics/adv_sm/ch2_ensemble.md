---
title: "系综理论"
isCJKLanguage: true
description: 高统第二章，系综理论基本原理 + 微正则系综
date: 2024-09-28T19:56:03+08:00
categories:
    - adv.sm
tags:
    - 统计力学
    - 凝聚态物理
    - 物理学
math: true
license: 
image: covers/adv_sm_chap2.jpg
hidden: false
comments: true
draft: false
---

[返回目录](/p/高等统计物理/)

# 系综理论 — Ensemble Theory

我们在本章考虑系综理论，首先我们来明确系统和系综的含义。

## 相空间

任意时刻，一组相坐标 \( (q,p)=(q_1,\cdots,q_{3N},p_1,\cdots,p_{3N}) \) 被视作系统的一个状态，因此这些坐标构成的 \( 6N \) 维空间将被视作系统的“坐标空间”，我们称之为 **相空间** 。相空间的前 \( 3N \) 维子空间描述系统的位形，称为 **位形空间** ，后 \( 3N \) 维描述系统的动量。换言之， \( 6N \) 维相空间正被视为 \( N \) 粒子构成的系统空间，其中每一个点都代表一个 \( N \) 粒子系统。

我们在 [第一章](/p/热力学系统/) 中详细研究了单个系统的行为，但我们引入了 **等概率原理** 这一重要的假设，也就是说我们研究的这个“单系统”应该被视作全部可能系统在某种意义上的代表，这就引出了所谓“系综”。

## 系综 (Ensemble)

正如我们所说，我们不再考虑单个系统。我们在每一时刻都考虑大量系统的 “illusory copies” （假想的副本），系统以相等的概率在这些副本之间选择，这种集合 {illusory copies} 就被称为系综。由于每个系统都为相空间中的一个点，因此系综可以被视作相空间上的流体。

我们知道，系统的运动方程为 Hamilton 正则方程

\[ \dot{q}_i=\frac{\partial H(q, p)}{\partial p_i},\qquad\dot{p}_i=-\frac{\partial H(q, p)}{\partial q_i} \]

系统的能量 \( E \) 给定，也就是说系综应该被限制在曲面 \( H(q,p)=E \) 上。根据我们在 [第一章](/p/热力学系统/) 中对理想气体的研究，我们宁愿将曲面 \( H(q,p)=E \) 扩宽成壳层 \( E-\dfrac{1}{2}\Delta < H(q,p) < E+\dfrac{1}{2}\Delta \) ，以 \( \Gamma \) 来代替 \( \Omega \) 进行计数。

我们用 \( \rho(q,p,t) \) 来表示在相空间给定点 \( q,p \) 处时间 \( t \) 时的系统密度，考虑力学量 \( f(q,p) \) 的系综平均值

\[ \braket{f}=f\ 的系综平均=\frac{\displaystyle{\int f(q,p)\rho(q,p,t)d^{3N}qd^{3N}p}}{\displaystyle{\int \rho(q,p,t)d^{3N}qd^{3N}p}}\]

这个值被称为 \( f \) 的统计观测值。

## Liouville 方程

作为在相空间上的“系统”流体，系综自然也服从流体力学的基本原理，即连续性方程

\[ \frac{\partial}{\partial t}\rho(q,p,t)+\mathop{\rm div}[\rho(q,p,t)\bm v]=0 \]

其中 \( \bm v \) 为相速度，div 为相空间的 \( 3N \) 维散度。我们把上式散度化简，代入 Hamilton 正则方程，很容易得到

\[ \frac{\partial\rho}{\partial t}+\{\rho, H\}=0 \]

上式中的花括号为 Poisson 括号。这个式子被称为 **Liouville 方程** ，容易看出左边正式 \( \dfrac{d\rho}{dt}=\dfrac{\partial\rho}{\partial t}+\{\rho, H\} \) ，因此上述方程也就是 \( \dfrac{d\rho}{dt}=0 \) 。

我们将 \( \dfrac{\partial\rho}{\partial t}\equiv 0 \) 的系综称为 **平衡态系综** ，这些系综中各个系统都处于热平衡。

## 微正则系综 — The Microcanonical Ensemble

微正则系综描述着以 \( N,V,E \) 确定的宏观态对应的系统集合，然而正像我们前面说的，我们宁愿用 \( \left(E-\dfrac{1}{2}\Delta, E+\dfrac{1}{2}\Delta\right) \) 这个区间来代替具体的能量 \( E \) 。我们用 \( \omega=(q,p) \) 来表示相空间的测度，即 \( d\omega=d^{3N}qd^{3N}p \) ，则微正则系综在相空间内占据的体积为

\[ \omega = \int'd\omega=\int' d^{3N}qd^{3N}p \]

其中带 \( \prime \) 的积分表示在区域 \( E-\dfrac{1}{2}\Delta < H(\omega) < E+\dfrac{1}{2}\Delta \) 中的积分。

根据等概率原理，我们知道微正则系综的密度应该是均匀的，即

\[ \rho(\omega)=\begin{dcases} \text{const}, & E-\dfrac{1}{2}\Delta < H(\omega) < E+\dfrac{1}{2}\Delta \\ 0, & \text{otherwise} \end{dcases} \]

上式不含时间，说明微正则系综是稳定系综，即系统间处于热平衡，因此我们有

\[\begin{split}
\braket{f}&=f\ 的系综平均\\
&= (f\ 的系综平均)\ 的时间平均\\
&= (f\ 的时间平均)\ 的系综平均\\
&= f\ 的长时间平均 = f_{\ 期望值}
\end{split}\]

为了确定状态数，我们需要确定一个基本度量 \( \omega_0 \) ，这个度量相当于状态计数的单位，即 \( \omega \) 体积内的状态数可以渐进表示为 \( \Gamma\simeq\dfrac{\omega}{\omega_0} \) ，此时熵 \( S=k_B\log\Gamma \) 。我们先放出结论，对于自由度为 \( f \) 的系统构成的微正则系综， \( \omega_0=h^f \) 为 Planck 常数的 \( f \) 次幂。

## 实例 1 — 理想气体

系综的体积为

\[\begin{split}
    \omega &= \int' d\omega=\int' d^{3N}q \int' d^{3N}p \\
    &= V^N\mathop{\displaystyle{\int\cdots\int}}\limits_{\left(E-\frac{1}{2}\Delta\right) < \sum_{r=1}^{3N}\frac{p_r^2}{2m} < \left(E+\frac{1}{2}\Delta\right)}d^{3N}p\xlongequal{y_r^2=\frac{p_r^2}{2m}} V^N\mathop{\displaystyle{\int\cdots\int}}\limits_{2m\left(E-\frac{1}{2}\Delta\right) < \sum_{r=1}^{3N}y_r^2 < 2m\left(E+\frac{1}{2}\Delta\right)}d^{3N}y
\end{split}\]

我们用 \( S_{n-1}(R) \) 和 \( V_n(R) \) 来表示 \( n \) 维球的表面积和体积，注意到 \( dV_n(R)=S_{n-1}(R)dR \) ，上式等于

\[\omega = V_{3N}\left[\sqrt{2m\left(E+\frac{1}{2}\Delta\right)}\right] - V_{3N}\left[\sqrt{2m\left(E-\frac{1}{2}\Delta\right)}\right] \simeq 
\Delta\sqrt{\frac{m}{2E}} S_{3N-1}\left(\sqrt{2mE}\right) \]

算出为 \( \omega\simeq\dfrac{\Delta}{E}V^N\dfrac{(2\pi mE)^{3N/2}}{[(3N/2)-1]!} \) ，回到 [第一章](/p/热力学系统/) 中对理想气体的研究中得到的 \( \Gamma \) ，两式相除得到 \( (\omega/\Gamma)_\text{asymptotic}\equiv\omega_0=h^{3N} \) 。

## 实例 2 — 1 维谐振子

一维谐振子的 Hamilton 量为 \( H(\omega)=\dfrac{p^2}{2m}+\dfrac{1}{2}m\omega^2q^2 \) ，通过求解 Liouville 方程可以确定其相空间轨迹为如下椭圆：

\[\frac{q^2}{2E/m\omega^2}+\frac{p^2}{2mE}=1\]

其面积为 \( \pi\cdot\sqrt{\dfrac{2E}{m\omega^2}}\cdot\sqrt{2mE}=\dfrac{2\pi E}{\omega} \) ，考虑此式的差值即为

\[\omega=\int'd\omega=\left.\dfrac{2\pi E}{\omega}\right|_{E-\frac{1}{2}\Delta}^{E+\frac{1}{2}\Delta}=\frac{2\pi\Delta}{\omega}\]

我们知道，谐振子的相邻两条能级之间的间距为 \( \hbar\omega=\dfrac{h\omega}{2\pi} \) ，因此状态数应该接近于 \( \Gamma\simeq\dfrac{\Delta}{\hbar\omega}=\dfrac{2\pi\Delta}{h\omega} \) ，由此基本体积确定为 \( \omega_0\simeq\dfrac{\omega}{\Gamma}=h \) ，这与 Heisenberg 的不确定性关系 \( \left(\Delta q\Delta p\right)_{\min}\simeq h \ 量级 \) 不谋而合。

[返回目录](/p/高等统计物理/)

[上一篇](/p/热力学系统/)

[下一篇](/p/系综理论/)