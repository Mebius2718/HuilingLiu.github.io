---
title: "第二章 线性理论"
subtitle: ""
date: 2023-7-16T20:00:00+08:00
author: "Mebius"
authorLink: ""
hiddenFromHomePage: True
draft: True
---

*昔日曾见此湖图，不信人间有此湖。*

*今日打从湖上过，画工还欠费工夫。*

## 2.1 扰动方程

### 2.1.1 宇宙物质场的扰动

我们可以用流体力学的语言来描述宇宙中物质的分布和运动。考虑简单的情形，认为这些物质是无粘滞的理想流体。在 Lagrange 空间下，我们有连续性方程和动力学方程

\begin{align*}
&\frac{d\rho}{dt}+\rho \nabla_r \cdot \vec{u}=0 \\\\\\\\
&\frac{d\vec{u}}{dt}=-\frac{1}{\rho}\nabla_r P - \nabla_r \phi
\end{align*}

>1. 这里的物质是指重子物质，对于暗物质的动力学方程中不应该有压强一项，不过这并不影响我们本章节的推导。
>2. 此处所有的 $\nabla_r$ 算子都是指对物理空间的求导

以及描述引力场的泊松方程
\begin{equation*}
\nabla_r^2\phi=4\pi G\rho-\Lambda
\end{equation*}

我们也可以在 Euler space 下描述物质的运动。这其与 Lagrangian space 的区别是前者关注的是某个位置附近的物质密度场和速度场，后者则是追踪确定物质粒子的运动。在 Euler space 下，此时的连续性方程和运动学方程变为


\begin{align*}
&\frac{d\rho}{dt}+\nabla_r \cdot (\rho\vec{u})=0 \\\\
&\frac{d\vec{u}}{dt}+(\vec{u}\cdot \nabla_r)\vec{u}=-\frac{1}{\rho}\nabla_r P - \nabla_r \phi
\end{align*}

以上几个方程是为了描述当今宇宙物质运动，应得到类似于 Friedmann 方程的解。由宇宙膨胀的物理意义，我们猜想以上的方程的解应为一组**稳定解和扰动解的叠加**：

\begin{align*}
&\rho=\bar{\rho}(1+\delta)=\rho_0\left(\frac{a_{0}}{a}\right)^3(1+\delta) \\\\
&\vec{u}=\vec{u}_0+\vec{v}=H\vec{r}+\vec{v} \\\\
&P=P_0+p \\\\
&\phi=\phi_0+\Phi
\end{align*}

实际上，我们已经非常熟悉这个方程的稳定解——尺度因子 a 的变化已经被 Friedmann 方程很好的描述了。所以我们不妨在共动坐标系考察这一问题，这有助于我们消掉 $\vec{u}$ 中哈勃流这一项。对于共动坐标系中的方程，也可以看作一种数学变换：
\begin{equation*}
\vec{r}=a \vec{\chi}
\end{equation*}

相应的，$\nabla_r, \rho,\vec{u}$ 也应作相应的变换。此时三个方程变为

\begin{align}
\frac{\partial{\delta}}{\partial{t}}+\frac{1}{a}\nabla \cdot[(1+\delta)]\vec{v}&=0 \\\\
\frac{\partial{\delta}}{\partial{t}}+\frac{\dot{a}}{a}\vec{v}+\frac{1}{a}(\vec{v}\cdot \nabla)\vec{v}&=-\frac{1}{a\bar{\rho}}\nabla p-\frac{1}{a}\Phi 
\end{align}


当然还有泊松方程，其中暗能量一项已经被宇宙学膨胀的稳定解约去了
\begin{equation}
\nabla^2\Phi=4\pi G\bar{\rho}a^2\delta
\end{equation}
注意 (1)(2)(3) 的 nabla 算子应为 $\nabla =\nabla_\chi$ ，作用在共动坐标系下。**我们约定：若无特殊说明，以后的各个物理量和求导，均在是在共动坐标系下讨论。**

我们关心的是扰动项，物理上这些扰动应该非常小，所以我们只保留关于扰动 $\vec{v},~\delta,~p$ 的一阶项，此时有

