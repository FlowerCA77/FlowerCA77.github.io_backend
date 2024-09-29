---
title: "正则系综确定分布的平均值方法"
isCJKLanguage: true
description: 按照 Darwin 和 Fowler 的方法计算分布的平均值
date: 2024-09-28T19:56:03+08:00
categories:
    - adv.sm
tags:
    - 统计力学
    - 凝聚态物理
    - 物理学
math: "mathjax"
license: 
image: covers/darwin_fowler.jpg
hidden: false
comments: true
draft: false
---

[返回目录](/p/高等统计物理/)

# 正则系综确定分布的平均值方法

## 背景

正则系综描述着共享总能量 \( \mathscr{E} \) 的 \( \mathscr{N} \) 个全同系统构成的系综，这些系统的能级为 \( E_r \) ， \( n_r \) 表示能量为 \( E_r \) 的系统个数，因此存在约束关系

\[
\sum_r n_r=\mathscr{N},\quad\sum_r n_rE_r=\mathscr{E}=\mathscr{N}U
\]

其中 \( U=\mathscr{E}/\mathscr{N} \) 为系综内系统的平均能量。

系统的改组数量为

\[ W\{n_r\}=\dfrac{\mathscr{N}!}{n_0!n_1!n_2!\cdots} \]

我们的目标是计算平均值

\[ \braket{n_r}=\dfrac{\sum_{\{n_r\}}n_rW\{n_r\}}{\sum_{\{n_r\}}W\{n_r\}} \]

## 引理

首先我们来研究 Cauchy 积分。考虑在紧子集(有界闭区域) \( K_0 \) 上的全纯函数 \( f(z) \) ， \( a \) 为邻域 \( \mathop{\rm Int}K_0 \) 内一点，我们考虑足够小的开圆盘 \( B_r(a)\Subset K_0 \)，根据 Cauchy 定理

\[\begin{split}
    \oint\frac{f(z)}{z-a}dz &= \oint_{B_r(a)}\frac{f(z)}{z-a}dz\xlongequal{z=a+re^{it}}\int_0^{2\pi}\frac{f(a+re^{it})}{re^{it}}d(a+re^{it}) \\
    &=\int_0^{2\pi}\frac{f(a+re^{it})}{re^{it}}rie^{it}dt=2\pi i\braket{f(a+re^{it})}\to 2\pi if(a),\quad(r\to 0)
\end{split}\]

由此我们得到了 Cauchy 积分公式 \( \displaystyle{f(a)=\frac{1}{2\pi i}\oint\frac{f(z)}{z-a}dz} \) 。

![](figures/taylor.svg)

现在我们考虑将 \( f(z) \) 在闭圆盘 \( K=\mathop{\rm Close}B_r(a) \) 的内部展开，记 \( C=\partial K \) 为盘线，根据上述 Cauchy 积分

\[ \forall z\in\mathop{\rm Int}K:f(z)=\frac{1}{2\pi i}\oint_C\frac{f(\xi)}{\xi-z}d\xi \]

考虑到几何级数展开

\[ \frac{1}{\xi-z}=\frac{1}{(\xi-a)-(z-a)}=\frac{1}{\xi-a}\frac{1}{1-\dfrac{z-a}{\xi-a}}=\frac{1}{\xi-a}\sum_{n=0}^\infty\left(\frac{z-a}{\xi-a}\right)^n \]

我们知道，几何级数是一致收敛的，因此

\[ \begin{split}
    f(z) &= \frac{1}{2\pi i}\oint_C\left[\sum_{n=0}^\infty\frac{(z-a)^n}{(\xi-a)^{n+1}}\right]f(\xi)d\xi \\
    &= \sum_{n=0}^\infty\left[\frac{1}{2\pi i}\oint_C\frac{f(\xi)}{(\xi-a)^{n+1}}d\xi\right](z-a)^n=\sum_{n=0}^\infty a_n(z-a)^n
\end{split} \]

