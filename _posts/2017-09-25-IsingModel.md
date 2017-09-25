---
layout: szhang_note
category: notes
math: true
code: true
title: Ising 模型
---


# Ising模型介绍
Ising模型是一个以物理学家恩斯特·易辛为名的数学模型，用于描述物质的铁磁性。一个二维的方晶格易辛模型是已知最简单而会产生相变的物理系统之一。

模型描述：
N个经典粒子(编号$i=1,2…,N$)，其哈密顿量只与每个粒子的自旋自由度($s_i=1,-1$只有单方向分量)有关，与空间运动自由度($x_i,p_i$)无关；粒子静止的摆放在周期性d维晶格上(冻结了空间运动自由度)。

体系微观状态的描述为：
$$(s_1,s_2,…,s_N)=\{s_i\}$$
可见体系共有$2^N$种微观状态(相空间的大小)

Ising Hamiltonian:$$H(\sigma)=-J\sum_{\langle i~j\rangle} s_i s_j -B\sum_j s_j$$

<>代表不重复的最近邻的键 ，最近邻格点上的自旋与自旋之间相互作用，自旋与外场之间有耦合。J>0称为铁磁Ising模型，J<0称为反铁磁Ising模型。

# 一维Ising模型计算
## 一维Ising模型定性理解
零场零温（T=0,B=0）下
$$H=-J\sum_{<i,j>}s_is_j.....s_i=\pm1$$





T=0，基态二重简并
![零温，基态][1]


  T>0，基态与激发态都以一定概率出现：$\rho(\{s_i\})=e^{\beta H(\{s_i\})}$
  ![元激发][2]
  
  
  
  
  
  
 
  温度会打破完全有序的状态，给体系带来熵。第一激发态N-1重简并。
  
  一般来说，自由能F=U-TS取极小决定了体系的热力学状态，这里面有序项$F_{order}=0$，无序项$F_{disorder}\approx2J-k_BT\ln(N-1)$(只考虑元激发)。相变点$F_{disorder}=F_{order}$即$0=2J-k_BT\ln(N-1)$，可以得到，
  $$T_c={2J\over \ln (N-1)}$$
  
  热力学极限下，$T_c=0$,即一维Ising系统不存在非零温相变。
  
## 一维Ising模型严格解
具体看体系热力学性质需要严格求出体系配分函数，这里需要用到转移矩阵的方法，哈利顿量写成

$$\begin{aligned}
H=&-J(s_1s_2+s_2s_3+...+s_{N-1}s_{N}+s_{N}s_1)\\
&-B(s_1+s_2+...s_N)\\
=&-\left(Js_1s_2+B{s_1+s_2\over 2}\right)-\left(Js_2s_3+B{s_2+s_3\over 2}\right)-...\\
&-\left(Js_Ns_1+B{s_N+s_1\over 2}\right)
\end{aligned}$$

配分函数

$$Z(T,B)=\mathrm{Tr}(e^{-\beta H})=\sum_{\{s_{i}\}}e^{-\beta H(\{s_i\})}=\sum_{s_1=\pm 1}\sum_{s_2=\pm 1}…\sum_{s_N=\pm 1}e^{-\beta H(\{s_i\})}$$

于是可以写为：

$$\begin{aligned}
Z=&\mathrm{Tr}(e^{-\beta H})\\
=&\sum_{\{s_i\}}e^{\gamma s_1s_2+\alpha{s_1+s_2\over 2}}e^{\gamma s_2s_3+\alpha{s_2+s_3\over 2}}...e^{\gamma s_Ns_1+\alpha{s_N+s_1\over 2}}\\
=&\sum_{\{s_i\}}T_{s_1,s_2}T_{s_2,s_3}...T_{s_N,s_1}\\
=&\sum_{s_1}\sum_{s_2}...\sum_{s_N}T_{s_1,s_2}T_{s_2,s_3}...T_{s_N,s_1}
\end{aligned}$$

其中$$T=
\left(
\begin{array}{c}
e^{\gamma+\alpha}~~e^{-\gamma}\\ 
e^{-\gamma}~~e^{\gamma-\alpha}
\end{array}
\right)
$$称为转移矩阵，$\alpha,\gamma$为温度相关系数。又已知，任意矩阵
$$A^N_{i,j}=\sum_{k_2k_3...k_N}A_{i,k2}A_{k_2k_3}...A_{k_N,j}$$
所以得到

$$\begin{aligned}
Z=&\sum_{s_1}T^N_{s_1,s_1}\\
&=tr(T^N)\\
&=\lambda_1^N+\lambda_2^N
\end{aligned}$$


其中$\lambda_{1,2}=e^\gamma(\cosh\alpha\pm\sqrt{\sinh^2\alpha+e^{-4\gamma}})$
通过其得到体系热力学性质。

 - $F(T,B)=-\beta^{-1}\ln Z(T,B)$
 - $U(T,B)=-\left({\partial \ln Z\over \partial \beta}\right)$ 
 - $G(r)=< s_{k}s_{k+r}> -<s_{k} > < s_{k+r}>$

 热力学极限下，可以得到
 $$F=-NJ-Nk_BT\ln\left[\cosh\left(B\over k_BT\right)+\sqrt{\sinh^2\left(B\over k_BT\right)+e^{-4J\over k_BT}}\right]$$
 
