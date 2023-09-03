> 本文由 [简悦 SimpRead](http://ksria.com/simpread/) 转码， 原文地址 [blog.csdn.net](https://blog.csdn.net/zimuzi2019/article/details/126634216)

内容基于[中国大学 MOOC](https://so.csdn.net/so/search?q=%E4%B8%AD%E5%9B%BD%E5%A4%A7%E5%AD%A6MOOC&spm=1001.2101.3001.7020) 的 2023 考研计算机网络课程所做的笔记。

感谢 LY，他帮我做了一部分笔记。其中第四章网络层各小节的顺序稍微做了下调整，和上课老师讲的先后顺序稍有不同，但内容是完整的。

课程内容和西电平时讲课的内容大致重合，西电可能会多讲一点内容，但多讲的考试基本不是重点，自己对照任课老师的课件补一下即可。考试要复习的内容看上去很多，但最后考的都很基础，基本不会考特别偏的知识。

王道的计网讲的中规中矩，听课听完可能会有点懵，建议快速过一遍内容后就开始刷题来加深理解。

其他章节的链接如下：

[计算机网络笔记（王道考研） 第一章：计算机网络体系结构](https://blog.csdn.net/zimuzi2019/article/details/126634216)

[计算机网络笔记（王道考研） 第二章：物理层](https://blog.csdn.net/zimuzi2019/article/details/126634063)

[计算机网络笔记（王道考研） 第三章：数据链路层](https://blog.csdn.net/zimuzi2019/article/details/126634296)

[计算机网络笔记（王道考研） 第四章：网络层](https://blog.csdn.net/zimuzi2019/article/details/126634461)

[计算机网络笔记（王道考研） 第五章：传输层](https://blog.csdn.net/zimuzi2019/article/details/126634511)

[计算机网络笔记（王道考研） 第六章：应用层](https://blog.csdn.net/zimuzi2019/article/details/126634551)

[其他各科笔记汇总](https://blog.csdn.net/zimuzi2019/article/details/126227917)

[计算机网络](https://so.csdn.net/so/search?q=%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C&spm=1001.2101.3001.7020)体系结构
==================================================================================================================

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/Screen%20Shot%202022-07-22%20at%2014.24.42.png)

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220830211342463.png)

概念 & 功能
-------

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220830205555199.png)

### 计算机网络的概念

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220830205751556.png)

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220830205817027.png)

### 计算机网络的功能

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220830205916133.png)

> 资源共享 —— 如网络打印机，只要主机和打印机都连在同样一个网络内，同时给打印机配置一个固定的静态 IP 地址，手机就可以通过网络和打印机相连接，实现所有人对该打印机硬件资源的共享

> 提高可靠性和负载均衡都是分布式处理引申出来的功能

### ~计算机网络的发展~

第一阶段

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220830210248929.png)

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220830210339385.png)

第二阶段 —— 三级结构

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220830210424117.png)

第三阶段 —— 多层次 ISP 结构

沿用第二阶段的三层结构，把网络的管理权利分散，由 ISP 进行网络的分配以及服务的提供等等，我们交的网费就是给 ISP 的服务费

全世界有一个很大的 IP 池，由因特网管理机构来管理。如果 ISP 供应商要给用户提供服务分配 IP，它会从 IP 池里要到一个网段的 IP 地址然后再分给用户。ISP 会给这一区域范围内的用户分配 IP 地址

> 假如你的 IP 地址由四川电信分配，也可以享受北京电信的服务，只不过它不是直接管理你的 ISP
> 
> 如下载一些资源的时候会看到很多的选项，如四川电信、四川移动、北京电信等等，这些其实就是根据 ISP 来选择的，选择别的运营商进行下载就可能速度比较慢

只要每一个本地 ISP 都安装路由器连接到了地区 ISP，而地区 ISP 也有路由器连接到主干 ISP 就可以完成因特网当中所有的数据分组转发的任务

随着流量的激增，人们对于网络的要求也越来越高，就开始研究怎么更快地转发分组。因此就诞生了 IXP，就可以允许图中的两个网络直接相连而不用再需要第三个网络来转发分组了

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220830210625244.png)

