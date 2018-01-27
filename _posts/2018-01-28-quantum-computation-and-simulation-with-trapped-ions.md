---
layout: szhang_publication
category: publications
title: 离子量子计算与模拟
pdf: /notes/2018/01/28/离子阱科普.pdf
cover: /notes/2018/01/28/1.png
---
段路明<sup>1</sup>，尹璋琦<sup>1</sup>，张静宁<sup>1</sup>，张翔<sup>2,1</sup>

1 清华大学交叉信息研究院量子信息中心，2 人民大学物理系

## 第一节 引言

量子计算与模拟是目前量子信息技术中核心的研究方向。在量子计算与模拟的物理实现中，离子系统是最早提出的实验系统，也是一直处于引领地位的系统之一。离子系统具有优异的相干性能，基于离子的量子比特相干时间已经超过了10分钟，可以实现超高保真度（>99.9%）的普适量子逻辑门。基于此系统，人们已经制备了14个量子比特的多体纠缠态，并在超过50个离子的系统中实现了自旋多体模型的量子模拟。由于离子系统在量子物理学，特别是量子计算与模拟上的重要意义，发明离子阱的Wolfgang Paul获得了1989年的诺贝尔物理奖，第一次把离子技术用于演示量子计算的David Wineland获得了2012年的诺贝尔物理奖，首次提出基于离子量子计算理论方案的Ignacio Cirac和Peter Zoller 也获得了2013年沃尔夫物理奖。

本章我们将简要介绍离子阱的基本物理原理，对基于离子的量子计算与模拟的技术现状做一个回顾，并对其未来的发展进行展望。

## 第二节 离子囚禁与Paul型阱

囚禁离子的目的是将离子与环境隔离开来，成为一个纯净的量子系统。离子是单个带电原子，因此通过电场特别是静电场让离子在其中实现稳定平衡是最为直接的想法。然而稳定平衡点必须是电势场的极小值点，数学上要求电势场在该点处三个空间方向的二阶偏导都小于零。但根据真空麦克斯韦方程，电势场沿三个方向的二阶偏导之和为零，这与我们的要求矛盾，因此仅凭静电场无法实现三维空间中离子的稳定囚禁，必须引入其他形式的场形成束缚。

Paul教授提出利用交变电场实现离子的稳定囚禁，发展起来的装置现称为Paul型阱。离子量子计算与模拟实验均使用Paul型阱[^1]。Paul阱束缚的离子会排成一列，形成线性晶体，可以通过聚焦激光光束独立寻址并相干控制各单个离子。为减少空气分子对囚禁离子的撞击，实验中离子阱放置于超高真空系统中，然后加热原子炉使原子气化后产生原子束，再使用激光束将原子电离为离子。通过控制原子喷射速率及电离强度，可以精确实现单个到成千上万个离子的稳定囚禁。图一显示典型的离子实验装置。

![](/notes/2018/01/28/1.png)
图１  (a) 清华量子信息中心的离子实验系统  (b) 离子阱内部结构，显示出22个离子组成的离子晶体

## 第三节 囚禁离子的相干控制

囚禁离子的量子相干操控的主要奠基人是David Wineland，他因此贡献而获得了2012年诺贝尔物理学奖[^2]。刚束缚的离子在阱中的振动很剧烈，因此需要先将它冷却下来，最常用的方法是基于多普勒效应的激光冷却[^3]。激光光束起到一个类似于摩擦力的效果，离子的动能将逐渐降低下来，然后再通过边带冷却将离子的振动量子态从热态一直冷却到量子基态。

当离子冷却下来进入量子区域后，我们就可以开始进行离子量子比特的初始化与读取，一般通过光泵浦技术来实现。我们会选取三个能级，两个寿命较长的作为量子比特能级，一个寿命很短的作为激发态能级。并且在选取时根据选择定则，保证激发态能级自发辐射后只会落到第一个能级上。然后用频率等于激发态与第二个能级频率差的窄线宽激光照射离子，几微秒后离子就会以百分之百的概率被制备到第一个能级上，从而实现离子量子比特的初始化。读取方法与之类似，只是换取不同的激发态能级，保证自发辐射后离子只会落到第二个能级上。假如离子开始处于第二个能级，那么在激光照射过程中，离子的量子态会来回振荡中并放出大量的自发辐射光子，而通过收集并统计光子数目就可以测量出离子一开始处于第二个能级的概率。通过不断的努力，人们对离子量子比特初始化与读取的保真度都已经近乎完美。

