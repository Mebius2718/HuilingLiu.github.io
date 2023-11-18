---
title: "第三章 随机场"
subtitle: ""
date: 2023-7-16T20:00:00+08:00
author: "Mebius"
authorLink: ""
hiddenFromHomePage: True
draft: True
---

线性理论描述了宇宙中结构的增长，具体的，他告诉我们不同波矢对应的结构的增长相互独立。那么如何验证现有宇宙学模型和线性理论？一个自然的想法是获得宇宙中任意位置出的密度涨落，再与我们的模型进行对比。这种方法需要超算来进行 reconstruction 数值模拟，且其中包含了许多可调参数和系统误差，这并不是验证理论的最佳方式。另一种方式是研究宇宙中物质涨落的种种统计性质。做一个类比，如果我们想研究一团热气体的宏观性质，我们并不需要得知气体中每个分子的位置和速度，只需要知道它统计意义上的速度分布函数即可。

综上所述，为了验证现有的宇宙学模型和线性理论，人们发展了一系列统计量来描述宇宙密度和分布的统计性质。同时发展一套方法用以将观测数据和理论模型做比对，这里面涉及到一系列误差的处理。本章将简单介绍这些内容。

## 3.1 两点相关函数与功率谱

### 3.1.1 两点相关函数

我们将宇宙分为 n 个区域，这些区域的坐标为 ${\vec{x}_{1},\vec{x}_{2}},\dots,\vec{x}_{n}$，每个区域存在密度的涨落 $\delta_{1},\delta_{2},\dots,\delta_{n}$，并用概率密度函数 $p(\delta_{1},\delta_{2},\dots,\delta_{n})$ 描述产生某种密度涨落的概率分布。有了概率密度分布后，我们还可以计算这些随机变量的**矩**，以获得一些更直观的感受
$$
\langle \delta_{1}^{l_{1}}\delta_{2}^{l_{2}}\dots\delta_{n}^{l_{n}} \rangle=\int \delta_{1}^{l_{1}}\delta_{2}^{l_{2}}\dots\delta_{n}^{l_{n}} p(\delta_{1},\delta_{2},\dots,\delta_{n}) \, d\delta_{1}  d\delta_{2}\dots d\delta_{n} 
$$
显而易见地
+ $l_i=0, i=1,2,\dots,n$，$\langle 1 \rangle=1$
+ $\langle \delta_{1} \rangle=\langle \delta_{2} \rangle=\dots=\langle \delta_{n} \rangle=0$，这是 over density 的定义和宇宙学原理所致

由于宇宙学原理，我们还要定义密度涨落的方差
$$
\sigma^2=\langle \delta_{i}^2 \rangle ,\quad i=1,2,\dots,n
$$
以及两点相关函数
$$
\xi(r)= \langle\delta_{i}\delta_{j}\rangle=\int \delta_{1}\delta_{2} ~p(\delta) \, d\delta \quad i\neq j
$$
于是有
$$
\sigma^2=\xi(0)
$$

### 3.1.2 功率谱

