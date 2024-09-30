---
title: "机器学习"
description: 存放机器学习的理论、算法和实现，以及一些具体例子的封装
date: 2024-09-30T20:11:51+08:00
image: 
math: "mathjax"
license: 
hidden: false
comments: true
draft: false
---

# 教材

Stuart Russell, Peter Novrig. *Artificial Intelligence: A Modern Approach*, Fourth Edition. 中译本: 人工智能: 现代方法, 张博雅等译. 北京: 人民邮电出版社, 2023.1.


# 投稿目录

[机器学习与监督学习通论](/p/机器学习与监督学习通论)

[\( k \)-邻近算法 与 \( k\bm d \) 树 及其应用](/p/knn-算法/)

# 绪论 — Introduce

*内容来自 : wikipedia*

## 简介

> **Machine learning (ML)** is a field of study in artificial intelligence concerned with the development and study of statistical algorithms that can learn from data and generalize to unseen data, and thus perform tasks without explicit instructions. Quick progress in the field of deep learning, beginning in 2010s, allowed neural networks to surpass many previous approaches in performance.
>
> *机器学习 (ML) 是人工智能领域的一门学科，专注于研究从数据中学习并对未见过的数据进行泛化，从而能够执行无需明确指令的任务的统计算法的发展和研究。深度学习领域的快速进步始于 2010 年代，使得神经网络在性能上超越了之前的许多方法。*
>
> ML finds application in many fields, including natural language processing, computer vision, speech recognition, email filtering, agriculture, and medicine. The application of ML to business problems is known as predictive analytics.
>
> *ML 在许多领域都有应用，包括自然语言处理、计算机视觉、语音识别、电子邮件过滤、农业和医学等。ML在商业问题中的应用被称为预测分析。*
>
> Statistics and mathematical optimization (mathematical programming) methods comprise the foundations of machine learning. Data mining is a related field of study, focusing on exploratory data analysis (EDA) via unsupervised learning.
>
> *统计学和数学优化（数学规划）方法构成了机器学习的基础。数据挖掘是与之相关的研究领域，专注于通过无监督学习进行探索性数据分析 (EDA) 。*
>
> From a theoretical viewpoint, probably approximately correct (PAC) learning provides a framework for describing machine learning.
>
> *从理论角度来看，“可能近似正确” (PAC) 学习为机器学习提供了一个描述框架。*

## 理论

> A core objective of a learner is to generalize from its experience. Generalization in this context is the ability of a learning machine to perform accurately on new, unseen examples/tasks after having experienced a learning data set. The training examples come from some generally unknown probability distribution (considered representative of the space of occurrences) and the learner has to build a general model about this space that enables it to produce sufficiently accurate predictions in new cases.
> 
> *学习者的核心目标是从其经验中进行归纳。在此背景下，泛化指的是学习机器在经历了学习数据集之后，能够在未见过的新的示例/任务上准确执行的能力。训练示例来自一些通常未知的概率分布（被认为是发生空间的代表性分布），学习者必须构建一个关于这个空间的通用模型，以便在新情况下产生足够准确的预测。*
> 
> The computational analysis of machine learning algorithms and their performance is a branch of theoretical computer science known as computational learning theory via the Probably Approximately Correct Learning (PAC) model. Because training sets are finite and the future is uncertain, learning theory usually does not yield guarantees of the performance of algorithms. Instead, probabilistic bounds on the performance are quite common. The bias–variance decomposition is one way to quantify generalization error.
> 
> *机器学习算法的计算分析及其性能是理论计算机科学的一个分支，通过“可能近似正确学习” (PAC) 模型被称为计算学习理论。由于训练集是有限的，未来是不确定的，学习理论通常不能保证算法的性能。相反，性能的概率性界通常很常见。偏差-方差分解是量化泛化误差的一种方法。*
> 
> For the best performance in the context of generalization, the complexity of the hypothesis should match the complexity of the function underlying the data. If the hypothesis is less complex than the function, then the model has under fitted the data. If the complexity of the model is increased in response, then the training error decreases. But if the hypothesis is too complex, then the model is subject to overfitting and generalization will be poorer.
> *在泛化性能方面要达到最佳表现，假设的复杂度应该与数据背后的函数复杂度相匹配。如果假设的复杂度低于函数，那么模型就会对数据进行欠拟合。如果相应地增加模型的复杂度，那么训练误差就会降低。但如果假设过于复杂，那么模型就会出现过拟合问题，泛化性能就会变差。*
> 
> In addition to performance bounds, learning theorists study the time complexity and feasibility of learning. In computational learning theory, a computation is considered feasible if it can be done in polynomial time. There are two kinds of time complexity results: Positive results show that a certain class of functions can be learned in polynomial time. Negative results show that certain classes cannot be learned in polynomial time.
> 
> *除了性能边界外，学习理论家还研究学习的时间复杂度和可行性。在计算学习理论中，如果一个计算可以在多项式时间内完成，则认为它是可行的。有两种时间复杂度结果：正面结果表明，某些类型的函数可以在多项式时间内学习。负面结果表明，某些类函数无法在多项式时间内学习。*