\begin{align}
\frac{\partial{\delta}}{\partial{t}}+\frac{1}{a}\nabla \cdot\vec{v}&=0 \\\\
\frac{\partial{\vec{v}}}{\partial{t}}+\frac{\dot{a}}{a}\vec{v}&=-\frac{1}{a\bar{\rho}}\nabla p-\frac{1}{a}\nabla\Phi \\\\
\nabla^2\Phi&=4\pi G\bar{\rho}a^2\delta
\end{align}

以上便是宇宙物质涨落的演化需要满足的方程。

特别的，我们对（5）两边求旋度，注意到 $\nabla \times \nabla f=0$ （散度无旋），故有
$$
\frac{\partial}{\partial{t}}\left(\nabla \times \vec{v}\right)+\frac{\dot{a}}{a}(\nabla \times \vec{v})=0 \tag{8}
$$
所以有
$$
\nabla \times \vec{v} \propto \frac{1}{a}
$$
从哈勃时标对应的时间尺度来看，宇宙迅速膨胀（尺度因子 a 迅速增大）导致 v 的角向速度迅速减小，所以我们忽略 v 的角向分量，只需考虑其平行分量即可，即
$$
v=v_{r}\hat{r}\tag{9}
$$
我们将在 3.2.2 进一步分析这个结论。

### 2.1.2 扰动方程的导出

为了处理压强项，我们考虑最简单的绝热扰动
$$
c_s^2=\frac{\partial{P}}{\partial{\rho}}=\frac{p}{\bar{\rho}\delta} \tag{10}
$$
带入 (5) 后有
$$
\frac{\partial{\vec{v}}}{\partial{t}}+\frac{\dot{a}}{a}\vec{v}=-\frac{c_{s}^2}{a}\nabla \delta-\frac{1}{a}\nabla \Phi\tag{11}
$$
对（11）两边求散度，再将 (4) 带入可得扰动方程
$$
\frac{\partial^2{\delta}}{\partial{t^2}}+2\frac{\dot{a}}{a}\frac{\partial{\delta}}{\partial{t}}=4\pi G\bar{\rho}\delta+\frac{c_s^2}{a^2}\nabla^2\delta
\tag{12}
$$
方程右侧的两项分别来自于引力和压强。我们只看引力项发现，宇宙的膨胀会抑制宇宙某处质量的增长；同时，更大的密度将促进该处密度的增长。

> 笔者认为这两点可以被很唯象的理解：其一，宇宙的膨胀使得物质间的物理距离变大，引力变小，使得物质更慢的汇聚；其二，过密的区域产生更强的引力，吸积其他物质的速率更快。

### 2.1.3 傅里叶空间中的扰动方程

由于扰动方程在实空间下不仅有关于时间的偏导，还有关于空间的偏导，故不好求解。我们不妨在傅立叶空间下求解：在傅立叶空间中，我们可以把对实空间的偏导转化为动量。本课程中对傅立叶变换有如下约定：正变换为
$$
\delta(\vec{k},t)=\frac{1}{V}\int \delta(\vec{x},t)e^{-i\vec{k}\cdot \vec{x} } \, d^3\vec{x} 
$$
逆变换为
$$
\delta(\vec{x},t)=\frac{V}{(2\pi)^3}\int \delta(\vec{k},t)e^{-i\vec{k} \cdot \vec{x}} \, d^3\vec{k} 
$$
为了简单起见，**我们约定：在傅立叶空间的函数简写为** $f_{\vec{k}}$，有时也略去波矢 $\vec{k}$ 中的矢量符号成为$f_k$，用来表示那些傅里叶变换后只与 k 的大小无关，与 k 方向无关的函数。

在傅立叶空间有以下性质

$$
\nabla \delta(\vec{x},t)=\sum_k (i\vec{k}\delta_{\vec{k}})e^{i\vec{k} \cdot \vec{x}}
$$

**由于傅立叶空间的正交性**，方程中相同 $\vec{k}$ 的系数必须相同，所以从实空间中的方程到傅立叶空间的方程往往只需要做如下替换即可：

$$
\nabla\to i\vec{k},~\delta\to\delta_{\vec{k}}
$$

利用上面的替换，我们可以把扰动增长方程写为

