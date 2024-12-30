# 样本及抽样分布

数理统计的内容包括：如何收集、整理数据资料；如何对所得的数据资料进行分析、研究，从而对所研究的对象的性质、特点作出推断。在数理统计中，我们研究的随机变量，它的分布是未知、或者是完全不知道的，人们是通过对所研究的随机变量进行重复独立的观察，得到许多观察值，对这些数据进行分析，从而对所研究的随机变量的分布作出种种推断。

## 随机样本

**总体**：试验的全部可能的观察值。

**个体**：每一个可能观察值。

总体的**容量**：总体中所包含的个体的个数，容量为有限的称为**有限总体**，容量为无限的称为**无限总体**。

在数理统计中，人们都是通过从总体中抽取一部分个体，根据获得的数据来对总体分布作出推断的。被抽出的部分个体叫做总体的一个**样本**。

设$X$是具有分布函数$F$的随机变量，若$X_1,X_2,\dots,X_n$是具有同一分布函数$F$的、相互独立的随机变量，则称$X_1,X_2,\dots,X_n$为从分布函数$F$（或总体$F$，或总体$X$）得到的**容量为$n$的简单随机样本**，简称**样本**，它们的观察值$x_1,x_2,\dots,x_n$称为**样本值**，又称为$X$的$n$个**独立的观察值**。

## 抽样分布

样本是进行统计推断的依据。在应用时，往往不是直接使用样本本身，而是针对不同的问题构造样本的适当函数，利用这些样本的函数进行统计推断。

设$X_1,X_2,\dots,X_n$是来自总体$X$的一个样本，$g(X_1,X_2,\dots,X_n)$是$X_1,X_2,\dots,X_n$的函数，若$g$中不含未知参数，则称$g(X_1,X_2,\dots,X_n)$是一**统计量**。

常用的统计量有：

设$X_1,X_2,\dots,X_n$是来自总体$X$的一个样本，$x_1,x_2,\dots,x_n$是这一样笨的观察值。定义

**样本平均值** 
$$
\bar{X}=\frac{1}{n}\sum_{i=1}^{n}X_i
$$
**样本方差**
$$
S^2=\frac{1}{n-1}\sum_{i=1}^{n}{(X_i-\bar{X})^2}=\frac{1}{n-1}(\sum_{i=1}^{n}X_i^2-n\bar{X}^2)
$$
**样本标准差**
$$
S=\sqrt{S^2}=\sqrt{\frac{1}{n-1}\sum_{i=1}^{n}{(X_i-\bar{X})^2}}
$$
**样本$k$阶（原点）矩**
$$
A_k=\frac{1}{n}\sum_{i=1}^nX_i^k,\  k=1,2,\dots
$$
**样本$k$阶中心矩**
$$
B_k=\frac{1}{n}\sum_{i=1}^{n}(X_i-\bar{X})^k,\  k=2,3,\dots
$$
**样本变异系数**（反映随机变量的波动性大小）
$$
C_v=\frac{S}{|\bar{X}|}
$$
设$X_1,X_2,\dots,X_n$是总体$F$的一个样本，用$S(x),-\infty<x<\infty$表示$X_1,X_2,\dots,X_n$中不大于$x$的随机变量的个数，定义**经验分布函数$F_n(x)$**为
$$
F_n(x)=\frac{1}{n}S(x),\  -\infty<x<\infty
$$
统计量的分布称为**抽样分布**

## 常用统计量的分布

以下介绍一些常见的统计量的分布，这些分布提供了统计推断的基础，使得我们可以从有限的数据中做出关于整个总体的结论。

### $\chi^2$分布

​	设$X_1,X_2,\dots,X_n$是来自总体$N(0,1)$的样本，则称统计量
$$
\chi^2=X_1^2+X_2^2+\dots+X_n^2
$$
服从自由度为$n$的**$\chi^2$分布**，记为$\chi^2\sim\chi^2(n)$。

**$\chi^2$分布的可加性**	设$\chi^2_1\sim\chi^2(n_1)$，$\chi_2^2\sim\chi^2(n_2)$，并且$\chi^2_1,\chi_2^2$相互独立，则有
$$
\chi^2_1+\chi_2^2\sim\chi^2(n_1+n_2)
$$
**$\chi^2$分布的数学期望和方差**	若$\chi^2\sim\chi^2(n)$，则有
$$
E(\chi^2)=n,\quad D(\chi^2)=2n
$$
**$\chi^2$分布的上分位点**	对于给定的正数$a,0<a<1$，满足条件
$$
P\{\chi^2>\chi^2_a(n)\}=\int_{\chi_a^2(n)}^\infty{f(y)\mathrm{d}y}=a
$$

### $t$分布

​	设$X\sim N(0,1)$，$Y\sim\chi^2(n)$，且$X,Y$相互独立，则称随机变量
$$
t=\frac{X}{\sqrt{Y/n}}
$$
服从自由度位$n$的**$t$分布**。记为$t\sim t(n)$。$t$分布又称为**学生氏(Student)分布**。

**$t$分布的上分位点**	对于给定的正数$a,0<a<1$，满足条件
$$
P\{t>t_a(n)\}=\int_{t_a(n)}^\infty{h(t)\mathrm{d}t}=a
$$

### $F$分布

​	设$U\sim \chi^2(n_1)$，$V\sim\chi^2(n_2)$，且$U,V$相互独立，则称随机变量
$$
F=\frac{U/n_1}{V/n_2}
$$
服从自由度为$(n_1,n_2)$的**$F$分布**，记为$F\sim F(n_1,n_2)$。

**$F$分布的上分位点**	对于给定的正数$a,0<a<1$，满足条件
$$
P\{F>F_a(n_1,n_2)\}=\int_{F_a(n_1,n_2)}^\infty\psi(y)\mathrm{d}y=a
$$