## 方法

> Machine learning approaches are traditionally divided into three broad categories, which correspond to learning paradigms, depending on the nature of the "signal" or "feedback" available to the learning system:
>
> *机器学习的方法通常被分为三大类，这与学习系统的 “信号” 或 “反馈” 的性质有关，对应于不同的学习范式：*
>
> - **Supervised learning**: The computer is presented with example inputs and their desired outputs, given by a "teacher", and the goal is to learn a general rule that maps inputs to outputs.
>
>   - *监督学习：计算机被展示一些示例输入和它们的期望输出（由“老师”给出），目的是学习一个将输入映射到输出的通用规则。*
>
> - **Unsupervised learning**: No labels are given to the learning algorithm, leaving it on its own to find structure in its input. Unsupervised learning can be a goal in itself (discovering hidden patterns in data) or a means towards an end (feature learning).
>
>   - *无监督学习：学习算法不被给予任何标签，完全靠自己从输入数据中寻找结构。无监督学习既可以作为一种目标（在数据中发现隐藏的模式），也可以作为实现其他目标的一种手段（特征学习）。*
>
> - **Reinforcement learning**: A computer program interacts with a dynamic environment in which it must perform a certain goal (such as driving a vehicle or playing a game against an opponent). As it navigates its problem space, the program is provided feedback that's analogous to rewards, which it tries to maximize.
>
>   - *强化学习：计算机程序与动态环境交互，必须完成某个目标（例如驾驶车辆或与对手进行游戏）。在探索问题空间的过程中，程序会收到类似于奖励的反馈，并试图最大化这些奖励。*

### 监督学习 — Supervised Learning

> Supervised learning algorithms build a mathematical model of a set of data that contains both the inputs and the desired outputs. The data, known as training data, consists of a set of training examples. Each training example has one or more inputs and the desired output, also known as a supervisory signal. In the mathematical model, each training example is represented by an array or vector, sometimes called a feature vector, and the training data is represented by a matrix. Through iterative optimization of an objective function, supervised learning algorithms learn a function that can be used to predict the output associated with new inputs. An optimal function allows the algorithm to correctly determine the output for inputs that were not a part of the training data. An algorithm that improves the accuracy of its outputs or predictions over time is said to have learned to perform that task.
>
> *监督学习算法会建立一个包含输入和期望输出的数据集的数学模型。该数据被称为训练数据，由一组训练示例组成。每个训练示例包含一个或多个输入和期望输出（也称为监督信号）。在数学模型中，每个训练示例由一个数组或向量表示，有时称为特征向量，而训练数据则由一个矩阵表示。通过对目标函数的迭代优化，监督学习算法可以学习一个函数，用于预测与新输入相关的输出。一个最优函数使算法能够正确确定未在训练数据中出现的输入的输出。如果一个算法能够在不断学习的过程中提高其输出或预测的准确性，则可以说该算法学会了执行该任务。*
>
> Types of supervised-learning algorithms include active learning, classification and regression. Classification algorithms are used when the outputs are restricted to a limited set of values, and regression algorithms are used when the outputs may have any numerical value within a range. As an example, for a classification algorithm that filters emails, the input would be an incoming email, and the output would be the name of the folder in which to file the email. Examples of regression would be predicting the height of a person, or the future temperature. 
>
> *监督学习算法的类型包括主动学习、分类和回归。当输出被限制为有限的一组值时，使用分类算法。当输出可能在一定范围内具有任何数值时，使用回归算法。例如，对于用于过滤电子邮件的分类算法，输入将是一封新到达的电子邮件，输出将是该电子邮件应被归档到哪个文件夹的名称。预测身高或预测未来温度是回归算法的一些示例。*
>
> Similarity learning is an area of supervised machine learning closely related to regression and classification, but the goal is to learn from examples using a similarity function that measures how similar or related two objects are. It has applications in ranking, recommendation systems, visual identity tracking, face verification, and speaker verification.
>
> *相似性学习是监督式机器学习的一个领域，与回归和分类密切相关，但其目标是使用一个衡量两个对象之间相似度或相关性的相似性函数来从示例中学习。它在排名、推荐系统、视觉身份跟踪、人脸验证和说话人验证等领域都有应用。*