$$
\frac{d^2\delta_{\vec{k}}}{dt^2}+2\frac{\dot{a}}{a}\frac{d\delta_{\vec{k}}}{dt}=\left(4\pi G \bar{\rho}-\frac{k^2c_s^2}{a^2}\right)\delta_{\vec{k}}
$$

以及

\begin{equation}
\frac{d\delta_{\vec{k}}}{dt}+\frac{1}{a}i\vec{k} \cdot \vec{v}_{\vec{k}}=0
\end{equation}

\begin{equation}
\frac{d}{dt} \vec{v}_k + \frac{\dot{a}}{a} \vec{v}_k = -\frac{i\vec{k}}{a}\left(c_s^2\delta_k+\Phi_k\right)
\end{equation}

以上三个方程分别为连续性方程和动力学方程。同时还有傅里叶空间中的泊松方程

\begin{equation}
-k^2\Phi_{k}=4\pi G\bar{\rho}a^2\delta_{k}
\end{equation}

我们要注意的是在做**傅里叶变换时包含了一个隐藏的周期性条件**，因为严格的三维傅里叶变换定义在一个立方体内，而我们模拟的宇宙或者考察的天区未必会有如此好的边界。所以对于不规则的宇宙而言，线性理论往往会在考察的边界有较大的误差。

在傅里叶空间考察问题还有一些好处，因为不同 k 对应着不同尺度的演化，所以观察方程的解关于 k 的变化会给我们相同结构在不同尺度上演化的信息。

让我们回顾方程（9），由于线性理论中速度场只有 r 方向分量，所以在 k 空间中速度场也具有旋转对称性，即
$$
\vec{v_{k}}=v_{k}\hat{k}
$$
将其带入傅里叶空间的连续性方程

$$
\frac{d\delta_k}{dt}+\frac{ik}{a}v_{k}=0 \quad\rightarrow \quad\vec{v}_{k}=\frac{i\vec{k}a}{k^2}\frac{d\delta_k}{dt}
$$
这将密度涨落与速度场联系在了一起。


### 2.1.4 辐射主导的宇宙

在宇宙演化的初期为辐射主导的宇宙，此时的流体力学方程有所变化

\begin{align}
&\frac{d\rho}{dt}+\nabla_r \cdot [(\rho+P)\vec{u}]=0 \\\\
&\frac{d\vec{u}}{dt}+(\vec{u}\cdot \nabla_r)\vec{u}=-\frac{1}{\rho+P}\nabla_r P - \nabla_r \phi \\\\
&\nabla^2_r\phi=4\pi (\rho+3P) \\\\
&P=w\rho
\end{align}

对于辐射宇宙是绝热的，我们可以通过热力学第一定律得到密度和尺度因子的关系
$$
dQ=dU+PdV=0~~\rightarrow \quad \rho a^{3(1+w)}=Const
$$
在相对论性物质主导的宇宙中，尺度因子的变化为
$$
\left( \frac{\dot{a}}{a} \right)^2=\frac{8\pi G}{3}\rho_\gamma \propto a^{-3(1+w) } \quad \rightarrow \quad a\propto t^{\frac{2}{3(1+w)}}
$$
于是平均密度的演化为
$$
\bar{\rho}=\frac{3H^2}{8\pi G}=\frac{1}{6(1+w)^2\pi Gt^2}
$$
这自然也满足与尺度因子的关系。我们将其带入流体力学方程，与前文类似，在傅立叶空间中的流体力学方程最终被写为辐射的扰动方程
$$
\ddot{\delta}_k+2\frac{\dot{a}}{a}\dot{\delta}_k=4\pi G\bar{\rho}(1+w)(1+3w)\delta_k-\frac{k^2c_s^2}{a^2}\delta_k
$$

---

## 2.2 宇宙的扰动增长

上一节中，我们得到了共动坐标系下的扰动方程

$$
\frac{\partial^2{\delta}}{\partial{t^2}}+2\frac{\dot{a}}{a}\frac{\partial{\delta}}{\partial{t}}=4\pi G\bar{\rho}\delta+\frac{c_s^2}{a^2}\nabla^2\delta
$$

同时，我们还写出了傅里叶空间的扰动方程