自由能是温度T与磁场B的解析函数，无奇异性，任意阶可微，不存在自发磁化。
 
## 二维Ising模型计算
 
 由Lars Onsager导出
 重要结论：
 $$\frac{kT_{c}}{J}=\frac{2}{ln(1+\sqrt{2})}\approx2.269$$
 $$E=-2NJ\tanh2\beta J-NJ\frac{\sinh^{2}2\beta J-1}{\sinh2\beta J\cosh2\beta J}[\frac{\pi}{2}K_{1}(\kappa)-1]$$
[Crystal Statistics. I. A Two-Dimensional Model with an Order-Disorder Transition][3]




## Weiss平均场理论计算
除了少数几个特殊情况以外，无法得到Ising模型的严格解。忽略格点自旋的相关性。
$$H_{MF}=-(Jqm+B)\sum_{i=1}^{N}s_i+Jm^2{Nq\over 2}$$
通过配分函数计算平均磁矩$m$，得到自洽条件，
$$m=\tanh\left({B+Jqm\over k_BT}\right)$$
考虑自发磁化（$B=0$）
由自洽条件得到居里温度
$$T_c=Jq/k_B$$

# Ising模型经典计算方法

## Metropolis算法
Metropolis–Hastings 算法是在数值模拟易辛模型时最常用的一种蒙特卡洛方法。

 1. 首先取一个冻结自旋系统模型，初始构型的选择依赖于温度。高温下可以选择完全随机无序的初始构型，低温下选择有序铁磁或者反铁磁构型。
 2. 随机或逐个选取一个或几个自旋进行反转形成新构型，将一个老构型改变成另外一个新构型时，新构型被认可概率正比于$r=e^{-\Delta E\over k_BT}$，其中$\Delta E$为两构型能量差。
 3. 如果新构型能量低$\Delta E<0$，$r>1$接受该构型。如果新构型能量较高$\Delta E>0$，$r<1$则产生一个0~1随机数$\mathrm{rand}$，如$\mathrm{rand}<r$就接受，否则维持原构型。
 
## 核心子程序代码

```matlab
function m=Isingrand(T)
    N=1000;
    s=zeros(N,N);
    %T is temperature
    J=1;%exchange interaction strength
    k=1;%Boltzmann constant
    for i=1:N
        for j=1:N
            if(rand>0.5)
              s(i,j)=1;
            else
              s(i,j)=-1;
            end
        end
    end
    for i=1:2000*N^2
        [a,x,y]=spinflip(s,k,T,N,J);
        s(x,y)=s(x,y)*a;
    end
    m=abs(sum(sum(s))/N^2);
end
```
```matlab
function [a,x,y]=spinflip(s,k,T,N,J)
     x=floor(rand*N+1);
     y=floor(rand*N+1);
    if x~=1&&x~=N&&y~=1&&y~=N
        dH=2*J*s(x,y)*(s(x-1,y)+s(x+1,y)+s(x,y-1)+s(x,y+1));
    elseif x==1&&y~=1&&y~=N
        dH=2*J*s(1,y)*(s(1,y-1)+s(1,1+y)+s(2,y)+s(N,y));
    elseif x==N&&y~=1&&y~=N
        dH=2*J*s(N,y)*(s(N,y-1)+s(N,1+y)+s(1,y)+s(N-1,y));
    elseif x~=1&&x~=N&&y==1
        dH=2*J*s(x,1)*(s(x-1,1)+s(x+1,1)+s(x,2)+s(x,N));
    elseif x~=1&&x~=N&&y==N
        dH=2*J*s(x,N)*(s(x-1,N)+s(x+1,N)+s(x,1)+s(x,N-1));
    elseif x==1&&y==1
        dH=2*J*s(1,1)*(s(2,1)+s(N,1)+s(1,2)+s(1,N));
    elseif x==1&&y==N
        dH=2*J*s(1,N)*(s(2,N)+s(N,N)+s(1,1)+s(1,N-1));
    elseif x==N&&y==N
        dH=2*J*s(N,N)*(s(1,N)+s(N-1,N)+s(N,1)+s(N,N-1));
    elseif x==N&&y==1
        dH=2*J*s(N,1)*(s(1,1)+s(N-1,1)+s(N,2)+s(N,N));
    end
    a=1;
    if(dH<=0)
        a=-1;
    elseif (exp(-1*dH/k/T)>rand)
        a=-1;
    end
end
```
## 计算结果
由于计算模型较大，自己计算机运行能力有限，没有执行太多循环。通过两张图，定性的可以开出$J$与$T_c$的正相关关系。
左图$J=1$，右图$J=2$，均为磁化率-温度（$m-T$）图像。


![J=1，2，m-T图像][4]

# Ising模型量子模拟方法







  [1]: http://owqv2do09.bkt.clouddn.com/letdly/170924/aGc11ciAmI.png
  [2]: http://owqv2do09.bkt.clouddn.com/letdly/170924/cJLLIjLGGL.png
  [3]: https://journals.aps.org/pr/abstract/10.1103/PhysRev.65.117
  [4]: http://owqv2do09.bkt.clouddn.com/letdly/170924/jF3D0dCalK.png