### 无监督学习 — Unsupervised Learning

> Unsupervised learning algorithms find structures in data that has not been labeled, classified or categorized. Instead of responding to feedback, unsupervised learning algorithms identify commonalities in the data and react based on the presence or absence of such commonalities in each new piece of data. Central applications of unsupervised machine learning include clustering, dimensionality reduction, and density estimation. Unsupervised learning algorithms also streamlined the process of identifying large indel based haplotypes of a gene of interest from pan-genome.
>
> *无监督学习算法可以在未标记、分类或归类的数据中发现结构。与响应反馈不同，无监督学习算法会识别数据中的共同点，并根据每块新数据中是否存在这些共同点来做出反应。无监督机器学习的主要应用包括聚类、降维和密度估计。无监督学习算法还简化了从泛基因组中识别基因感兴趣区域的大型插入/缺失等位基因型 (haplotype) 的过程。*
>
> Cluster analysis is the assignment of a set of observations into subsets (called clusters) so that observations within the same cluster are similar according to one or more predesignated criteria, while observations drawn from different clusters are dissimilar. Different clustering techniques make different assumptions on the structure of the data, often defined by some similarity metric and evaluated, for example, by internal compactness, or the similarity between members of the same cluster, and separation, the difference between clusters. Other methods are based on estimated density and graph connectivity.
>
> *聚类分析是将一组观测数据划分为若干子集（称为簇）的过程，使得同一簇中的观测数据在根据预先指定的一或多个标准（如相似性）的相似性方面相似，而来自不同簇的观测数据则不相似。不同的聚类技术对数据结构有不同的假设，通常由一些参数（如距离或相似度）定义，并通过例如距离或同一簇成员之间的相似度、不同簇之间的差异等进行评估。其他方法则基于密度和轮廓。*
>
> A special type of unsupervised learning called, self-supervised learning involves training a model by generating the supervisory signal from the data itself.
>
> *一种特殊的无监督学习方法称为“自监督学习”，它通过从数据本身生成监督信号来训练模型。*

### 半监督学习 — Semi-Supervised Learning

> Semi-supervised learning falls between unsupervised learning (without any labeled training data) and supervised learning (with completely labeled training data). Some of the training examples are missing training labels, yet many machine-learning researchers have found that unlabeled data, when used in conjunction with a small amount of labeled data, can produce a considerable improvement in learning accuracy.
>
> *半监督学习介于无监督学习（没有任何标注的训练数据）和有监督学习（有完全标注的训练数据）之间。一些训练示例缺少训练标签，但许多机器学习研究人员发现，在少量标注数据的辅助下，未标注数据可以显著提高学习准确性。*
>
> In weakly supervised learning, the training labels are noisy, limited, or imprecise; however, these labels are often cheaper to obtain, resulting in larger effective training sets.
>
> *在弱监督学习中，训练标签是噪声的、有限的或不准确的；然而，这些标签通常更容易获取，因此可以生成更大的有效训练集。*