$$
\frac{d^2\delta_{\vec{k}}}{dt^2}+2\frac{\dot{a}}{a}\frac{d\delta_{\vec{k}}}{dt}=\left(4\pi G \bar{\rho}-\frac{k^2c_s^2}{a^2}\right)\delta_{\vec{k}}
$$

以及傅里叶空间下连续性方程和以及动力学方程

\begin{equation}
\frac{d\delta_{\vec{k}}}{dt}+\frac{1}{a}i\vec{k} \cdot \vec{v}_{\vec{k}}=0
\end{equation}

\begin{equation}
\frac{d}{dt} \vec{v}_k + \frac{\dot{a}}{a} \vec{v}_k = -\frac{i\vec{k}}{a}\left(c_s^2\delta_k+\Phi_k\right)
\end{equation}

以及一个有用的结论
$$
\vec{v}_{k}=\frac{i\vec{k}a}{k^2}\frac{d\delta_k}{dt}
$$
在本节我们将使用这些方程讨论宇宙的扰动增长。

### 2.2.1 宇宙密度场的扰动增长

由于于我们的宇宙中重子气体稀薄，所以忽略共动坐标系下扰动方程中压强一项。此时密度扰动方程可以写为
$$
\frac{d^2 \delta}{dt^2}+2\frac{\dot{a}}{a}\frac{d\delta}{dt}=4\pi G\bar{\rho}\delta
$$
由于没有压强项，所以也不需要在傅里叶空间讨论它了。有趣的是，他和 Friedman 的加速方程相似，其中 Friedmann 加速方程即

$$
\frac{dH}{dt}+H^2=-\frac{4\pi G}{3}(\bar{\rho}_m-2\bar{\rho}_L)
$$

两边求导即有
$$
\frac{d^2H}{dt^2}+2\frac{\dot{a}}{a}\frac{dH}{dt}=4\pi G\bar{\rho}_{m}H
$$
这恰好说明 H(t) 便是扰动方程的一个衰减解！但我们更关心的是密度随时间增长的解，所以我们仍要求解这个方程，但 H 的给了我们信心，这至少说明该方程在确定的宇宙参数下是有解析解的。

既然已经获知其中一个解的全部信息，我们使用一些奇妙的技巧求解该方程的另一个解：对于该微分方程的两个解 $\delta_{1}, \delta_{2}$，我们有

$$
\begin{align}
\frac{d^2 \delta_1}{dt^2}+2\frac{\dot{a}}{a}\frac{d\delta_1}{dt}=4\pi G\bar{\rho}\delta_1 \\\\
\frac{d^2 \delta_2}{dt^2}+2\frac{\dot{a}}{a}\frac{d\delta_{2}}{dt}=4\pi G\bar{\rho}\delta_2
\end{align}
$$

消去右侧，得到



$$
\delta_2 \ddot{\delta}_1-\delta_1 \ddot{\delta}_2 + 2\frac{\dot{a}}{a} (\delta_2\dot{\delta}_1-\delta_1\dot{\delta}_2)=0
$$

即有
$$
\dot{y}+2\frac{\dot{a}}{a}y=0 \quad y=\delta_2 \dot{\delta_1}-\delta_1 \dot{\delta_2}
$$

分离变量得到

$$
\delta_2\dot{\delta_1}-\delta_1\dot{\delta_2}=y\propto a^{-2}
$$

**注意，上式对于包含压强的扰动方程依然成立。** 我们将 $\delta_2(t)=H(t)$ 带入其中，得到

$$
\frac{d}{dt} \left( \frac{\delta_1}{H} \right)=\frac{1}{H^2}(\dot{\delta_1}H-\dot{H}\delta_1)=\frac{1}{\dot{a}^2}
$$

所以有
$$
\delta=H(t)\int_{0}^t \frac{1}{a^2(t)H^2(t)} \, dt \tag 5
$$
特别的，对于 Einstein-de Sitter 宇宙，我们有
$$
H=\frac{\dot{a}}{a}=\frac{2}{3t}, ~a\propto t^{2/3}
$$
所以在暗物质主导的宇宙中有
$$
\delta \propto  t^{2/3}\propto a \tag 6
$$
这是一个非常优雅且重要的结论！对于暗物质主导的宇宙，其物质涨落正比于该宇宙的大小。这个结论在暗晕形成模型中起到了非常重要的作用。