具备了初始化与读取的能力后，对于离子量子比特就可以相干控制。对于量子比特能级差位于微波频段（比如超精细分裂能级）的情形，通过施加可调相位的微波场，可以直接实现任意的单比特量子逻辑门操作。对于能级差位于光学频段的稳定能级，可以借助声光或电光调制器，先通过调控微波实现对窄线宽激光的频率、相位控制，然后用窄线宽激光来调控实现任意的单比特量子逻辑门。

## 第四节 离子量子计算

实现量子计算的关键是在任意一对离子量子比特之间实现纠缠量子逻辑门操作（如受控非门），这需要利用离子间的库仑相互作用，该相互作用体现在离子晶体的振动谱上，量子化后用声子态描述。

Cirac和Zoller在1995年首次提出了基于囚禁离子的通用量子计算方案[^4]，其基本思想是通过振动声子作为数据总线在离子之间传递信息以实现纠缠量子门操作。假定一串离子囚禁在线性离子阱中，当离子的集体振荡被激光冷却到振动基态后，通过对不同的离子施加独立的聚焦激光束，离子的比特量子态分别与振动声子态耦合，然后通过声子态的传递实现任意一对离子间的受控非门。受控非门与前一节提到的单比特量子逻辑门一起构成了一组通用量子逻辑门，通过通用量子逻辑门的组合可以实现任意量子操作，从而用于构造通用量子计算机。

Cirac-Zoller方案要求初始声子处于绝对基态，对环境热噪声的容错能力较差。为克服此问题，Mølmer和Sørensen（及稍后的Milburn）于1999年提出另一种方案来构建受控非门。他们使用正负失谐的双色激光同时照射两个离子，失谐量略小于声子频率。在此过程中一系列的红蓝边带虚能级将产生多条Raman跃迁路径，这些路径干涉后恰好可以实现强度、相位与初始声子态和环境热噪声几乎无关的两比特纠缠操作。只要控制激光开启时间为半个Raman跃迁周期，再插入一系列单比特操作就可以实现两比特受控非门。该方案的纠缠操作中所施加的激光对两个离子完全相同，从而允许人们通过更简单的一束光同时作用于所有离子上实现多比特量子纠缠。

Cirac-Zoller和Mølmer-Sørensen方案仍然有个共同问题，就是都要求激光只与某个单一振动模式耦合，因此必须使用频谱间隔较大的纵向声子模式（线性离子晶体对称轴方向）。然而纵向声子模式的频率很低，对环境热噪声较为敏感，而且离子间距的不均匀性导致不同位置处离子的振动幅度略有不同，这些都会影响方案的速度以及对于多离子的可扩展性。因此Duan研究组于2006年提出使用能量较高且对离子完全对称的所有横向声子模式一起来传递相互作用[^5][^6]。激光与所有横向声子模式总的相互作用非常复杂，但通过最优控制的方法，该系统可严格求解，并通过数值方法求解出合适的控制参数，实现高保真度的量子逻辑门[^5][^6]，该方法称为最优控制方案，具有完全的可扩展性，已成功应用于实验[^7]。现在实验上对于较小系统的量子计算（例如10-20个量子比特以下），一般直接使用Mølmer-Sørensen方案。对20个以上量子比特的离子量子计算系统，因为上述的原因，则必须使用最优控制方案。

离子量子计算系统在实验方面，拥有所有物理系统中多方面的世界记录，包括迄今为止最大的量子纠缠态（薛定谔猫态）的制备[^8]，最高的普适量子逻辑门的保真度[^9]，最长的单量子比特相干时间[^10]，以及最完备的可编程性（任意比特间的连通性）[^11]。

完成一个具有实用意义的量子计算过程往往需要上亿个量子逻辑门操作，为了实现这点，必须提高普适量子逻辑门的保真度，超过容错量子计算的阈值要求，并延长量子存储时间，实现容错量子计算。

早在2011年，奥地利因斯布鲁克大学实验组就制备了14个离子量子比特的最大纠缠态（薛定谔猫态）[^8]。2016年，英国牛津大学实验组利用钙离子的超精细结构作为量子比特，实现了保真度分别为99.9％的两量子比特门和99.9934％的单量子比特门，显著高于容错量子计算所需的99％最小阈值[^9]。同一年里，美国马里兰大学实验组展示了一个五量子比特完全可编程的离子量子计算机，该计算机可以通过执行任意通用量子逻辑门序列来实现任意的量子算法[^11]。2017年，清华大学量子信息中心实验组通过钡离子协同冷却镱离子，并应用动态解耦脉冲来抑制磁场波动和环境噪声，在单量子比特上成功观测到相干时间超过10分钟的量子存储[^10]。

