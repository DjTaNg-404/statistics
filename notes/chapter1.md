# 大数定律及中心极限定律

大数定律是叙述随机变量序列的前一些项的算术平均值在某种条件下收敛到这些项的均值的算术平均值；中心极限定理是确定在什么条件下，大量随机变量之和的分布逼近与正态分布。

## 大数定律

**弱大数定理（辛钦大数定理）**：设$X_1,X_2,\dots$是相互独立，服从同一分布的随机变量序列，且具有数学期望$E(X_k)=\mu(k=1,2,\dots)$。作前$n$个变量的算术平均$\frac{1}{n}\sum_{k=1}^{n}X_k$，则对于任意$\varepsilon>0$，有
$$
\lim_{n\to\infty}P\{|\frac{1}{n}\sum_{k=1}^{n}X_k-\mu|<\varepsilon\}=1
$$
注意：

1. 相互独立是指对于任意的$n>1,X_1,X_2,\dots,X_n$是相互独立的。
2. 为什么要特地有条件*具有数学期望*，因为数学期望（均值）可能会不存在，例如对于离散型随机变量中级数$\sum{|x_i|p_i}$不收敛时，以及对于连续型随机变量中密度函数$f(x)$在无限区间上取值，且广义积分$\int_{-\infty}^{\infty}|x|f(x)\mathrm{d}x$​不绝对收敛时。经典例子为柯西分布（Cauchy distribution）
3. 辛钦大数定理的证明需要运用到切比雪夫不等式

辛钦大数定理想要阐述的是，对于独立同分布且具有均值$\mu$的随机变量$X_1,X_2,\dots,X_n$，当$n$很大时他们的算术平均值$\frac{1}{n}\sum_{k=1}^{n}X_k$很有可能接近于$\mu$，即期望值。

现引入依概率收敛的定义：

设$Y_1,Y_2,\dots,Y_n,\dots$是一个随机变量序列，$a$是一个常数。若对于任意正数$\varepsilon$，有
$$
\lim_{n\to\infty}P\{|Y_n-a|<\varepsilon\}=1
$$
则称序列$Y_1,Y_2,\dots,Y_n,\dots$**依概率收敛于$a$**，即为$Y_n\xrightarrow{\text{P}}a$。

这样，辛钦大数定理又可以叙述为：

**弱大数定理（辛钦大数定理）**：设$X_1,X_2,\dots,X_n,\dots$相互独立，服从同一分布的随机变量序列，且具有数学期望$E(X_k)=\mu(k=1,2,\dots)$。则序列$\bar{X}=\frac{1}{n}\sum_{k=1}^{n}X_k$依概率收敛于$\mu$，即$\bar{X}\xrightarrow{\text{P}}\mu$。

下面是辛钦大数定理的重要推论。

**伯努利大数定理**：设$f_A$是$n$次独立重复试验中事件$A$发生的次数，$p$是事件$A$在每次试验中发生的概率，则对于任意正数$\varepsilon>0$，有
$$
\lim_{n\to\infty}P\{|\frac{f_A}{n}-p|<\varepsilon\}=1
$$
或
$$
\lim_{n\to\infty}P\{|\frac{f_A}{n}-p|\ge\varepsilon\}=0
$$
伯努利大数定理的结果表明，对于任意$\varepsilon>0$，只要重复独立试验的次数$n$充分大，事件$\{|\frac{f_A}{n}-p|\ge\varepsilon\}$是一个小概率事件，由实际推断原理知，这一事件实际上几乎是不发生的。由实际推断原理，在实际应用中，当实验次数很大时，便可以用事件的频率来代替事件的概率。

实际推断原理：概率很小的事件在一次试验中实际上几乎是不发生的。

## 中心极限定理