### 2.2.2 线性增长因子

我们可以将（4）写为
$$
\delta(z) = D(z)\delta_{0} = \frac{g(z)}{1+z}\delta_{0}
$$
其中 $\delta_{0}$ 是 z=0 时的密度涨落，而D(z) 即**线性增长因子**，g(z) 代表了 Einstein de-Sitter 宇宙和真实宇宙的区别。原则上，线性增长因子是一个没有解析解的积分，我们现在自然可以用计算机很快的获得一个十分精确的数值，而对上世纪 90 年代的人们来说并没有这么好的条件，所以 Carroll et al (2019) 给出了一个很好的估计
$$
g(z)=\frac{5}{2}\Omega_{m}(z)\left\[ \Omega^{4/7}_{m}(z)-\Omega_L(z) +\left( 1+\frac{\Omega_m(z)}{2} \right)\left[ 1+\frac{\Omega_L(z)}{70} \right]\right\]^{-1}
$$
由于线性增长因子和宇宙学直接相关，理论上我们可以借助它来约束宇宙学参数，但这需要相当长时间的观测才能有效的约束宇宙学参数，这并不现实。

### 2.2.3 速度场与引力场

获知了密度涨落的演化信息后，我们便可以通过方程（4）得到速度场信息

$$
\vec{v}_k=\frac{i\vec{k}a}{k^2}\frac{d\delta_k}{dt}
=\frac{i\vec{k}a}{k^2}\delta_k(t_0) \frac{dD}{dt}
=\frac{i\vec{k}}{k^2}Ha\delta_k\frac{d\ln D}{d\ln a}
=\frac{i\vec{k}}{k^2}Ha\delta_k f(\Omega)
$$

其中
$$
f(\Omega_{m})=-\frac{d\ln D(z)}{d\ln (1+z)}\approx\Omega_{m}^{0.6}
$$
最后的近似来自 Peebles et al 1990。它说明对于高密度区域的本动速度往往更大；同时，由于不同尺度的本动速度反比于 k，所以尺度大的结构有着更大的本动速度，这也是为什么在暗物质模拟中，密度场中小尺度的结构在速度场中消失的原因。

当然，这个公式也可以用来限制宇宙学参数。但由于宇宙距离的测量中，标准烛光依然存在着种种问题和较大误差，所以本动速度无法精确的确定；其次，我们只能测量星系的本动速度和密度涨落而非暗物质，所以会引入更大的不确定度，这个不确定度与星系的形成模型密切相关，是星系天文学中待解决的重要问题。总之，这种限制宇宙学参数的方法并不十分有效。

接下来让我们考虑引力场的分布。在傅里叶空间中，泊松方程变为
$$
-k^2\Phi_{k}=4\pi G\bar{\rho}a^2\delta_{k}
$$
我们先考虑引力场随时间的变化，由泊松方程得到
$$
\Phi_{k}(a)=-\frac{4\pi G\delta_{k,0}}{k^2}D(a)\bar{\rho}a^2\propto \frac{D}{a}\propto Const \tag 8
$$
这里认为是物质主导时期的宇宙，由 $\bar{\rho} a^3=Const$ 即质量守恒。这说明线性理论下，宇宙的引力场不随时间变化。在考虑暗能量的情形下，引力势则随着宇宙的膨胀而衰减。

再考虑某一时刻的引力场与速度场、密度场的关系，我们由
$$
\vec{v}_k=\frac{i\vec{k}}{k^2}Ha\delta_k f(\Omega)=\frac{Hf(\Omega)}{4\pi G\bar{\rho}_m a}i\vec{k}\Phi
$$
变换到实空间有
$$
\vec{v}\propto-\nabla \Phi \tag 9
$$
这说明本动速度正比于引力大小。

从 CMB 的各向异性中可以计算出太阳系相对于共动坐标系的速度，会发现太阳系处于一个引力较大的区域，人们认为这是由宇宙中许多引力源叠加导致的。

### 2.3.2 重子声波震荡