## 第五节 囚禁离子量子模拟

在研究多体物理和材料特性时，物理学家抽象出了基于格点自旋系统的物理模型。它不仅可以用来描述物质磁性和相变现象，而且可以作为连续空间物理高频截断后的近似模型。囚禁离子系统是人们用来模拟格点自旋模型的量子模拟器的主要实现平台。通常每一个囚禁离子代表一个格点自旋，通过离子与激光的相互作用来调节自旋间耦合的形式和强度。

德国马普研究所的Cirac研究组于2004年提出可以利用激光与离子的相互作用在囚禁离子系统中实现有效的量子自旋模型的哈密顿量[^12]，进而通过改变哈密顿量的相互作用强度来模拟量子相变。通过调节控制激光的强度、偏振和失谐，可以令离子受到与自旋态相关的光偶极力的作用，实现各种形式的可控多体自旋模型。在格点自旋模型中，格点的维度和链接性质对系统的物理特性具有非常重要的影响，通过巧妙地调节多模激光场的频率、强度和相位，可以在线型离子阱中产生任意维度、任意链接的格点自旋模型[^13]。

近十年来，在利用离子量子模拟器模拟格点自旋系统的实验方向也取得了丰硕的成果。德国马普研究所的实验组于2008年在包含两个囚禁离子的量子模拟器上实现了横场Ising模型哈密顿量[^14]，并通过调节参数观测到由顺磁态向铁磁态的转变。随后， 马里兰大学Monroe研究组于2010年在包含三个离子的量子模拟器上实现了横场Ising模型，并首次研究了阻挫网络对系统量子行为的影响[^15]。

相变在自然界中普遍存在，是物理学家最为关心的物质变化现象之一。量子相变是经典相变的量子对应，理论上只发生在热力学极限条件下。为了在离子量子模拟器中观测和研究量子相变，人们致力于提高离子量子模拟器中包含的离子数目。2011年，Monroe研究组首先实现了包含9个离子的量子模拟器[^16]，并且观测到随着离子数目的增加，从顺磁态到铁磁态的转变越来越陡峭，初步显示出量子相变的特征。随后，通过连续调节长程相互作用的范围，该研究组在包含16个囚禁离子的量子模拟器中研究了阻挫反铁磁相互作用对量子行为的影响[^17]。最近，该研究组成功地搭建了包含53个囚禁离子的量子模拟器[^18]，并研究了具有长程相互作用的横场Ising模型的非平衡动力学，观测到动力学相变现象。

与经典模拟类似，量子模拟也可大致分为仿真和数字模拟两大类。在仿真模拟实验中，人们在量子模拟器中产生目标哈密顿量，并按照预设方案连续地调节参数，实时地模拟待研究的量子过程。上述对格点自旋模型的量子模拟均属于量子仿真模拟的范畴。另一方面，人们也可以将待研究的量子过程离散化，通过小型量子计算机上系列逻辑门操作来实现模拟目标哈密顿量，这一方式被称为数字量子模拟。

2011年，奥地利Innsbruck大学研究组以数字模拟方式实现了包含5个离子的量子耗散系统模拟器[^19]，其中时间演化被分解为一系列相干和耗散过程。随后，该研究组利用量子耗散系统模拟器研究了量子多体系统的非平衡演化[^20]，并观测到动力学相变的某些特性。2016年，该研究组将基于囚禁离子的数值量子仿真器的应用推广到格点规范理论[^21]，用包含4个囚禁离子的系统模拟了（1+1）维的Schwinger场论模型，该模型描述费米物质和规范波色子之间的相互作用。清华量子信息中心研究组也利用离子的自旋和声子态实验模拟了时间反演[^22]和非平衡态热力学特性[^23]。

## 第六节 离子量子计算的规模化与扩展性

虽然囚禁离子系统已经达到了量子计算的各项基本要求，但要将此系统扩展到包含大量离子，足以解决经典计算机做不了的大规模计算问题，我们还面临着规模化和扩展性的问题。对于囚禁离子量子计算平台的规模集成化，人们提出了不同的架构模型。这些模型的共性是将大规模计算平台划分解为基本模块。最主要的架构模型有两种：即离子输运方案和量子网络方案，离子输运方案中，不同的量子计算模块通过离子在不同阱之间的相干输运来链接，而离子量子网络方案中，不同的计算模块通过光子纠缠通道形成量子计算网络。下面我们分别介绍这两种典型架构。

