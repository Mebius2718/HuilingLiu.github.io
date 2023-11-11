---
title: "Problem Set 8"
subtitle: ""
date: 2023-06-07T20:00:00+08:00
draft: false
author: "Mebius"
authorLink: ""
hiddenFromHomePage: True
---

Chapter 5: 3, 4, 5, 1, 2, 7, 21

## 作业答案
### 5-3
圆柱和圆柱体的半径差别 $\delta=R_{2}-R_{1}=0.5cm$，与 $R_{2}$ 的数量级相差不到 2，所以这里我们还是严格求解这个问题：氢气在圆柱筒中的转速只和 r 有关且不随时间变化，这说明各层间的力矩是一样的。考虑 r 处的力矩为
$$
G=\eta \frac{d(\omega r)}{dr}2\pi r L \cdot r
$$
求解这个微分方程可得
$$
\omega(r)=\frac{C}{r}-\frac{G}{2\pi \eta Lr^2}
$$
其中 C 为常数。带入边界条件 $\omega(R_{2})=\omega, \omega(R_{1})=0$ ,得到
$$
\eta=\frac{G}{2\pi \eta LR_{2}}\left[ \frac{1}{R_{1}}-\frac{1}{R_{2}} \right]=7.88\times 10^{-5} N\cdot m^{-2}\cdot s
$$

### 5-4
由于速度梯度相等，我们可以简单的写出在 r 处的速度梯度
$$
\frac{dv}{dz}=\frac{\omega r}{d}
$$
这个梯度会造成盘收到粘滞阻力，当盘有角速度 $\omega$ 时，它受和力矩为
$$
G=\int_{0}^R F(r)r \, dr= \int_{0}^R \left(\eta \frac{ dv}{dz} 2\pi r \right) r \, dr=\frac{\pi \eta}{2d}\omega R^4
$$
由角动量定理，对于匀质圆盘的转动惯量为 $I=\frac{1}{2}MR^2$，所以
$$
\frac{1}{2}MR^2 \frac{d\omega}{dt}=-\frac{\pi \eta}{2d}\omega R^4
$$
解得
$$
\omega(t)=\omega_{0}\exp\left( -\frac{\eta \pi R^2}{Md} t\right)
$$

### 5-5
标准状态指 T=0°C，p=1 atm。对于本题中的放射性二氧化碳，它的相对原子质量为 46 

（1）我们取最左端的位置为 x=0，由理想气体状态方程
$$
p\mu =\rho RT
$$
得到 t=0 时的密度梯度为
$$
\frac{d\rho}{dx}=\frac{\mu p_{0}}{RT_{0}L}=1.03 kg/m^{4}
$$

（2）参考 p204 的公式
$$
\frac{dN}{dt}=D\left( \frac{dn}{dx} \right)A=\frac{A}{3\pi d^2L}\sqrt{ \frac{4RT}{\pi \mu} }=9.87 \times 10^{15}s^{-1}
$$
（3）由第二问的结论易得
$$
\frac{dm}{dt}=\mu  \frac{dN}{dt}=7.54\times 10^{-10}kg/s
$$

### 5-1
（1）对于气体的粘滞系数（p201）有
$$
\eta=\frac{1}{3}nm\bar{v}\lambda
$$
而对气体压强有
$$
p=nkT
$$
所以它们的比例为
$$
\frac{\eta}{p}=\frac{m\bar{v}\lambda}{3kT}=\frac{m\bar{v}^2}{3kT}\tau = \frac{8}{3\pi}\tau
$$
其中 $\tau$ 为两次碰撞的平均时间，用到了 $\bar{v}=\sqrt{ \frac{8kT}{\pi m} }$，对于单位时间碰撞次数 $Z=\frac{1}{\tau}$ 有
$$
\frac{p}{\eta}=\frac{3\pi}{8}Z=1.18Z\approx Z
$$
（2）对于标准状态下的气体 p=1 atm，所以
$$
Z\approx \frac{p}{\eta}=5.6\times 10^9 s^{-1}
$$

### 5-2
参考教材 p201 和 p204 的公式，有
$$
\eta=\frac{1}{3}nm\bar{v}\lambda,\quad D=\frac{1}{3}v\lambda
$$
所以有
$$
\eta=D\rho=4.01 \times 10^{-5}N\cdot s/m^2
$$

### 5-7
参考教材 p201 , p204 和 p211 的公式，有
$$
\eta=\frac{1}{3}nm\bar{v}\lambda,\quad D=\frac{1}{3}v\lambda,\quad\kappa=\frac{1}{3}n\bar{v}\lambda  \frac{C_{V}}{N_{A}}
$$
所以有
$$
D=\frac{\eta}{\rho},\quad\kappa \propto \eta \frac{ C_{V}}{m}
$$
（1）则有
$$
\frac{\kappa_{Ar}}{\kappa_{He}}=\frac{\eta_{Ar}}{\eta_{He}} \frac{m_{He}}{m_{Ar}}=0.11
$$
（2）则有
$$
\frac{D_{Ar}}{D_{He}}=\frac{\eta_{Ar}}{\eta_{He}} \frac{\rho_{He}}{\rho_{Ar}}=\frac{\eta_{Ar}}{\eta_{He}} \frac{m_{He}}{m_{Ar}}=0.11
$$
这是因为标准状态下气压、温度一致，所以数密度也一致。

### 5-21
（1）记 $n=1.5mol, T_{2}=40K, T_{1}=10K$，则吸热为
$$
Q=\int_{T_{1}}^{T_{2}} nC \, dT= \frac{nk}{\theta^3}\int_{T_{1}}^{T_{2}} T^3 \, dT=\frac{nk}{4\theta^3}(T_{2}^4-T_{1}^4)=83.1J
$$
（2）平均摩尔热容为
$$
\langle C_{V} \rangle = \frac{Q}{n(T_{2}-T_{1})}=1.858J/(mol \cdot K)
$$
（3）在 T2 时的热容为
$$
C_{V}(T_{2})=k\left( \frac{T_{2}}{\theta} \right)^3=5.60J/(mol \cdot K)
$$