### 强化学习 — Reinforcement Learning

> Reinforcement learning is an area of machine learning concerned with how software agents ought to take actions in an environment so as to maximize some notion of cumulative reward. Due to its generality, the field is studied in many other disciplines, such as game theory, control theory, operations research, information theory, simulation-based optimization, multi-agent systems, swarm intelligence, statistics and genetic algorithms. In reinforcement learning, the environment is typically represented as a Markov decision process (MDP). Many reinforcements learning algorithms use dynamic programming techniques. Reinforcement learning algorithms do not assume knowledge of an exact mathematical model of the MDP and are used when exact models are infeasible. Reinforcement learning algorithms are used in autonomous vehicles or in learning to play a game against a human opponent.
>
> *强化学习是机器学习的一个领域，关注软件代理在环境中应该如何采取行动，以最大化某种累积奖励的概念。由于其通用性，该领域在许多其他学科中也受到研究，例如博弈论、控制理论、运筹学、信息论、基于模拟的优化、多代理系统、群体智能、统计学和遗传算法。在强化学习中，环境通常被表示为马尔可夫决策过程 (MDP) 。许多强化学习算法使用动态规划技术。强化学习算法不假定对 MDP 有精确的数学模型的了解，并且在精确模型不可行的情况下使用。强化学习算法用于自主车辆或学习与人类对手玩游戏。*

### 降维 — Dimensionality Reduction

> Dimensionality reduction is a process of reducing the number of random variables under consideration by obtaining a set of principal variables. In other words, it is a process of reducing the dimension of the feature set, also called the "number of features". Most of the dimensionality reduction techniques can be considered as either feature elimination or extraction. One of the popular methods of dimensionality reduction is principal component analysis (PCA). PCA involves changing higher-dimensional data (e.g., 3D) to a smaller space (e.g., 2D). The manifold hypothesis proposes that high-dimensional data sets lie along low-dimensional manifolds, and many dimensionality reduction techniques make this assumption, leading to the area of manifold learning and manifold regularization.
>
> *降维是一种通过获取主变量集来减少考虑的随机变量数量的过程。换句话说，它是一种减少特征集维度（也称为“特征数量”）的过程。大多数降维技术可以被认为是特征消除或提取。降维的一种流行方法是主成分分析 (PCA) 。PCA 涉及将高维数据（例如 3D ）转换为较小的空间（例如 2D ）。 “流形假设”提出高维数据集位于低维流形上，许多降维技术都基于这一假设，从而产生了流形学习和流形正则化领域。*

### 自学习 — Self-Learning

