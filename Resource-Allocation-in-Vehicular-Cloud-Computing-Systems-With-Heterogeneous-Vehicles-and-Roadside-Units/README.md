# Mobile-Edge-Computing

## An SMDP-Based Resource Allocation in Vehicular Cloud Computing Systems
[文章链接](https://ieeexplore.ieee.org/document/7277060)

### Abstract
车辆自组织网络有望显着提高交通安全性和运输效率，同时提供舒适的驾驶体验。然而，所连接的车辆的可用通信，存储和计算资源未得到充分利用以满足智能运输系统的服务要求。车载云计算（VCC）是一种很有前景的方法，它利用云计算的优势并将其应用于车载网络。在本文中，我们提出了一种最优计算资源分配方案，以最大化VCC系统的总长期预期回报。系统奖励是通过考虑VCC系统的收入和成本以及可用资源的可变性特征得出的。然后，将优化问题表示为具有VCC系统的定义的状态空间，动作空间，奖励模型和转移概率分布的无限时域半马尔可夫决策过程(SMDP)。我们利用迭代算法来开发描述在特定状态下必须采取哪种动作的最优方案。数值结果表明，基于SMDP的方案可以在可接受的复杂度内获得显着的性能增益。







## Resource Allocation in Vehicular Cloud Computing Systems With Heterogeneous Vehicles and Roadside Units

[文章链接](https://ieeexplore.ieee.org/document/7891877)



### Abstract

### Introduction
许多国家都在努力实现智能交通系统（ITSs）的实际应用。

提出了车载自组织网络（VANET），用于提供车辆之间的网络连接和实时信息共享的能力。此外，VANET已与传感器和路边单元（RSU）集成，用于与道路上的车辆通信，以促进交通安全[2]，[3]。 最近，已经提出了用于将VANET与云计算技术集成的车辆云计算（VCC）系统。VCC系统的计算和通信能力为公路用户提供了实用性和便利性，因此相关研究最近受到了很多关注[4]，[5]。

在VANET中，每辆车都配备了车辆设备（VE），其性能类似于带有网络接口的小型计算机[6]。通过VE，车辆可以与其他VE，RSU，传感器甚至其他车辆通信。 通过交换各自的已知信息和从传感器收集的信息，可以促进驾驶安全性，并且可以减少驾驶到目的地所消耗的时间。引入云计算系统使得VE和RSU的能力几乎与小型计算机相当[7]，[8]。这种VCC网络不仅提供传输数据的能力，还提供计算服务，例如到目的地的最短路径，最佳驾驶速度等。

### System Framework
![image](https://github.com/qpointwang/Mobile-Edge-Computing/blob/master/Resource-Allocation-in-Vehicular-Cloud-Computing-Systems-With-Heterogeneous-Vehicles-and-Roadside-Units/deng1-2690961-large.gif)
#### A. Cloud Architecture
本文定制了[16]和[28]中提出的系统来提出我们的VCC系统，如图1所示。系统中的云架构分为两层：1）远程云（RC）和2）车载云（VC）。RC由多个强大的计算资源组成，因此可以通过RC计算有效地处理任何服务。 与以前的环境不同，本文考虑了VC中的异构车辆。VC由一定范围内的多个异构车辆的VE和具有计算资源的多个RSU构成。为了量化VC中的计算资源，由车辆和RSU提供的计算资源根据资源单元（RU）的数量来测量。 来自资源池的这些RU，由集中式VC系统控制和分配。VC的计算能力取决于资源池中的RU数量。  
由于本文涉及的车辆的异质性，这些异构车辆中的VE提供不同数量的RU。例如，在图1中，假设每个黑色车辆具有较弱的计算能力，仅向VC提供一个RU;而每个蓝色车辆（可能成本更高）具有提供2个RU的强大计算能力。 假设每个RSU提供2个RU。 然后，图1中的2个RSU和5个车辆（其中2个为蓝色，3个为黑色）在VC资源池中提供11个RU。

#### B. Handling the Service Requests From Vehicles
考虑车辆通过VC服务范围，并向VC发出服务请求。然后，VC响应有两种情况。 在第一种情况下，为了直接处理该请求，VC在资源池中分配多个RU来计算所请求的服务。分配的RU数直接影响完成此请求的时间。在第二种情况下，VC将此请求传送给RC以处理它（参见图1）。通常，RC具有强大的计算资源，因此可以立即完成此服务请求。据推测，RC几乎不消耗任何时间。虽然VC不使用任何RU计算，但它消耗一点的功率和时间。

#### C. Assumptions and Notations
RSU的功率由有线电力支持，因此RSU应具有无限寿命，VCC系统也是如此。VCC系统的服务范围大小取决于动态连接到VC的车辆的地理分布。考虑VC中RSU的数量和位置是固定的，VC和RSU之间的连接是确定的。 因此，VC的服务范围基于其与RSU的连接。  
设\${R}\$表示VCC系统中的RSU数量。假设每个RSU都可以提供 \$\textit{T}\_{R}\$。为了保持操作VCC系统的稳定性，假设VCC系统服务的车辆数量具有上限，其由\${K}\$表示。设\${M}\$表示当前VC资源池中可用的RU数。\${M}\$随时间变化，因为它取决于动态通过VCC服务范围的车辆数量。  
VCC系统服务的车辆数量是动态的。 之前的工作假设均匀车辆的到达和离开数均遵循泊松分布。 然而，本文考虑了车辆的异质性，即车辆是不同类型的。因此，本文假设每种类型的车辆的到达和离开的数量都遵循泊松分布。令\$\lambda_{j}\$ (resp., \$\mu_{j}\$ )表示向VC提供j个RU的类型的车辆的到达（分别，离开）的数量。类似地，每辆车的到达和离开服务请求的数量也遵循泊松分布。并且，这两个数字分别由\$\lambda_{p}\$ 和 \$\mu_{p}\$表示。请注意，下标p是符号，而不是索引。  
因此，RU完成服务请求所消耗的平均时间为1/\$\mu_{p}\$ 。本文假设在每个单位时间完成的服务请求数量随着处理这些请求的RU数量呈指数增长。 例如，2个RU完成的服务请求数为\$2\mu_{p}\$ ; 并且两个RU完成服务请求所消耗的平均时间是1/(\$2\mu_{p}\$ ).。

#### D. System State Setting
在应用SMDP解决相关问题之前，我们需要建立VCC系统状态的表示。所有这些状态的集合表示为\$S=\{s|s=(n_{1} ,n_{2} ,\ldots ,n_{N_{R}} ,V_{1} ,V_{2} ,\ldots ,V_{S_{R}} ,e)\}\$ 它由以下三个部分组成。