**定理一（独立同分布的中心极限定理）**：设随机变量$X_1,X_2,\dots,X_n,\dots$相互独立，服从同一分布，且具有数学期望和方差：$E(X_k)=\mu,D(X_k)=\sigma^2>0(k=1,2,\dots)$，则随机变量之和$\sum_{k=1}^{n}X_k$的标准化变量
$$
Y_n=\frac{\sum_{k=1}^{n}{X_k}-E(\sum_{k=1}^{n}{X_k})}{\sqrt{D(\sum_{k=1}^{n}{X_k})}}=\frac{\sum_{k=1}^{n}{X_k}-n\mu}{\sqrt{n}\sigma}
$$
的分布函数$F_n(x)$对于任意$x$满足
$$
\lim_{n\to\infty}F_n(x)=\lim_{n\to\infty}P\{\frac{\sum_{k=1}^{n}{X_k}-n\mu}{\sqrt{n}\sigma}\le x\}=\int_{-\infty}^{x}\frac{1}{\sqrt{2\pi}}e^{-\frac{t^2}{2}}\mathrm{d}t=\phi(x)
$$
​	这就是说，均值为$\mu$，方差为$\sigma^2>0$的独立同分布的随机变量$X_1,X_2,\dots,X_n$之和$\sum_{k=1}^{n}{X_k}$的标准化变量，当$n$充分大时，有
$$
\frac{\sum_{k=1}^{n}{X_k}-n\mu}{\sqrt{n}\sigma}\sim N(0,1)
$$
将左端改写成$\frac{\frac{1}{n}\sum_{k=1}^{n}{X_k}-n\mu}{\sigma/\sqrt{n}}=\frac{\bar{X}-\mu}{\sigma/\sqrt{n}}$，这样上述结果可写成：当$n$充分大时，
$$
\frac{\bar{X}-\mu}{\sigma/\sqrt{n}}\sim N(0,1)\quad 或\quad \bar{X}\sim N(\mu,\sigma^2/n)
$$
**定理二（李雅普诺夫（Lyapunov）定理）**：设随机变量$X_1,X_2,\dots,X_n,\dots$相互独立，它们具有数学期望和方差$E(X_k)=\mu_k,\quad D(X_k)=\sigma_k^2>0,k=1,2,\dots$，记$B_n^2=\sum_{k=1}^{n}\sigma_k^2$，做存在正整数$\delta$，使得当$n\to\infty$时，
$$
\frac{1}{B_n^{2+\delta}}\sum_{k=1}^{n}E\{|X_k-\mu_k|^{2+\delta}\}\to0
$$
则随机变量之和$\sum_{k=1}^{n}X_k$的标准化变量
$$
Z_n=\frac{\sum_{k=1}^{n}{X_k}-E(\sum_{k=1}^{n}{X_k})}{\sqrt{D(\sum_{k=1}^{n}{X_k})}}=\frac{\sum_{k=1}^{n}{X_k}-\sum_{k=1}^{n}\mu_k}{B_n}
$$
的分布函数$F_n(x)$对于任意$x$满足
$$
\lim_{n\to\infty}F_n(x)=\lim_{n\to\infty}P\{\frac{\sum_{k=1}^{n}{X_k}-\sum_{k=1}^{n}\mu_k}{B_n}\le x\}=\int_{-\infty}^{x}\frac{1}{\sqrt{2\pi}}e^{-\frac{t^2}{2}}\mathrm{d}t=\phi(x)
$$
​	定理二表明随机变量$Z_n$当$n$很大时，近似地服从正态分布$N(0,1)$。

**定理三（棣莫弗-拉普拉斯（De Moivre-Laplace）定理）**：设随机变量$\eta_n(n=1,2,\dots)$服从参数为$n$，$p(0<p<1)$的二项分布，则对于任意$x$，有
$$
\lim_{n\to\infty}P\{\frac{\eta_n-np}{\sqrt{np(1-p)}}\le x\}=\int_{-\infty}^{x}\frac{1}{\sqrt{2\pi}}e^{-\frac{t^2}{2}}\mathrm{d}t=\phi(x)
$$