> Self-learning, as a machine learning paradigm was introduced in 1982 along with a neural network capable of self-learning, named crossbar adaptive array (CAA). It is learning with no external rewards and no external teacher advice. The CAA self-learning algorithm computes, in a crossbar fashion, both decisions about actions and emotions (feelings) about consequence situations. The system is driven by the interaction between cognition and emotion. The self-learning algorithm updates a memory matrix \( W =\|w(a,s)\| \) such that in each iteration executes the following machine learning routine:
>
> *自学习是一种机器学习范式，于1982年与一种能够自我学习的神经网络一起被引入，该神经网络被称为交叉开关自适应阵列 (CAA) 。这是一种无需外部奖励和外部教师指导的学习方式。 CAA 的自学习算法采用交叉方式计算关于动作和关于后果情况的情感（情绪）决策。系统由认知和情感之间的相互作用驱动。自学习算法更新一个记忆矩阵 \( W =\|w(a,s)\| \) ，使得在每次迭代中执行以下机器学习流程：*
>
> - in situation \( s \) perform action \( a \)
>   - *在情况 \( s \) 下采取行动 \( a \)*
> - receive a consequence situation \( s' \)
>   - *面临后果 \( s' \)*
> - compute emotion of being in the consequence situation \( v(s') \)
>   - *计算处于后果情境中的情绪 \( v(s') \)*
> - update crossbar memory \( w'(a,s) = w(a,s) + v(s') \)
>   - *更新交叉开关的记忆 \( w'(a,s) = w(a,s) + v(s') \)*
>
> It is a system with only one input, situation, and only one output, action (or behavior) a. There is neither a separate reinforcement input nor an advice input from the environment. The backpropagated value (secondary reinforcement) is the emotion toward the consequence situation. The CAA exists in two environments, one is the behavioral environment where it behaves, and the other is the genetic environment, wherefrom it initially and only once receives initial emotions about situations to be encountered in the behavioral environment. After receiving the genome (species) vector from the genetic environment, the CAA learns a goal-seeking behavior, in an environment that contains both desirable and undesirable situations.
>
> *这是一个只有单一输入（情况）和单一输出（行动或行为） \( a \) 的系统。环境既没有独立的强化输入，也没有来自环境的建议输入。反向传播的价值（次级强化）是对后果情况的情绪。 CAA 存在于两个环境中，一个是行为环境， CAA 在其中表现，另一个是遗传环境， CAA 仅在一次且最初从中接收关于将在行为环境中遇到的情况的初始情绪。从遗传环境中接收基因（物种）向量后， CAA 学习一种寻求目标的行为，在一个包含既有吸引力又有排斥力的情况的环境中。*

## 模型

> A machine learning model is a type of mathematical model that, after being "trained" on a given dataset, can be used to make predictions or classifications on new data. During training, a learning algorithm iteratively adjusts the model's internal parameters to minimize errors in its predictions. By extension, the term "model" can refer to several levels of specificity, from a general class of models and their associated learning algorithms to a fully trained model with all its internal parameters tuned.
>
> *机器学习模型是一种数学模型，在对给定数据集进行“训练”后，可以用于对新数据进行预测或分类。在训练过程中，学习算法会逐次调整模型内部参数，以最小化其预测中的误差。因此，“模型”一词可以指代特定模型及其相关学习算法的多个层次，直至指代完全训练好的模型及其所有内部参数的调整。*
>
> Various types of models have been used and researched for machine learning systems, picking the best model for a task is called model selection.
>
> 机器学习系统中使用了各种类型的模型，为任务选择最佳模型称为模型选择。

### 人工神经网络 — Artificial Neural Network (ANN)

> Artificial neural networks (ANNs), or connectionist systems, are computing systems vaguely inspired by the biological neural networks that constitute animal brains. Such systems "learn" to perform tasks by considering examples, generally without being programmed with any task-specific rules.
>
> *人工神经网络 (ANNs) 或称连接主义系统，是一种受生物神经网络启发的计算系统，后者构成了动物大脑的功能。这种系统通常通过考虑示例来“学习”执行任务，通常无需按照特定任务的规则进行编程。*
>
> An ANN is a model based on a collection of connected units or nodes called "artificial neurons", which loosely model the neurons in a biological brain. Each connection, like the synapses in a biological brain, can transmit information, a "signal", from one artificial neuron to another. An artificial neuron that receives a signal can process it and then signal additional artificial neurons connected to it. In common ANN implementations, the signal at a connection between artificial neurons is a real number, and the output of each artificial neuron is computed by some non-linear function of the sum of its inputs. The connections between artificial neurons are called "edges". Artificial neurons and edges typically have a weight that adjusts as learning proceeds. The weight increases or decreases the strength of the signal at a connection. Artificial neurons may have a threshold such that the signal is only sent if the aggregate signal crosses that threshold. Typically, artificial neurons are aggregated into layers. Different layers may perform different kinds of transformations on their inputs. Signals travel from the first layer (the input layer) to the last layer (the output layer), possibly after traversing the layers multiple times.
>
> *ANN 是一种基于连接在一起的单元或节点（称为“人工神经元”）的模型，它大致模拟生物大脑中的神经元。每个连接（类似于生物大脑中的突触）都可以从一个人工神经元向另一个人工神经元传输信息，即“信号”。接收信号的人工神经元可以对信号进行处理，然后向与其连接的其他人工神经元发送信号。在常见的 ANN 实现中，人工神经元之间的连接之间的信号是一个实数，每个人工神经元的输出是其输入总和的某个非线性函数。人工神经元和连接之间的边缘通常有一个权重，随着学习的进行而调整。权重会增加或减少连接处信号的强度。人工神经元可能有一个阈值，只有当总信号超过该阈值时才会发送信号。通常，人工神经元会组合成不同的层。不同的层可能对其输入执行不同的变换。信号从第一层（输入层）传递到最后一层（输出层），可能需要在各层之间多次穿梭。*
>
> The original goal of the ANN approach was to solve problems in the same way that a human brain would. However, over time, attention moved to performing specific tasks, leading to deviations from biology. Artificial neural networks have been used on a variety of tasks, including computer vision, speech recognition, machine translation, social network filtering, playing board and video games and medical diagnosis.
>
> *ANN 方法的原始目标是像人脑一样解决问题。然而，随着时间的推移，人们的关注点转向执行特定的任务，导致偏离了生物学。人工智能神经网络已被应用于各种任务，包括计算机视觉、语音识别、机器翻译、社交网络过滤、棋盘和视频游戏以及医学诊断。*
>
> Deep learning consists of multiple hidden layers in an artificial neural network. This approach tries to model the way the human brain processes light and sound into vision and hearing. Some successful applications of deep learning are computer vision and speech recognition.
>
> *深度学习是一种在人工神经网络中包含多个隐藏层的方法。这种方法试图模拟人类大脑将光和声音转换为视觉和听觉的方式。深度学习的一些成功应用包括计算机视觉和语音识别。*

### 决策树 — Decision Tree

> Decision tree learning uses a decision tree as a predictive model to go from observations about an item (represented in the branches) to conclusions about the item's target value (represented in the leaves). It is one of the predictive modeling approaches used in statistics, data mining, and machine learning. Tree models where the target variable can take a discrete set of values are called classification trees; in these tree structures, leaves represent class labels, and branches represent conjunctions of features that lead to those class labels. Decision trees where the target variable can take continuous values (typically real numbers) are called regression trees. In decision analysis, a decision tree can be used to visually and explicitly represent decisions and decision making. In data mining, a decision tree describes data, but the resulting classification tree can be an input for decision-making.
>
> *决策树学习使用决策树作为预测模型，从关于某个项目（以树枝表示）的观察结果出发，推断出该项目的目标值（以树叶表示）。它是统计学、数据挖掘和机器学习中使用的预测建模方法之一。目标变量可以取离散集合值的树模型称为分类树；在这些树结构中，叶子代表类标签，树枝代表导致这些类标签的特征的交集。目标变量可以取连续值（通常是实数）的决策树称为回归树。在决策分析中，决策树可以用于可视化和明确地表示决策和决策制定。在数据挖掘中，决策树描述数据，但生成的分类树可以作为决策的输入。*

### 支持向量机 — Support-Vector Machine (SVM)

> Support-vector machines (SVMs), also known as support-vector networks, are a set of related supervised learning methods used for classification and regression. Given a set of training examples, each marked as belonging to one of two categories, an SVM training algorithm builds a model that predicts whether a new example falls into one category. An SVM training algorithm is a non-probabilistic, binary, linear classifier, although methods such as Platt scaling exist to use SVM in a probabilistic classification setting. In addition to performing linear classification, SVMs can efficiently perform a non-linear classification using what is called the kernel trick, implicitly mapping their inputs into high-dimensional feature spaces.
>
> *支持向量机 (SVM) 又称为支持向量网络，是一种用于分类和回归的相关监督学习方法的集合。给定一组带有标记的训练示例，每个示例都被标记为属于两个类别中的一个，SVM 训练算法会构建一个模型，用于预测新示例属于哪个类别。SVM训练算法是一种非概率的二元线性分类器，尽管存在诸如 Platt 缩放之类的方法，可以将 SVM 应用于概率分类环境中。除了进行线性分类外， SVM 还可以高效地使用所谓的“核技巧”进行非线性分类，将输入数据隐式映射到高维特征空间。*

### 回归分析 — Regression Analysis

> Regression analysis encompasses a large variety of statistical methods to estimate the relationship between input variables and their associated features. Its most common form is linear regression, where a single line is drawn to best fit the given data according to a mathematical criterion such as ordinary least squares. The latter is often extended by regularization methods to mitigate overfitting and bias, as in ridge regression. When dealing with non-linear problems, go-to models include polynomial regression (for example, used for trendline fitting in Microsoft Excel), logistic regression (often used in statistical classification) or even kernel regression, which introduces non-linearity by taking advantage of the kernel trick to implicitly map input variables to higher-dimensional space.
>
> *回归分析是一种包含多种统计方法的工具，用于估计输入变量与其相关特征之间的关系。其最常见的形式是线性回归，即根据诸如普通最小二乘法等数学准则，绘制一条直线来最佳拟合给定的数据。后者通常通过正则化方法进行扩展，以减少过拟合和偏差，例如岭回归。当处理非线性问题时，常用的模型包括多项式回归（例如，用于在 Microsoft Excel 中绘制趋势线）、逻辑回归（通常用于统计分类），甚至核回归，通过利用核技巧将输入变量隐式映射到更高维空间来引入非线性。*

### Bayes 网络 — Bayesian Network

> A Bayesian network, belief network, or directed acyclic graphical model is a probabilistic graphical model that represents a set of random variables and their conditional independence with a directed acyclic graph (DAG). For example, a Bayesian network could represent the probabilistic relationships between diseases and symptoms. Given symptoms, the network can be used to compute the probabilities of the presence of various diseases. Efficient algorithms exist that perform inference and learning. Bayesian networks that model sequences of variables, like speech signals or protein sequences, are called dynamic Bayesian networks. Generalizations of Bayesian networks that can represent and solve decision problems under uncertainty are called influence diagrams.
>
> *Bayes 网络（也称为信念网络或有向无环图模型）是一种概率图模型，它使用有向无环图 (DAG) 来表示一组随机变量及其条件独立性。例如， Bayes 网络可以表示疾病和症状之间的概率关系。给定症状，该网络可以计算各种疾病存在的概率。存在高效的算法可以进行推理和学习。表示和解决不确定性条件下决策问题的 Bayes 网络的一般化形式称为影响图。*

### Gauss 过程 — Gaussian Process

> A Gaussian process is a stochastic process in which every finite collection of the random variables in the process has a multivariate normal distribution, and it relies on a pre-defined covariance function, or kernel, that models how pairs of points relate to each other depending on their locations.
>
> *Gauss 过程是一种随机过程，其中过程的任意有限集合的随机变量都有多维正态分布。它依赖于一个预先定义的协方差函数（或核函数），该函数根据点的位置模型点对之间的关系。*
> Given a set of observed points, or input–output examples, the distribution of the (unobserved) output of a new point as function of its input data can be directly computed by looking like the observed points and the covariances between those points and the new, unobserved point.
>
> *给定一组观察点或输入-输出示例，可以通过观察这些点及其与新、未观察点之间的协方差来直接计算新点输出（即未观察点的输出）的分布。*
>
> Gaussian processes are popular surrogate models in Bayesian optimization used to do hyperparameter optimization.
>
> *Gauss 过程是 Bayes 优化中常用的超参数优化替代模型。*

### 遗传算法 — Genetic Algorithm

> A genetic algorithm (GA) is a search algorithm and heuristic technique that mimics the process of natural selection, using methods such as mutation and crossover to generate new genotypes in the hope of finding good solutions to a given problem. In machine learning, genetic algorithms were used in the 1980s and 1990s. Conversely, machine learning techniques have been used to improve the performance of genetic and evolutionary algorithms.
>
> *遗传算法 (GA) 是一种仿照自然选择过程的搜索算法和启发式技术，它使用突变和交叉等方法来生成新的基因型，以期找到给定问题的良好解决方案。在机器学习领域，遗传算法在 20 世纪 80 年代和 90 年代得到了应用。相反，机器学习技术已被用于改进遗传和进化算法的性能。*

### 信念函数 — Belief Function

> The theory of belief functions, also referred to as evidence theory or Dempster–Shafer theory, is a general framework for reasoning with uncertainty, with understood connections to other frameworks such as probability, possibility and imprecise probability theories. These theoretical frameworks can be thought of as a kind of learner and have some analogous properties of how evidence is combined (e.g., Dempster's rule of combination), just like how in a pmf-based Bayesian approach would combine probabilities. However, there are many caveats to these beliefs functions when compared to Bayesian approaches in order to incorporate ignorance and uncertainty quantification. These belief function approaches that are implemented within the machine learning domain typically leverage a fusion approach of various ensemble methods to better handle the learner's decision boundary, low samples, and ambiguous class issues that standard machine learning approach tend to have difficulty resolving. However, the computational complexity of these algorithms are dependent on the number of propositions (classes), and can lead to a much higher computation time when compared to other machine learning approaches.
>
> *信念函数理论，又称为证据理论或 Dempster–Shafer 理论，是一种处理不确定性的通用框架，与概率、可能性和不精确概率理论等其他框架存在联系。这些理论框架可以被看作是一种学习器，具有将证据组合（例如， Dempster 组合规则）的类似特性，就像在基于 pmf 的 Bayes 方法中会将概率进行组合一样。然而，与 Bayes 方法相比，信念函数方法在纳入无知和不确定性量化时存在许多局限性。在机器学习领域中实现的这些信念函数方法通常采用各种集成方法的融合策略，以更好地处理学习器的决策边界、低样本量和模糊类问题，而这些问题通常是传统机器学习方法难以解决的。然而，这些算法的计算复杂度取决于命题（类）的数量，与其他机器学习方法相比，可能会导致更高的计算时间。*

### 训练模型

> Typically, machine learning models require a high quantity of reliable data to perform accurate predictions. When training a machine learning model, machine learning engineers need to target and collect a large and representative sample of data. Data from the training set can be as varied as a corpus of text, a collection of images, sensor data, and data collected from individual users of a service. Overfitting is something to watch out for when training a machine learning model. Trained models derived from biased or non-evaluated data can result in skewed or undesired predictions. Biased models may result in detrimental outcomes, thereby furthering the negative impacts on society or objectives. Algorithmic bias is a potential result of data not being fully prepared for training. Machine learning ethics is becoming a field of study and notably, becoming integrated within machine learning engineering teams.
>
> *通常来说，机器学习模型需要大量的可靠数据来进行准确的预测。在训练机器学习模型时，机器学习工程师需要针对并收集大量具有代表性的数据样本。训练集的数据可以是多种多样的，比如文本语料库、图像集合、传感器数据，以及来自服务中单个用户的数据。在训练机器学习模型时，需要警惕过度拟合的问题。由带有偏见或未经评估的数据训练得到的模型可能会导致预测偏斜或不可接受。带有偏见的模型可能会导致不利后果，从而进一步加剧对社会或目标的负面影响。算法偏见可能是由于数据在训练过程中没有得到充分准备而产生的潜在结果。机器学习伦理学正在成为一门学科，并且越来越受到机器学习工程团队的重视。*

### 联邦学习

> Federated learning is an adapted form of distributed artificial intelligence to training machine learning models that decentralizes the training process, allowing for users' privacy to be maintained by not needing to send their data to a centralized server. This also increases efficiency by decentralizing the training process to many devices. For example, Gboard uses federated machine learning to train search query prediction models on users' mobile phones without having to send individual searches back to Google.
>
> *联邦学习是一种适应性分布式人工智能，用于在不将用户数据发送到集中式服务器的情况下训练机器学习模型，从而保护用户的隐私。此外，通过将训练过程分散到多个设备上，还可以提高效率。例如， Gboard 使用联邦机器学习在用户的移动设备上训练搜索查询预测模型，而不需要将每个搜索结果发送回谷歌。*