上一小节中，我们能通过求解扰动方程得到了波动解和衰减解，并指出暗晕中的物质振动尚未得到观测证据的支持。本小节中我们讨论一种可以被观测支持的振动解，即**重子声波震荡（baryon acoustic oscillations, BAO**）

在 1100 < z < 3000 的时间中，宇宙中的电子和光子不断的发生康普顿散射，二者强烈地耦合在一起。我们考虑一个空间上的大尺度，时间上的小尺度的过程。忽略哈勃项，此时的扰动方程为

$$
\ddot{\delta}_b+\frac{k^2 c_s^2}{a^2}\delta_b=4\pi G\bar{\rho}\delta_{dm} =-\frac{k^2}{a^2}\Phi_{dm}
$$

在 Einsteind-de Sitter 宇宙中，引力项 $\Phi_{dm}$ 被冻结。同时由于我们关注短时标上的过程，所以认为尺度因子 a 也不变。所以方程写为
$$
\ddot{\delta}_b+\frac{k^2c_s^2}{a^2}\left( \delta_b+\frac{\Phi_{dm}}{c_s^2} \right)=0
$$
这是个波动方程，解得
$$
\delta_b=(\delta_{b,0}+\frac{\Phi_{dm}}{c_s^2})\cos \omega t+\frac{1}{\omega}\dot{\delta}_{b,0}\sin\omega t-\frac{\Phi_{dm}}{c_s^2},~~\omega=\frac{kc_s}{a}
$$
现在我们可以解释为什么可以忽略哈勃项了，我们考虑该振动的时标长短
$$
T=\frac{2\pi}{\omega}=\frac{kc_{s}}{a}\gg \frac{1}{H}
$$
这是因为此时的声速（光速量级）远大于解耦后的声速，或者说金斯波长接近视界的大小，所以该震荡确实是一个短时标的过程。

在 recombination 之前，物质不断在重子和光子耦合的宇宙中振动。随着重子和光子解耦，该震荡也随之停止，此时会留下不同相位的振动模式，其中振动到密度最高峰的波会留下高密度区域。这个区域的长度为
$$
\lambda=2 c_s t_{rec}=\frac{2}{\sqrt{ 3 }}c_{s}t_{{rec}}\approx 150 ~\text{Mpc}
$$
我们可以计算它对应的角长度
$$
\theta=\frac{\lambda}{d_{A}(z_{rec})}=0.7^{\circ}
$$
以上便是宇宙重子声波震荡的数学背景。它为我们遗留了重子物质在宇宙尺度上的成团信息。如今该现象可以通过 CMB 以及星系的成团性探测到：例如，若我们测量星系的两点相关函数，则会发现其在 150Mpc 上有一个峰；同样位置的峰也会出现在 $Ly-\alpha$ 森林的两点相关函数中。我们可以测量不同红移处的 BAO ，从而约束宇宙学参数。

### 2.3.3 重子物质的演化

我们进一步考虑在暗物质主导的宇宙中重子物质的变化。在这种情况下，我们将扰动方程写为
$$
\frac{d^2\delta_b}{dt^2}+2\frac{\dot{a}}{a}\frac{d\delta_b}{dt}=4\pi G\bar{\rho}\delta_{dm}-\frac{k^2c_s^2}{a^2}\delta_b
$$
这里用下标 b 和 dm 分别代表重子物质项和暗物质项。

我们考虑多方流气体 $P\propto \rho^\omega, \omega=\frac{4}{3}$，这种气体的声速有
$$
c_s^2a=\frac{ \partial P }{ \partial \rho }a\propto \rho^{1/3}a=Const 
$$
可知这一项不随时间变化。而对于 Einstein-de Sitter 宇宙，由前文的结论，我们有
$$
\delta_{dm}=Aa=A\left( \frac{3}{2}H_0 t\right)^{\frac{2}{3}}a_0,~~ c_s^2a=D
$$
其中 A、D 为常数。由此，扰动方程变为
$$
t^2\ddot{\delta}_b + \frac{4t}{3}\dot{\delta}_b + \frac{k^2D}{a_0^3\left( \frac{3}{2}H_0^2 \right)^2}\delta_b=A\frac{4\pi G\bar{\rho}_0a_0}{\left( \frac{3}{2}H_0 \right)^{\frac{4}{3}}}t^{\frac{2}{3}}
$$
解得
$$
\delta_b=\frac{Aa_0\left( \frac{3}{2}H_0^2 \right)^{\frac{2}{3}}}{1+k^2/k_J^2}t^{\frac{2}{3}}=\frac{\delta_{dm}}{1+k^2/k_J^2},~~ k_J^2=\frac{3a^2H^2}{2c_s^2}
$$
这说明在很大尺度上重子物质和暗物质的密度演化相似，这是因为大尺度上重子物质间的压强项可以忽略不计。

