---
title: "机器学习与监督学习通论"
description: 
date: 2024-10-01T00:27:14+08:00
image: 
math: true
license: 
hidden: false
comments: true
draft: false
---

## 机器学习

我们以 Russell 和 Norvig 的教材上的内容来展开，关于机器学习，其概念可以在原文中找到：

> 如果一个智能体通过对世界进行观测来提高它的性能，我们称其为智能体 *学习（learning）* 。学习可以是简单的，例如记录一个购物清单，也可以是复杂的，例如爱因斯坦推断关于宇宙的新理论。当智能体是一台计算机时，我们称之为 **机器学习（machine learning）** ：一台计算机观测到一些数据，基于这些数据构建一个 *模型（model）* ，并将这个模型作为关于世界的一个 *假设（hypothesis）* 以及用于求解问题的软件的一部分。
>
> 为什么我们希望一台机器进行学习？为什么不通过合适的方式编程然后让它运行呢？这里有两个主要的原因。其一，程序的设计者无法预见未来所有可能发生的情形。举例来说，一个被设计用来导航迷宫的机器人必须掌握每一个它可能遇到的新迷宫的布局；一个用于预测股市价格的程序必须能适应各种股票涨跌的情形。其二，有时候设计者并不知道如何设计一个程序来求解目标问题。大多数人都能辨认自己家人的面孔，但是他们实现这一点利用的是潜意识，所以即使能力再强的程序员也不知道如何编写计算机程序来完成这项任务，除非他使用机器学习算法。

![](figures/ml_controltheory.svg)

从很高的角度看来，机器学习是一个负反馈的黑箱 \( M \) ，系统 \( M \) 本体具有可调的参数 \( w \) ，这些参数会受到输出影响。但机器学习是离散过程，因此这里的反馈并不会像自动控制系统里的反馈一样由微分方程决定，但我们还是要指出：机器学习的反馈过程，是一个 **负反馈** 过程。

事实上，执行和反馈是分开进行的，前者称为 **预测** ，后者称为 **训练** 。我们需要两组输入数据 \( x_1, x_2 \) 和其中一种输入的已知输出数据 \( y_1 \) 才能以最低限度驱动机器学习系统 \( M \) 。

\[ \left.\begin{align*}
&训练算法:& \\
\hline
&\quad \mathtt{input} & &x_1,y_1,w_0, loss_{\min}& \\
&\quad \mathtt{output}& &w& \\
&\qquad S_1 & &\tilde{y}_1\leftarrow M(x_1,w_0)& \\
&\qquad S_2 & &loss\leftarrow \mathrm{Dist}(y_1,\tilde{y}_1)& \\
&\qquad S_3 & &\mathtt{if}(loss>loss_{\min})& \\
&\qquad S_4 & &\qquad w\leftarrow \mathrm{Update}(loss, w_0)& \\
&\qquad S_4 & &\qquad \mathtt{goto}\ S_2& \\
&\qquad S_5 & &\mathtt{else}& \\
&\qquad S_6 & &\qquad \mathtt{return}\ w& \\
\end{align*}\quad\middle|\quad \begin{align*}
&预测算法:& \\
\hline
&\quad \mathtt{input} & &x_2, w& \\
&\quad \mathtt{output}& &y_2& \\
&\qquad S_1 & & y_2\leftarrow\ M(x_2,w) & \\
&\qquad S_2 & & \mathtt{return}\ y_2& \\
\end{align*}\right.\]