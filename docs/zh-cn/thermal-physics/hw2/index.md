# Problem Set 2

<p>Chapter1: 12, 14</p>
<p>Chapter3: 12, 15, 1, 2, 11, 16</p>
<h2 id="作业答案">作业答案</h2>
<h3 id="1-12">1-12</h3>
<p>(1) 对具有两个独立参量T，p的物质，应有$V=V(T,p)$，则
$$
dV = \left(\frac{ \partial V }{ \partial T }\right)_pdT + \left(\frac{ \partial V }{ \partial p }\right)_TdT \tag{1-12.1}
$$
同时又有等压膨胀系数 $\alpha$ 和等温压缩系数 $\beta$ 的定义
$$
\alpha=\frac{1}{V}\left(\frac{ \partial V }{ \partial T } \right)_p~~~~
\beta=-\frac{1}{V}\left(\frac{ \partial V }{ \partial p } \right)_T
$$
于是易得
$$
\ln V=\int \frac{dV}{V} =\int (\alpha dT-\beta dp)
$$
(2)由题意，我们将这些系数的表达式带入第一问(1-12.1)中
$$
dV=\frac{nR}{p}dT-(\frac{V}{p}+a)dp \tag{1-12.2}
$$
在推导的过程中，要时刻记住自由参量是T，p和n，而V为它们的函数。为了得到它的物态方程，我们可以考虑初始条件为 $(p_0, T_0, V_0)$ 的物质，先经过等压变化到 $(p_0, T, V_1)$，然后再经过等温变化到 $(p,T,V)$。当然，在p-T图中选择其他你喜欢的路径也可以。
对于等压变化有$dp=0, p=p_0$，故有
$$
dV=\frac{nR}{p}dT~~\rightarrow <del>V_1=V_0+nR(T-T_0)/p_0
$$
对于等温变化有$dT=0, T=T$
$$
dV=-(\frac{V}{p}+a)dp</del>\rightarrow<del>dpV=pdV+Vdp=-apdp</del>
\rightarrow~~pV-p_0V_1=\frac{1}{2}ap^2-p_0^2
$$
联立即有
$$
pV-nRT+\frac{1}{2}ap^2=C
$$
其中C为常数。
当然，出于敏锐的直觉，由（1-12.2）也可以直接得到
$$
pV=\int (pdV+Vdp)=\int (nRdT-apdp)=nRT-\frac{1}{2}ap^2+C
$$</p>
<h3 id="1-14">1-14</h3>
<p>对于本题，我们想要求得的是末态的状态量，它仅仅由末态决定，而与如何从初态变化到末态无关，所以不妨考虑这样的过程
（1）先自由升温60$^{\circ}$C，此时两棒压力为零，长度从$l_{10}\rightarrow l_{11},l_{20}\rightarrow l_{21}$
（2）在这个温度下进行等温压缩，这样便能使用胡克定律（见教材P32）
对于过程（1），我们考虑可以从等温线膨胀系数得到长度的变化
$$
l_{i1}=l_{i0}(1+\alpha <em>{i}\Delta T)~,\quad i=1,2
$$
对于过程（2），压缩后两棒相对于$l</em>{i1}$的伸长量不同，不妨设为$\Delta l_{1},\Delta l_{2}$。由题设，两棒的长度之和没有改变，也即
$$
l_{11}+l_{21}+\Delta l_{1}+\Delta l_{2}=l_{10}+l_{20}
$$
同时，由于它们相互挤压达到平衡，说明其压力相同。由胡克定律，我们有
$$
p=\frac{F}{A}=-Y_{1}\frac{\Delta l_{1}}{l_{10}}=-Y_{2}\frac{\Delta l_{2}}{l_{20}}
$$
联立以上三式，得到
$$
p=\frac{(\alpha_{1}l_{10}+\alpha_{2}l_{20})\Delta T}
{(1+\alpha_{1}\Delta T) l_{10}/Y_{1}+(1+\alpha_{2}\Delta T) l_{20}/Y_{2}}=1.2\times 10^8Pa
$$</p>
<p>其中两钟材料的杨氏模量、线膨胀系数和在原来温度下的长度如下（部分来自教材）
$$
\left{\begin{align}
&amp;l_{10}=0.45m  &amp;&amp;L_{20}=0.25m \
&amp;\alpha_1=1.2\times 10^{-5}K^{-1} &amp;&amp;\alpha_{2}=2.5\times 10^{-5}K^{-1} &amp;\
&amp;Y_{1}=2\times 10^{11}N \cdot m^{-2} &amp;&amp;Y_{2}=0.7\times 10^{11}N\cdot m^{-2} &amp; \
\end{align}\right.
$$
实际上，我们也可以运用1-12的结论，不难看出线膨胀系数与等压膨胀系数，杨氏模量与等温压缩系数都可以一一对应起来，这一部分就交给同学们自己导出金属棒的物态方程了。</p>
<h3 id="3-12">3-12</h3>
<p>（1）对于p-V图上顺时针变化的循环，他一个周期的对外做功与其面积相同。在图3－12中，我们从左下角开始，按顺时针方向，依次将该四边形的顶点记做ABCD，则
$$
W=S_{ABCD}=7.55mmHg\cdot L=1.01J
$$
需要注意的是该四边形并非是平行四边形，需要仔细计算其面积。
（2）估算中不妨做如下近似：认为肺内气体和外界气体温度和压强相同，则呼出的气体的分子数目为
$$
N=N_A\frac{p_{0}V_{max}}{RT}=3.49\times10^{22}, ~~where~ V_{max}=1.4L, p_{0}=760mmHg=1.01\times 10^5Pa
$$
此处采取压强为大气压，如果用最大压强作计算也可以。</p>
<h3 id="3-15">3-15</h3>
<p>写出1mol范德瓦尔斯气体的状态方程
$$
(p+\frac{a}{\nu^2})(\nu-b)=RT
$$
外界对气体做功为
$$
W=\int_{\nu_i}^{\nu_f} -pd\nu
= \int_{\nu_i}^{\nu_f} \left(\frac{a}{\nu^2}-\frac{RT}{\nu-b}\right)d\nu
=a(\frac{1}{\nu_i}-\frac{1}{\nu_f})-RT\ln(\frac{\nu_f-b}{\nu_i-b})
$$</p>
<h3 id="3-1">3-1</h3>
<p>认为初末态样品和容器构成的系统能量守恒，则样品释放的热量全部转化为铜和水的内能。同时，末态系统达到热平衡，三者的温度均为$T_2=26.1$, 则有
$$
mc(T_0-T_2)=m_1c_1(T_2-T_1)+m_2c_2(T_2-T_1)
$$
其中$T_0=100,~T_1=19.0$，分别为初态样品、水和铜的温度，$m=0.085kg$，$m_1=0.2kg$,$m_2=0.15kg$， 分别为样品、水和铜的温度，解得
$$
c=1.012\times10^3J/(kg\cdot K)
$$</p>
<h3 id="3-2">3-2</h3>
<p>对于理想气体，我们依次写出其初态和末态满足的理想气体状态方程
$$
\begin{align}
p_1V&amp;=n_1RT_1 \
p_2V&amp;=n_2RT_2 \
2p_3V&amp;=(n_1+n_2)RT_3
\end{align}
$$
同时由于其与外界没有发生<strong>能量</strong>交换（区分：没有从外界吸放热），这说明其内能不变
$$
cn_1T_1+cn_2T_2=c(n_1+n_2)T_3
$$
联立上述四个方程，解得
$$
p_3=(p_1+p_2)/2,~~T_3=\frac{p_1+p_2}{p_1T_2+p_2T_1}T_1T_2
$$</p>
<h3 id="3-11">3-11</h3>
<p>（1）时间长为
$$
t=E/\dot{E}=((2+17)\times4+7\times9)/510~h=0.27h=16min
$$
（2）考虑一种违背热二极端情况，我们认为消耗的能量全部转化为动能：
$$
\frac{1}{2}mv^2=E <del><del>\rightarrow</del></del>v=\sqrt{ \frac{2E}{m} }=139.5m/s
$$
其中1cal=4.18J。
这显然有悖于我们的生活经验，实际情况中，由于重心的上下运动、地面摩擦和风阻等影响，人的功率（~100W）做多能提供到10m/s的速度。</p>
<h3 id="3-16">3-16</h3>
<p>（1）为了得到气体的吸热，我们先计算这团气体的质量
$$
m_0=\rho V=34.8kg
$$
对于等容变化，吸热为
$$
Q=C_Vm_0\Delta T=C_pm\Delta T/\gamma=4.916\times10^5J
$$
（2）对于等压变化，吸热为
$$
Q=C_pm_0\Delta T=6.93\times10^5J
$$
（3）由理想气体状态方程，对于容器内的气体，其体积和压强都不变，则
$$
pV=nRT=Const~~\rightarrow~~mT=Const
$$
即容器内的气体质量和其温度的乘积为常数。
则所需的热量为
$$
Q=\int dQ =\int C_p m(T)dT=C_pm_0T_0\int \frac{dT}{T} = C_pm_0T_0\ln\frac{T_2}{T_1}=6.678\times10^5J
$$</p>