组成 & 分类
-------

### 计算机网络的组成

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220830210801985.png)

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220830210820386.png)

> 边缘部分用户直接使用，核心部分为边缘部分服务
> 
> 边缘部分：由一系列的端系统组成，这些端系统包括一些计算机，服务器，甚至还可以包括非常小的网络摄像头，这些都是边缘部分。通过核心部分提供服务，边缘部分才能实现端系统与端系统之间的通信
> 
> 核心部分：为边缘部分服务，包括连接起来的路由器，一些中间设备还有一些网络
> 
> 核心部分和边缘部分连接在一起就构成了计算机网络

> 端系统指的是在边缘的末端系统，端系统之间的通信强调的是进程之间的通信。两个端系统之间的进程通信主要包括两种方式，分别是 C/S 方式和 P2P 方式

> 通信子网 —— 把信息从一个主机传到另一个主机
> 
> 资源子网 —— 提供共享其他计算机上的各种资源（硬件、软件和数据资源等等）的服务
> 
> 可以理解为资源子网是对数据进行封装和处理，通信子网把数据送上路，中间的传输层弥补资源子网要求的服务和网络层提供的服务之间的差距，并且向高层用户屏蔽通信子网当中的一些细节

### 计算机网络的分类

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220830211208800.png)

> 局域网和广域网的区别不仅仅是它们在地理范围上的差别，更重要的是它们使用什么技术

> 报文交换和分组交换使用存储转发技术，不会一直占用线路。简单来说一整个文件就是一个报文，把报文切开成一个个分组

> 拓扑结构中的节点可以是路由器，交换机这些中间设备，也可以是端系统当中的主机。线则是抽象的通信链路

### ~标准化工作及相关组织~

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220830211548746.png)

标准化工作

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220830211711717.png)

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220830211733477.png)

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220830211805311.png)

标准化工作的相关组织

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220830211900430.png)

性能指标
----

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220830211936413.png)

### 速率

> 表示存储量的时候是以 2 为底，例：$1KB = 2 ^ {10}B；1MB = 2 ^ {10}KB $
> 
> 表示速率的时候是以 10 为底，例： 1 k b / s = 1 0 3 b / s ； 1 M b = 1 0 3 k b / s 1kb/s = 10 ^ 3b/s；1Mb = 10 ^ 3kb/s 1kb/s=103b/s；1Mb=103kb/s

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220830212213173.png)

### 带宽

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220830212239806.png)

> 注意带宽指的是在链路入口的位置发送数据的速率，而不是在链路上传播的速率

### 吞吐量

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220830212644783.png)

> 带宽≈吞吐量

### 时延

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220830212737480.png)

> 高速链路指的是发送速率提高，它并不会影响电磁波传播速度

> 排队时延和处理时延基本忽略不计，在例子中这两个时延发生在路由器中

### 时延带宽积

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220830213016541.png)

> 发送端第一个比特到达接收端时，发送端共发送了多少比特

### 往返时延 RTT

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220830213226134.png)

> 不考虑发送时延
> 
> RTT 越大，收到确认前可发送的数据越多

> 如何测算 RTT？在终端输入 ping 命令，后面加 IP 地址或域名

### 利用率

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220830213351865.png)

分层结构 协议 接口 服务
-------------

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220830233237365.png)

### 为什么要分层？

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220830214233757.png)

> 所谓激活就是发出一些命令，保证要传送的数据能够在通路上正确地发送以及接收。也就是先把路清一下，确定好这条路是可以通过的

### 怎么分层？

分层的基本原则：

1.  各层之间相互独立，每层只实现一种相对独立的功能
2.  每层之间界面自然清晰，易于理解，相互交流尽可能少
3.  结构上可分割开。每层都采用最合适的技术来实现
4.  保持下层对上层的独立性，上层单向使用下层提供的服务
5.  整个分层结构应该能促进标准化工作