离子输运架构：离子输运架构由大量相互连通的小型模块离子阱组成[^24]，离子比特在不同离子阱之间相干输运。通过改变模块离子阱的操作电压，我们可以在每个离子阱中束缚少数离子，或者令某个离子在阱间移动。被束缚在任何一个离子阱中的离子都可以按照现有单个离子阱的技术进行操作，同时离子的阱间移动将这些小型离子阱链接成一个大规模的量子计算系统。在这一架构中，组成量子网络的小型离子阱被分为记忆区和操作区。携带量子信息的离子被贮藏在记忆区。当进行逻辑操作时，相关离子首先被移动到操作区，进行逻辑操作后再回记忆区。

美国国家标准与技术研究所的Wineland研究组于2014年验证了初步具备离子输运架构的实验系统[^25]，即在被分别束缚在两个独立的势阱中的囚禁离子之间产生可调的量子逻辑门操作。将来这一基本模块有可能可以通过微加工技术扩展成为二维量子网络，从而构建基于囚禁离子的大规模量子计算平台。

离子量子网络架构：构建基于囚禁离子的大型量子网络的另一种可能途径是通过概率性的离子—光子映射来链接各个小型分布式离子阱，即通过以光子为媒介的相互作用来远距离耦合囚禁在不同离子阱中的离子，这种架构最早由文献[^26]提出。具体而言，在两个离子都处在激发态，有可能放出光子的情况下，测得一个光子而不区分其来自哪个离子，这种测量会将两个离子投影到量子纠缠态。在这种情况下，光子损耗只影响成功率，而不降低纠缠保真度。这种架构通过概率性的远距离纠缠和确定性的局域量子门来构造确定性的远距离量子门，以实现规模化量子计算网络。实验方面，密歇根－马里兰大学的研究组在2004年成功地观测到单个囚禁离子和单个光子的纠缠[^27]，实现了存储比特和通信量子比特之间的量子态传输，2007年成功产生了远程不同量子阱中量子比特之间的纠缠[^28]。2014年，马里兰大学研究组演示了通过辅助量子总线来传播量子纠缠的模块化量子网络构建方法的最小模型[^29]。关于这一架构理论和实验方面的进展可以参见Duan和Monroe的综述文章[^30]。

## 第七节 总结与展望

囚禁离子系统是最有希望实现大规模通用量子计算机和大型量子模拟器的物理平台之一，它既可以作为一个独立的多比特量子计算节点完成大部分量子计算、量子存储等任务，也可以借助离子-光子接口实现多个可扩展节点间的长程量子纠缠与量子网络通信。离子阱几乎是唯一同时满足全部“DiVincenzo”判据的系统，“DiVincenzo”判据描述了实现量子计算机和量子网络所必须满足的条件。

经过数十年的发展，基于囚禁离子系统的量子计算和量子模拟在理论和实验上均有巨大进展。其中单个量子模拟器中可相干操作的量子比特数达到53个，已经能够初步揭示无法通过经典方法计算模拟的量子特性和动力学行为。通过开发芯片离子阱等新型囚禁技术，囚禁离子系统还可以与其他类型的量子计算平台如超导量子电路系统相结合，发挥各自的优势，实现更为强大的混合型量子计算平台。有关大规模量子网络架构的理论也日趋完善，相应的基本模块和最小模型正在实验室中建成和测试。与此同时，人们仍然致力于在理论和实验技术两方面提高系统的各项量子指标，相信在不远的将来，在基于囚禁离子系统的量子模拟和量子计算领域有望出现能够展示量子优越性的大规模通用量子计算和量子仿真平台。