这就得到了 \( f(z) \) 的 Taylor 展开，其系数为 \( \displaystyle{a_n=\frac{1}{2\pi i}\oint_C\frac{f(\xi)}{(\xi-a)^{n+1}}d\xi} \) 。

## 过程

我们引入参数 \( \omega_r \) ，考虑等效权重因子 \( \widetilde{W}\{n_r\}=\dfrac{\mathscr{N}!\omega_0^{n_0}\omega_1^{n_1}\omega_2^{n_2}\cdots}{n_0!n_1!n_2!\cdots} \) 。在这里我们并引入统计物理中惯用的辅助函数 \( \Gamma(\mathscr{N},U)=\sum_{\{n_r\}}\widetilde{W}\{n_r\} \) ，这就使得

\[ \braket{n_r}=\omega_r\frac{\partial}{\partial\omega_r}(\log\Gamma)\bigg|_{\omega\equiv 1} \]

函数

\[ \Gamma(\mathscr{N},U)=\mathscr{N}!\sum_{\{n_r\}}\left(\frac{\omega_0^{n_0}}{n_0!}\frac{\omega_1^{n_1}}{n_1!}\frac{\omega_2^{n_2}}{n_2!}\cdots\right) \]

我们考虑 **生成函数**

\[ G(\mathscr{N},z)=\sum_{U=0}^\infty\Gamma(\mathscr{N},U)z^{\mathscr{N}U} \]

考虑到分配约束条件，我们可以改写上式为

\[\begin{split}
    G(\mathscr{N},z)&=\sum_{U=0}^\infty\left[\mathscr{N}!\sum_{\{n_r\}}\left(\frac{\omega_0^{n_0}}{n_0!}\frac{\omega_1^{n_1}}{n_1!}\frac{\omega_2^{n_2}}{n_2!}\cdots\right)\right]\times\left(z^{n_0E_0}z^{n_1E_1}z^{n_2E_2}\cdots\right) \\
    &=\sum_{U=0}^\infty\sum_{\{n_r\}}\frac{\mathscr{N}!}{n_0!n_1!n_2!\cdots}(\omega_0z_0^{E_0})^{n_0}(\omega_1z_1^{E_1})^{n_1}(\omega_2z_2^{E_2})^{n_2}\cdots
\end{split}\]

由于我们对所有可能的内能 \( U \) 都有求和，因此上式等价于去掉对 \( U \) 的求和并将  \( \sum_{\{n_r\}} \) 的能量约束条件去掉，这样上述级数就彻底变成一个 Newton 展开式了，根据多项式定理我们立马得到 \( G(\mathscr{N},z)=[f(z)]^{\mathscr{N}} \) ，其中函数

\[ f(z)=\omega_0z^{E_0}+\omega_1z^{E_1}+\omega_2z^{E_2}+\cdots=\sum_r\omega_rz^{E_r} \]

现在为了求出 \( \Gamma \) 函数，我们注意到 \( \Gamma \) 是生成函数的系数，为此我们将生成函数变成 Taylor 级数。令 \( t=z^{\mathscr{N}} \) ，代入生成函数的定义式中得到

\[ K(t)=\sum_{U=0}^\infty\Gamma(\mathscr{N},U)t^U \]

其中 \( K(t)=[f(z)]^{\mathscr{N}} \) ，因此我们立马可以得到

\[\begin{split}
    \Gamma(\mathscr{N},U)&=\frac{1}{2\pi i}\oint\frac{K(t)}{t^{U+1}}dt \\
    &=\frac{1}{2\pi i}\oint\frac{[f(z)]^{\mathscr{N}}}{z^{\mathscr{N}U+\mathscr{N}}}d(z^{\mathscr{N}}) \\
    &=\frac{1}{2\pi i}\oint\frac{[f(z)]^{\mathscr{N}}}{z^{\mathscr{N}U+\mathscr{N}}}\mathscr{N}z^{\mathscr{N}-1}dz \\
    &=\frac{\mathscr{N}}{2\pi i}\oint\frac{[f(z)]^{\mathscr{N}}}{z^{\mathscr{N}U+1}}dz
\end{split}\]