### 分层结构

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220830233100899.png)

> 只有对等实体之间才有协议，规定两对等实体实现的功能
> 
> 接口存在于相邻两层之间，每层之间的接口一定要说明这两层之间是如何进行服务的，该层如何实现其所提供的服务对上一层透明

> 中间层次为上一层提供服务，还包含下一层包括底下所有层次的服务的总和（该层自己也能使用）

> 每一层的 PDU 作为下一层的 SDU，加上该层的 PCI 得到这一层的 PDU

### 概念总结

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220830233216362.png)

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220830234423490.png)

OSI 参考模型
--------

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220831004727659.png)

### ISO/OSI 参考模型怎么来的

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220831000145520.png)

> 异构网络系统 —— 不同网络体系结构，不同厂家商家的网络

### ISO/OSI 参考模型

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220831001617227.png)

### ISO/OSI 参考模型解释通信过程

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220831001856504.png)

> 中间系统最多能到网络层，比如说路由器只需要经过 3 层，像交换机和网桥这些链路层上的一些设备可能只需要经过下面的 2 层。而其他的端系统是 7 层都要经过的

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220831001928735.png)

> 注意数据链路层不仅加首部也加尾部。物理层不会对数据再做其他额外的处理，而是形成 bit 流序列后再放到物理传输介质上进行传输

### 应用层

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220831002804553.png)

### 表示层

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220831002857593.png)

> 数据格式变换 —— 不同主机的编码以及表示方式都可能不太一样，上图中把 bit 流的形式转换成. jpg 的数据格式

### 会话层

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220831002938632.png)

> 建立、管理、终止会话 —— 在网页上看电影时，主机和电影服务器之间建立的连接就是一个会话，它不会影响主机和其他的网页窗口所建立起来的会话，会话彼此之间是相互独立而不影响的

> 打开网页：建立会话 关闭网页：终止会话

### 传输层

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220831003017882.png)

> 上面 4 层是端到端通信，下面 3 层都是点到点通信

> 可靠传输，不可靠传输 —— 可靠传输对于每一个接收到的报文段，接收端都会返回一个确认信息给发送端表示已接收，发送端收到确认信息之后才能够继续往下发送。而不可靠传输则不需要建立连接和使用确认机制

### 网络层

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220831003114673.png)

### 数据链路层

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220831004335652.png)

### 物理层

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220831004400531.png)

> 物理层把 bit 流转成电信号的形式然后放到链路上面传输即可，不需要对数据进行处理

> 单工：单向，一个人发送，另一个人接收。发送方和接收方不变
> 
> 半双工：两个人都可以作为发送方和接收方，但同一时间只能有一个人发送
> 
> 双工：可以双向同时发送信息

TCP/IP 模型 & 5 层参考模型
-------------------

### OSI 参考模型与 TCP/IP 参考模型

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220831013449990.png)

先诞生 TCP/IP 协议栈，然后把协议栈分层成 TCP/IP 参考模型

网络接口层合并了数据链路层和物理层合并，只相当于是与物理网络的接口，TCP/IP 参考模型并没有规定它其中的一些细节，只是指出主机必须通过某一些协议与网络连接，然后才能够在网络上面传递 IP 分组

网际层和和 OSI 参考模型的网络层功能差不多，它进行路由选择，把数据报和分组发给各个网络，是 TCP/IP 参考模型当中最关键的部分

传输层和 OSI 参考模型的也是一样的，都会实现端到端通信

应用层把表示层和会话层都纳入，形成一个包含所有高层协议的较大层次

相同点：

![](https://img-blog.csdnimg.cn/c8fcdd64981943a785464c14800fddf4.png)

> 异构网络互联 —— 实现不同厂家生产的设备进行相同的通信

不同点：

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220831013627591.png)

> IP 协议面向无连接

> TCP/IP 看重网络层，因此无连接

### 五层参考模型

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220831014303197.png)

### 5 层参考模型的数据封装与解封装

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220831014409282.png)