这里也引入了一个特征波矢 $k_{J}$，它对应的长度为
$$
\lambda_{J}=\frac{2\pi a}{k_{J}}=c_{s}\sqrt{ \frac{8\pi^2}{3H^2} }=c_{s}\sqrt{ \frac{1}{G\bar{\rho}} }
$$
这正是金斯波长！或者说，声速传播的边界。


## 2.4 Zel'dovich 近似

### 2.4.1 拉格朗日空间及另一种尺度因子

苏联的宇宙学家有不一样的见解。我们之前的推导相当于是在 Euler space 中的推导，本节中采取苏联宇宙学家 Zel'devich 的方案，我们在 Lagrangian space 考虑这个问题。这里我们采取另一种尺度因子 D (a)，不同于 a，D (a)在宇宙早期进行归一化，即
$$
D(a_i)=1, \quad \delta(a)=D(a)\delta_{i}
$$

>说起来这真是十分符合笔者的审美，因为笔者仍然持有一种绝对时空的观念，所以选择一个确定的时刻作为标度会让笔者感到舒适。

### 2.4.2 Zel'dovich 近似
计算泊松方程
$$
\nabla^2\Phi(\vec{x},a)=4\pi Ga^2\bar{\rho}\delta=4\pi G\frac{\bar{\rho}_ia_i^3}{a}D(a)\delta_i(\vec{x})=\frac{a_i}{a}D(a)\nabla^2\Phi_i(\vec{x})
$$
带入拉格朗日空间的运动方程
$$
\dot{\vec{v}}+\frac{\dot{a}}{a}\vec{v}=-\frac{\nabla \Phi}{a}
$$
两边乘以 a 后积分可得
$$
\vec{v}=-\frac{a_{i}\nabla \Phi_{i}}{a}\int_{t_{i}}^t \frac{D(a)}{a} \, dt 
$$
我们尝试继续将其化简。考虑扰动演化方程
$$
\ddot{\delta}+2\frac{\dot{a}}{a}\dot{\delta}=4\pi G\bar{\rho}\delta
$$
由于 D 的定义 $\delta(a)=D(a)\delta_{i}$，结合扰动演化方程有
$$
\dot{D}a^2=\int_{t_{i}}^t (a^2\ddot{D}+ 2a\dot{a}\dot{D})\, dt =\int_{t_{i}}^t a^2\left( \ddot{D}+ 2\frac{\dot{a}}{a}\dot{D} \right)\, dt=4\pi G\bar{\rho}a^3\int_{t_{i}}^t \frac{D(a)}{a} \, dt
$$
再带入速度场的表达式
$$
\vec{v}=-\frac{a_{i}\nabla \Phi_{i}}{a}\int_{t_{i}}^t \frac{D(a)}{a} \, dt =-\frac{a_{i}\nabla \Phi_{i}}{a}\frac{\dot{D}a^2}{4\pi G\bar{\rho}a^3}=-\frac{\dot{D}a_{i}}{4\pi G\bar{\rho}a^2}\nabla \Phi_{i}
$$
注意，这里的散度是对共动坐标 $\vec{\chi}$ 来说的。我们继续积分它，得到
$$
\vec{\chi}=\vec{\chi}_{i}-\frac{a_{i}D(a)}{4\pi G\bar{\rho}a^3}\nabla\Phi_{i}(\vec{\chi})(D-D(a_{i}))=\vec{\chi}_{i}-\frac{a_{i}D(a)}{4\pi G\bar{\rho}a^3}\nabla\Phi_{i}(\vec{\chi})(D-1)
$$
考虑到 $D\propto a$，对于宇宙的演化来说，宇宙的大小从暴涨结束到现在已经上升了几个数量级，所以 $D\gg 1$。此外 Zel'dovich 还建议将 $\vec{\chi}$ 用 $\vec{\chi}_{i}$ 替代，即 **Zel'dovich 近似**
$$
\vec{\chi}=\vec{\chi}_{i}-\frac{a_{i}D(a)}{4\pi G\bar{\rho}a^3}\nabla\Phi_{i}(\vec{\chi}_{i})
$$
这是一个非常漂亮的结论，它可以快速得到给定初始条件下，一段时间后的物质运动到什么位置，具有怎样的速度。我们可以通过这个方法给出再构造（reconstruction）数值模拟的初始条件。进而重建已知的宇宙。同时，人们发现这个非常可靠，比欧拉空间强不少。