[^1]:	"W. Paul, Electromagnetic traps for charged and neutral particles. Reviews of Modern Physics 62, 531-540 (1990)."
[^2]:	D. J. Wineland, Nobel Lecture: Superposition, entanglement, and raising Schr\"odinger's cat. Reviews of Modern Physics 85, 1103-1114 (2013).
[^3]:	D. Leibfried, R. Blatt, C. Monroe, D. Wineland, Quantum dynamics of single trapped ions. Reviews of Modern Physics 75, 281-324 (2003).
[^4]:	J. I. Cirac, P. Zoller, Quantum Computations with Cold Trapped Ions. Physical Review Letters 74, 4091-4094 (1995).
[^5]:	S.-L. Zhu, C. Monroe, L. M. Duan, Trapped Ion Quantum Computation with Transverse Phonon Modes. Physical Review Letters 97, 050505 (2006).
[^6]:	Z. Shi-Liang, C. Monroe, L. M. Duan, Arbitrary-speed quantum gates within large ion crystals through minimum control of laser beams. Europhysics Letters 73, 485 (2006).
[^7]:	K. Kim et al., Entanglement and Tunable Spin-Spin Couplings between Trapped Ions Using Multiple Transverse Modes. Physical Review Letters 103, 120502 (2009).
[^8]:	T. Monz et al., 14-Qubit Entanglement: Creation and Coherence. Physical Review Letters 106, 130506 (2011).
[^9]:	C. J. Ballance, T. P. Harty, N. M. Linke, M. A. Sepiol, D. M. Lucas, High-Fidelity Quantum Logic Gates Using Trapped-Ion Hyperfine Qubits. Physical Review Letters 117, 060504 (2016).
[^10]:	Y. Wang et al., Single-qubit quantum memory exceeding ten-minute coherence time. Nature Photonics 11, 646-650 (2017).
[^11]:	S. Debnath et al., Demonstration of a small programmable quantum computer with atomic qubits. Nature 536, 63 (2016).
[^12]:	D. Porras, J. I. Cirac, Effective Quantum Spin Systems with Trapped Ions. Physical Review Letters 92, 207901 (2004).
[^13]:	S. Korenblit et al., Quantum simulation of spin models on an arbitrary lattice with trapped ions. New Journal of Physics 14, 095024 (2012).
[^14]:	A. Friedenauer, H. Schmitz, J. T. Glueckert, D. Porras, T. Schaetz, Simulating a quantum magnet with trapped ions. Nature Physics 4, 757 (2008).
[^15]:	K. Kim et al., Quantum simulation of frustrated Ising spins with trapped ions. Nature 465, 590 (2010).
[^16]:	R. Islam et al., Onset of a quantum phase transition with a trapped ion quantum simulator. Nature Communications 2, 377 (2011).
[^17]:	R. Islam et al., Emergence and Frustration of Magnetism with Variable-Range Interactions in a Quantum Simulator. Science 340, 583-587 (2013).
[^18]:	J. Zhang et al., Observation of a many-body dynamical phase transition with a 53-qubit quantum simulator. Nature 551, 601 (2017).
[^19]:	J. T. Barreiro et al., An open-system quantum simulator with trapped ions. Nature 470, 486 (2011).
[^20]:	P. Schindler et al., Quantum simulation of dynamical maps with trapped ions. Nature Physics 9, 361 (2013).
[^21]:	E. A. Martinez et al., Real-time dynamics of lattice gauge theories with a few-qubit quantum computer. Nature 534, 516 (2016).
[^22]:	X. Zhang et al., Time reversal and charge conjugation in an embedding quantum simulator. Nature Communications 6, 7917 (2015).
[^23]:	S. An et al., Experimental test of the quantum Jarzynski equality with a trapped-ion system. Nature Physics 11, 193 (2015).
[^24]:	D. Kielpinski, C. Monroe, D. J. Wineland, Architecture for a large-scale ion-trap quantum computer. Nature 417, 709 (2002).
[^25]:	A. C. Wilson et al., Tunable spin–spin interactions and entanglement of ions in separate potential wells. Nature 512, 57 (2014).
[^26]:	L. M. Duan, B. B. Blinov, D. L. Moehring, C. Monroe, Scalable trapped ion quantum computation with a probabilistic ion-photon mapping. Quantum Information & Computation 4, 165-173 (2004).
[^27]:	B. B. Blinov, D. L. Moehring, L. M. Duan, C. Monroe, Observation of entanglement between a single trapped atom and a single photon. Nature 428, 153 (2004).
[^28]:	D. L. Moehring et al., Entanglement of single-atom quantum bits at a distance. Nature 449, 68 (2007).
[^29]:	D. Hucul et al., Modular entanglement of atomic qubits using photons and phonons. Nature Physics 11, 37 (2014).
[^30]:	L. M. Duan, C. Monroe, Colloquium: Quantum networks with trapped ions. Reviews of Modern Physics 82, 1209-1224 (2010).