第三章中，我们发现傅里叶空间中的密度涨落相互独立，这是一个非常好的性质，这暗示着我们也在傅里叶空间考察物质密度涨落的性质，考察在傅里叶空间中的两点相关函数
$$
\begin{align}
\xi_{k}(\vec{x})&=\langle \delta_{\vec{k}_{1}}\delta_{\vec{k}_{2}} \rangle  \\
&=\frac{1}{V_{u}^2}\left\langle  
\int \delta_{1}e^{-i\vec{k}_{1} \cdot \vec{x}_{1}} \, d\vec{x}_{1}   
\int \delta_{2}e^{-i\vec{k}_{2} \cdot \vec{x}_{1}} \, d\vec{x}_{2}   
\right\rangle  \\
&=\frac{1}{V_{u}^2}\iint \langle \delta_{1}\delta_{2} \rangle\exp(-i\vec{k}_{1} \cdot \vec{x}_{1}-i\vec{k}_{2} \cdot \vec{x}_{2})d \vec{x}_{1}d\vec{x}_{2} \\
&=\frac{1}{V_{u}^2}\int\xi(\vec{x})\exp(-i\vec{k}_{2}\cdot\vec{x})d\vec{x}\cdot \int \exp(i(\vec{k}_{1}+\vec{k}_{2})\cdot x_{1}) \, d\vec{x}_{1} \\
\end{align}
$$
考虑到傅里叶变换的性质，我们得到了
$$
\xi_{\vec{k}}(x)=\left\{\begin{align}
&0  &&\vec{k}_{1}+\vec{k}_{2}\neq 0 \\
&\frac{1}{V_{u}}\int\xi(\vec{x})\exp(-i\vec{k}\cdot\vec{x})d\vec{x} &&\vec{k}=-\vec{k}_{1}=\vec{k}_{2}
\end{align}\right.
$$
其揭示了两点相关函数和功率谱的关系，我们定义**功率谱**为
$$
P(\vec{k})=\int \xi(\vec{x})\exp(-i\vec{k}\cdot \vec{x}) \, d^3\vec{x}=V_{u}\langle \delta_{\vec{k}}\delta_{-\vec{k}} \rangle 
$$
这表明**功率谱和两点相关函数通过傅里叶变换联系在一起**，需要注意的是，功率谱的大小和所在宇宙的大小也有关系。

宇宙是各向同性的，两点相关函数和功率谱都只与 r 或 k 的大小有关，与其方向无关，所以我们在球坐标下表示它们会更方便一些，于是有
$$
P(k)=\int \xi(r) \exp(-ikr\cos \theta)r^2\sin \theta\, d \theta d\phi dr=4\pi\int \xi(r) \frac{\sin(kr)}{kr} r^2\, dr 
$$
同时有逆变换
$$
\xi(r)=\frac{1}{(2\pi)^3}\int P(k)\exp(i\vec{k}\cdot \vec{r}) \, d^3\vec{k} =\frac{1}{2\pi^2}\int P(k) \frac{\sin(kr)}{kr} k^2\, dk=\int \Delta(k) \frac{\sin(kr)}{kr}\, \frac{dk}{k}
$$
这里定义了一个**无量纲的功率谱**
$$
\Delta(k)=\frac{1}{2\pi^2}P(k)k^3
$$
他比功率谱好用一些，因为他不随着宇宙大小所影响。

## 3.2 高斯随机场

上一节中所讨论的两点相关函数和功率谱所包含的信息太少了，即便我们能精确测量它们，也无法得知宇宙的随机场是什么。我们需要引入更多假设来确定宇宙中的初始密度场的统计性质。从宇宙学原理出发——宇宙是各向同性和均匀的，我们认为宇宙的初始密度场是高斯随机场。

### 3.2.1 高斯随机场

定义高斯随机场（Gaussian Random Fields）：对随机场 $\delta(\vec{x})$ ，如果对于任意 n，任意 n 个点上的密度涨落 $(\delta_{1},\delta_{2},\dots,\delta_{n})$ 的联合概率密度函数为
$$
p(\delta)=\frac{\exp(-Q)}{[(2\pi)^n\det(\mathcal{U})]^{\frac{1}{2}}}
$$
其中
$$
\mathcal{U}_{ij}=\langle \delta_{i}\delta _{j} \rangle,\quad Q=\frac{1}{2}\sum_{i,j}\delta _{i}\delta_{j}(\mathcal{U}^{-1})_{ij}
$$
则称随机场 $\delta(\vec{x})$ 为高斯密度场。

>以 n=1 为例，此时 $$
p(\delta)=\frac{1}{\sqrt{ 2\pi\sigma }}\exp\left( -\frac{\delta^2}{2\sigma^2}\right), \quad \mathcal{U}=\langle \delta^2 \rangle=\sigma^2 ,\quad Q=\frac{\delta^2}{2\sigma^2}$$这与一维正太分布一致。对于 n 阶高斯分布来说，U 就是这些独立变量的协方差矩阵，这里就不作进一步的验证了。

我们在傅立叶空间中考察这个问题。不妨令
$$
\delta_\vec{k}=A_\vec{k}+iB_\vec{k}
$$
由于实函数的傅里叶展开有
$$
\delta_{\vec{k}}=\int \delta(\vec{x},t) \exp(-i\vec{k}\cdot \vec{x})\, dx=\bar{\delta}_{-\vec{k}} 
$$
即 $\delta_{\vec{k}}, \delta_{{-\vec{k}}}$ 互为复共轭，故有
$$
A_\vec{k}=A_{-\vec{k}} \quad B_\vec{k}=-B_{-\vec{k}}
$$
所以我们只用考虑上半平面的 $\vec{k}$，则有
$$
\langle A_\vec{k}A_\vec{k'} \rangle=\langle B_\vec{k}B_\vec{k'} \rangle =\left\{\begin{align}
&\frac{1}{2V_u}P(k) && \vec{k}=\vec{k}' \\
&0 && else
\end{align}\right.
$$
同时
$$
\langle A_\vec{k}B_\vec{k'} \rangle=0 
$$
所以一个傅立叶空间的高斯随机场是**互相独立**的，且概率密度函数的性质只跟功率谱有关。为了方便，我们将概率密度函数用傅立叶空间中的极坐标写为
$$
p(|\delta_k|,\varphi_k)=\frac{V_u}{\pi P(k)}\exp\left( -\frac{|\delta_k|^2V_u}{P(k)} \right)|\delta_k|d|\delta_k|d\varphi_k
$$ 
> 这里需要证明傅立叶变换后仍为高斯分布。王老师似乎没有意识到这一点。

我们回顾第三章的内容：傅里叶空间中的密度涨落相互独立，这里高斯场在傅里叶空间相互独立倒也不足为奇了。**总而言之，对于傅里叶空间中不同的 $\vec{k}$ 对应的密度涨落的高斯场相互独立**，我们只需要知道它们的方差，便能获得它的所有信息。这也说明，**功率谱便能表征整个高斯随机场的分布了！**

为什么宇宙的初始密度场是高斯随机场？

+ **暴涨模型的预言**：高斯微扰场是由暴涨期间的量子涨落自然产生的。由于高斯场在线性变换前后保持高斯分布，因此暴胀模型的一般预测是线性状态中的 $\delta(\vec{x})$ 遵循高斯统计。
+ **中心极限定理**：大量同分布的独立变量之和的分布逼近高斯分布。初始密度扰动场 $\delta(\vec{x})$ 可以写作傅里叶空间中密度涨落的傅里叶变换，只要傅里叶空间中的密度涨落场的相位彼此独立，中心极限定理就保证高斯分布。
+ **观测事实**：目前没有令人信服的观测证据表明密度场是非高斯的

### 3.2.2 功率谱的形状

傅里叶空间中，不同波矢的高斯随机场相互独立，所以功率谱 P(k) 给出密度场的全部统计性质。通过暴涨理论，人们给出
$$
P_{i}(k)\propto k^n, \quad n\approx 1
$$
同时我们认为宇宙的密度涨落按照线性理论演化，则可将不同时间的功率谱写为
$$
P(a,k)\propto D^2(a)\langle |\delta_{k}| \rangle^2 T^2(k)\propto 
D^2(a)T^2(k)P_{i}(k)
$$
其中 T(k) 为线性转移函数，他刻画了
$$
T(k)=\frac{\delta(k,t)}{\delta(k,t_{i})} \frac{\delta(0,t_{i})}{\delta(0,t)}
$$
之所以线性转移函数只与 k 有关，是因为线性理论中密度涨落正比于尺度因子
$$
\delta(k,t)=\delta(k,0)D(t)
$$
则有 
$$
T(k)=\frac{\delta(k,t)}{\delta(k,t_{i})} \frac{\delta(0,t_{i})}{\delta(0,t)}
=\frac{\delta(k,t_{0})}{\delta(k,t_{i})} \frac{\delta(0,t_{i})}{\delta(0,t_{0})}
$$
式中包含了宇宙保障结束的时刻 $t_{i}$，现在的时刻 $t_{0}$，以及波矢 k，所以线性转移函数与不随时刻 t 变化。


除了通过理论计算得到功率谱之外，另一种更直接的方法便是建立功率谱与实空间中重子物质的联系，进而通过观测得到它。例如前文中提到的宇宙学参数 $\sigma_{8}$

## 3.3 观测功率谱

**我们可以将估测中的星系视为空间中的粒子点集，并认为这些粒子数密度代表了宇宙中物质在该处的密度大小**。同时，我们用随机放置的半径为 R 的球体来采样，得到球体内部星系数量的方差。我们写出这个方差的表达式
$$
\sigma_{R}^2 =\frac{1}{M}\sum_{i=1}^M\left( \frac{n_i}{\bar{n}}-1\right)^2
$$
其中 M 是采样次数，n 是球体中星系的数密度，显然 n 是观测中容易得到的。

为了将该方差与功率谱联系，我们引入窗口函数（top hat windows function）
$$
W(\vec{x},R)=\left\{\begin{align}
&\frac{3}{4\pi R^3}&&x<R \\
&0&&x\ge R
\end{align}\right.
$$
于是球内的物质涨落为
$$
\delta_s(\vec{x},R)=\int \delta(\vec{x}')W(\vec{x}'-\vec{x},R) \, d^3\vec{x}' 
$$
这里的下标 S 代表 smooth，它的含义是用半径为 R 内的平均密度涨落当作该点的密度涨落，是一个令密度涨落场光滑的操作。这里之所以写成卷积的形式，是为了在对他进行傅立叶变换后有更简单的形式
$$
\delta_k^s=\delta_k\tilde{W}(kR)
$$
其中 $\tilde{W}$ 为 $W$ 的傅立叶变换。

由于**星系粒子的数密度表征了物质在宇宙中的密度**，所以对于方差，我们有
$$
\begin{align}
\sigma_{R}^2&=\langle \delta_{s}^2(R) \rangle = \xi_{s}(r=0)\\
&= \frac{1}{2\pi^2} \int P_{s}(k) k^2\, dk  \\
&= \frac{1}{2\pi^2} \int V_{u}\langle |\delta_{k}^s|^2 \rangle  \, dk \\
&= \frac{1}{2\pi^2} \int P(k)\tilde{W}(kR) k^2\, dk 
\end{align}
$$
综上所述，我们终于将观测量 $\sigma$ 与功率谱联系在了一起。由于历史原因，取 R=8 Mpc/h 作为主要观测的参数，即 $\sigma_8$ ，我们可以通过 $\sigma(R)$ 来对比真实宇宙和理论模型的差异。

上述理论推导对于 $\sigma_8$ 还是有些理想：
+ 星系的分布并不能完美的示踪物质的分布，并且有相当大的偏差，如著名的 assembly bias
+ 对于 8 kpc 的尺度，有非线性成分，与我们目前的推导的基础前提不一致

总而言之，我们仍是迈出了重要的一步，对于不同宇宙学模型来说，LCDM 模型与观测符合的最好。