### 2.4.3 Zel'dovich 近似的应用

接下来我们来看看 Zel'dovich 的威力。我们在拉格朗日空间中占据一定体积的一群粒子，它们从宇宙早期的归一化时刻运动到某个时刻，由于质量守恒
$$
\rho d^3\vec{\chi}=\rho_{i}d^3\vec{\chi}_{i}
$$
对于共动坐标系中所有物质来说，共动体积不变，所以质量守恒给出有
$$
\rho_{i}=\bar{\rho}
$$
考虑 Zel'dovich 近似
$$
\chi_{j}=\chi_{ij}-\frac{Da_{i}}{4\pi G\bar{\rho}a^3}\frac{ \partial \Phi_{i}(x_{j}) }{ \partial x_{{ij}} }=x_{ij}-DT\frac{ \partial \Phi_{i}(x_{j}) }{ \partial x_{{ij}} }  ,\quad j=1,2,3
$$
其中 $T=a_{i}/(4\pi G\bar{\rho} a^3)$，我们可以把粒子运动前后的位置变换写成矩阵的形式
$$
\vec{\chi}=\vec{\chi}_{i}-DT\nabla\Phi_{i}(\vec{\chi}_{i})
$$ 我们要从 Zel'dovich 近似回到前面几个小节的 $\delta$，于是有
$$
1+\delta=\frac{\rho}{\bar{\rho}}=\frac{\rho}{\rho_{i}}=\frac{d^3\vec{\chi}}{d^3\vec{\chi}_{i}}=\left({\det\left| \frac{ \partial \vec{x} }{ \partial \vec{x}_{i} }  \right|}\right)^{-1}
$$
此处的 
$$
\left(\frac{ \partial \vec{x} }{ \partial \vec{x}_{i} }\right)_{jk}=\delta_{jk}-DT\frac{ \partial^{2} \Phi_{i} }{ \partial x_{ij} \partial x_{ik} } 
$$
为 Jacobi matrix，作为实对称阵，他总能对角化，且一定能找到一组相互正交的特征向量。我们不妨就将这些特征向量的方向作为坐标轴的单位向量。此时该矩阵为对角矩阵，它的行列式为
$$
\det\left| \frac{ \partial \vec{x} }{ \partial \vec{x}_{i} }  \right|=(1-D\lambda_{1})(1-D\lambda_{2})(1-D\lambda_{3}), \quad \lambda_{j}=T\frac{ \partial^2 \Phi_{j} }{ \partial \chi^2_{i,j} } 
$$
对于线性理论有 $D\lambda_{j}\ll 1$，所以我们给出
$$
\delta=D(\lambda_{1}+\lambda_{2}+\lambda_{3})=T\nabla^2\Phi_{i}=D\delta_{i}
$$
他很好的重现了欧拉空间中推导的结果！

我们再对密度涨落进行更深入的讨论，结合上面的结果我们有
$$
1+\delta=\frac{1}{(1-D\lambda_{1})(1-D\lambda_{2})(1-D\lambda_{3})}
$$
这说明潮汐场主轴方向上的大小决定了形成怎样的结构

| $\lambda_{1}$ | $\lambda_{2}$ | $\lambda_{3}$ |structure|
|:-:|:-:|:-:|:-:|
|+|+|+|knot/cluster|
|+|+|-|filament|
|+|-|-|sheet|
|-|-|-|void|
