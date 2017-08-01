---
title: Python Machine Learning Chapter 2 note
date: 2016-08-09 16:02:42
math: true
tags: Machine Learning, Artificial Neurons, perceptron,ADAptive LInear NEuron(Adaline)

---
perceptron
---
perceptron (感知机) 是一个线性二分类器，基于 MCP neuron，主要功能是将多个输入转换成一个输出。模型如下 ($x$ 为输入向量, $w$ 为权重向量, $y$ 为激活函数的值, $\phi(y)$ 为unit step)：
$$
w=
\left[
\begin{array}{r}
w_1 \\\\ 
w_2 \\\\ 
w_3
\end{array}
\right]
,
x=
\left[
\begin{array}{r}
x_1 \\\\ 
x_2 \\\\ 
x_3
\end{array}
\right]
$$
$$
y = w^Tx
$$
$$
\phi(y) = 
\begin{cases}
1, & y \geq 0\\\\
-1, & y < 0
\end{cases}
$$

perceptron 算法的核心是，找到误分类的点，然后用误分类的点去更新参数向量（超平面的法向量）每次更新的幅度和学习速率有关，所以我们$\delta w$的值我们定义为$\alpha (y^{(i)} - \phi(x^{(i)}w))x^{(i)}$这样，如果分类正确则$\delta w$的值为0，只有误分类的点会有贡献。这个模型非常简洁明了，但是缺陷也非常明显，由于`activation function`会直接经过`unit step`变成离散量，没有好的办法通过数学的角度进行优化，只能遍历通过遍历整个数据集合来更新，直到全部分类正确（如果线性可分）

ADAptive LInear NEuron(Adaline)
---
Adaline 将`unit step` 移动到了`predict` 过程中,并且引入了`Sum of Squared Errors (SSE)`来评估假设和真实情况的的误差，这样的好处是误差不再是离散的了，而变成一个连续的过程了，如此我们就可以通过倒数的相关知识来求得使得`SSE`最小的`w`
