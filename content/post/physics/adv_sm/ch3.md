---
title: "正则系综"
isCJKLanguage: true
description: 高统第三章，正则系综
date: 2024-09-29T19:56:03+08:00
categories:
    - adv.sm
tags:
    - 统计力学
    - 凝聚态物理
    - 物理学
math: "mathjax"
license: 
image: covers/adv_sm_chap3.jpg
hidden: false
comments: true
draft: false
---

[返回目录](/p/高等统计物理/)

# 正则系综 — The Canonical Ensemble

我们考虑一个系统与一个大热库之间的平衡，这是研究正则系综的基础。事实上我们考虑的这种情况与 [第一章](/p/热力学系统/) 是类似的，其中一个是我们研究的系统，另一个是热库，只不过热库的能量足够大（或许是因为尺度足够大），我们研究的系统像是“浸入”在热库之中。

![](figures/adv_sm_fig3-1.png)

类似的能量守恒 \( E_r+E_r'=E^{(0)}=\text{const} \) 依然成立，只不过此时 \( E_r\ll E^{(0)} \) 。设 \( T=\dfrac{1}{k_B\beta} \) 为热库的温度，平衡时也为系统的温度。

类似的，由于能量守恒，状态数可以表示为 \( E_r \) 或 \( E_r' \) 的函数而不是同时独立地依赖于两者，我们记作 \( \Omega'(E'_r) \) ，\( \Omega' \) 的 \( \prime \) 表示状态数有可能依赖于热库的物理性质，但我们没有详细表出。

我们考虑 Taylor 展开

\[\begin{split}
\log\Omega'(E'_r) = \log\Omega'(E^{(0)}-E_r) &= \log\Omega'(E^{(0)})+\left(\frac{\partial\log\Omega'}{\partial E_r'}\right)_{E_r'=E^{(0)}}(-E_r)+\cdots \\
&\simeq \text{const}-\beta'E_r\quad\Longrightarrow\quad\Omega'(E'_r)=\text{const}\cdot e^{-\beta E_r}
\end{split}\]

这里我们用到了热平衡时系统的温度和热库的温度相等 \( \beta=\beta' \)。

根据等概率原理，取得上述角标 \( r \) 标注的状态的概率应该正比于上述状态数 \( P_r\propto\Omega'(E'_r)\propto e^{-\beta E_r} \) ，归一化后即可得到概率

\[ P_r=\frac{\exp(-\beta E_r)}{\sum\limits_r\exp(-\beta E_r)} \]

我们注意到 \( P_r \) 仅依赖于热库的温度，与热库的具体理化性质无关。

## 正则系综内的一个系统

考虑分享总能量 \( \mathscr{E} \) 的 \( \mathscr{N} \) 个全同系统，这些系统的能级为 \( E_r \) ，\( n_r \) 表示能量为 \( E_r \) 的系统数，则存在条件

\[ \sum_r n_r=\mathscr{N},\qquad\sum_r n_rE_r=\mathscr{E}=\mathscr{N}U \]

其中 \( U=\dfrac{\mathscr{E}}{\mathscr{N}} \) 为系统的平均能量，我们将其称为 **内能** ，在后面我们看到这个能量正是热力学能。

我们知道，系统在系综中的分配方式为

\[ W\{n_r\}=\frac{\mathscr{N}!}{n_0!n_1!n_2!\cdots} \]

热平衡时，类似的，\( W\{n_r\} \) 应该取极值，此时的分布我们设为 \( \{n^*_r\} \) 。考虑平均值

\[ \braket{n_r} = \frac{\sum_{\{n_r\}}n_rW\{n_r\}}{\sum_{\{n_r\}}W\{n_r\}} \]

我们将要说明， \( n_r^*=\braket{n_r} \) 。

### 分配极值

我们考虑目标函数的对数，使用 Striling 公式

\[ \log W=\log(\mathscr{N}!)-\sum_r\log(n_r!)\simeq\mathscr{N}\log\mathscr{N}-\sum_r n_r\log n_r \]

其变分为

\[ \delta(\log W)=-\sum_r(\log n_r+1)\delta n_r \]

考虑到分配条件，不妨引入 Lagrange 乘子

\[ \delta(\log W)-\alpha\delta(n_r)-\beta\delta(E_rn_r)\bigg|_{n_r=n^*_r}=\sum_r\left[-(\log n^*_r+1)-\alpha-\beta E_r\right]\delta n_r=0 \]

因此

\[ n^*_r=C\exp(-\beta E_r),\qquad C=e^{-(\alpha+1)} \]

很明显，根据系统数量条件

\[ \frac{n_r^*}{\mathscr{N}}=\frac{\exp(-\beta E_r)}{\sum\limits_r\exp(-\beta E_r)}=P_r \]

为了确定乘子 \( \alpha, \beta \) , 考虑系统能量条件

\[ U=\frac{\sum_r E_r\exp(-\beta E_r)}{\sum_r\exp(-\beta E_r)}=-\frac{\partial}{\partial\beta}\log\left[\sum_r\exp(-\beta E_r)\right] \]

我们记 \( Q(N,V,T)=\sum_r\exp(-\beta E_r) \) 称为 **配分函数** ，上式即 \( U=-\dfrac{\partial}{\partial\beta}\log Q \) 。

我们考虑 Helmholtz 自由能 \( F=U-TS \) ，存在微分关系

\[ \begin{split}
dF&=dU-TdS-SdT\\
&=(TdS-PdV+\mu dN)-TdS-SdT\\
&=-SdT-PdV+\mu dN
\end{split} \]

因此

\[\begin{split}
    U=F+TS&=F-T\left(\frac{\partial F}{\partial T}\right)_{N,V}=F+\beta\left(\frac{\partial F}{\partial\beta}\right)_{N,V}\\
    &=F\left(\frac{\partial\beta}{\partial\beta}\right)_{N,V}+\left(\frac{\partial F}{\partial\beta}\right)_{N,V}\beta=\left(\frac{\partial}{\partial\beta}(F\cdot\beta)\right)_{N,V}
\end{split}\]

这说明上述的 \( \beta \) 正是温度的 \( \beta \) 参数，且 \( Q=-F\cdot\beta \) 。

有了配分函数，那么 \( \mathscr{N}=\sum_r n^*_r=\sum_r C\exp(-\beta E_r)=CQ=e^{-(\alpha+1)}Q \) ，由此立马可以得到 \( \alpha=-\log\dfrac{\mathscr{N}}{Q}-1 \) 。

事实上 \( \alpha \) 乘子在这里是不重要的，因为我们总能归一化得到系数，而 \( \alpha \) 乘子仅仅确定系数而已。

### 均值

我们的目标是证明

\[ \frac{\braket{n_r}}{\mathscr{N}}=\frac{\exp(-\beta E_r)}{\sum_r\exp(-\beta E_r)} \]

并且式中的 \( \beta \) 乘子正恰好为温度的 \( \beta \) 参数。

可以采用 [Darwin-Fowler 的方法](/p/正则系综确定分布的平均值方法/) 来确定上式。

[返回目录](/p/高等统计物理/)

[上一篇](/p/系综理论/)

[下一篇](/p/高等统计物理/)