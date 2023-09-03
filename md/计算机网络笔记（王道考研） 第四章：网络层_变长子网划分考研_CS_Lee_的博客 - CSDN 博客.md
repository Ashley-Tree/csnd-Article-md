> 本文由 [简悦 SimpRead](http://ksria.com/simpread/) 转码， 原文地址 [blog.csdn.net](https://blog.csdn.net/zimuzi2019/article/details/126634461)

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

网络层
===

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220822160250007.png)

网络层功能概述
-------

### 网络层

主要任务是把分组从源端传到目的端，为分组交换网上的不同主机提供通信服务

网络传输单位是数据报

> IP 数据报过大就会进行分片，分片后的小单位即网络层的传输单元分组

功能一：路由选择和分组转发 最佳路径

功能二：异构网络互联

功能三：拥塞控制

若所有结点都来不及接受分组，而要丢弃大量分组的话，网络就处于拥塞状态。因此要采取一定措施，缓解这种拥塞

解决拥塞的方法：

*   开环控制：静态。在网络开始工作前就考虑所有能够产生拥塞的因素进行预先控制
*   闭环控制：动态。网络运行起来后自动调整

路由算法及路由协议
---------

### 路由算法

路由协议使用路由算法算出最佳路由填入路由表的每一个表项

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220822193434166.png)

### 路由算法的分类

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/Screen%20Shot%202022-08-03%20at%2011.32.59.png)

> 链路费用（路径代价）即路由器的跳数

### 分层次的路由选择协议

产生原因：

1.  因特网的规模很大。如果让所有的路由器都知道所有的网络如何到达，每个路由器的路由表都会异常庞大，处理起来很耗时
2.  许多单位不想让外界知道自己的路由选择协议，但还是想连入因特网

将整个因特网分成许多自治系统 AS，AS 外部和内部互相看不到使用的协议

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/Screen%20Shot%202022-08-03%20at%2011.39.14.png)

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/Screen%20Shot%202022-08-03%20at%2011.40.48.png)

> 网关≈路由器

RIP 协议与距离路由算法
-------------

RIP 和 OSPF 使用的路由算法不同（RIP —— 距离向量路由算法，OSPF —— 链路状态路由算法），适用的网络大小不同（RIP —— 较小网络，OSPF —— 较大网络）

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220822230503514.png)

### RIP 协议

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220822214448970.png)

> 直接交付：路由器和目的网络直接相连

### RIP 协议和谁交换？多久交换一次？交换什么？

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220822214603216.png)

### 距离向量算法

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220822214938028.png)

> 之所以要替换是因为路由表的更新要以最新消息为准

练习 1：

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220822215904253.png)

练习 2：

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220822215950391.png)

### RIP 协议的报文格式

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220822220035208.png)

> 不需要记忆报文的格式以及相应字段。只需要注意到 RIP 是应用层协议，封装好的 RIP 报文塞到 UDP 数据报中传送，并且一个报文最多可以传送 25 条路由表项信息

### RIP 协议好消息传得快，坏消息传得慢

RIP 的特点：当网络出现故障时，要经过比较长的时间（例如数分钟）才能将此信息传送到所有的路由器，” 慢收敛 “

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220822221921715.png)

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220822221950079.png)

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220822221844445.png)

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220822221815182.png)

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220822221735081.png)

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220822221659711.png)

OSPF 协议及链路状态算法
--------------

### OSPF 协议

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220822231035998.png)

> 链路状态协议≈链路状态算法

> 注意这里链路的度量 / 代价和之前讲的距离向量不一样，不是跳数

### 链路状态路由算法

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220822231617822.png)

### OSPF 区域

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220822232408212.png)

> 主干区域的标识符规定为 0.0.0.0，负责连通其他下层区域

> 主干区域当中的路由器都是主干路由器，上图中 R 3 , R 4 , R 7 R_3,R_4,R_7 R3​,R4​,R7​既是区域边界路由器也是主干路由器

采用分层次划分区域的方法虽然使得交换信息的种类增多，同时使 OSPF 协议更加复杂，但这样可以使得每个区域内部交换路由信息的通信量大大减小，因而 OSPF 协议能够适用于规模较大的自治系统

### OSPF 分组

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220822232446811.png)

考纲上 OSPF 是网络层协议（也有人说是传输层协议，因为相当于是传输层的数据单元放到网络层的数据部分进行封装）

### OSPF 其他特点

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220822232717349.png)

可以看这个视频 [https://www.bilibili.com/video/BV1YV41127U5](https://www.bilibili.com/video/BV1YV41127U5) 作为补充

BGP 协议
------

### BGP 协议

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220822233314390.png)

> 配置 BGP 时，每个 AS 的管理员都要选择至少一个路由器作为 AS 的 BGP 发言人。一般来说两个 BGP 发言人都是通过一个共享的网络连接在一起。BGP 发言人往往是 BGP 边界路由器

> BGP 发言人既使用 BGP 协议，也使用 AS 内部使用的内部网关协议。它既要清楚到达其他 AS 内的子网应该经过哪几个 AS，同时也要清楚外来分组在 AS 内下一跳应该走哪里

### BGP 协议交换信息的过程

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220822234908897.png)

> 上图即是一个 BGP 发言人构造出的树形结构的 AS 连通图

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220822235251885.png)

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220822235306181.png)

### BGP 协议报文格式

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220815213520074.png)

### BGP 协议特点

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220815213527367.png)

### BGP-4 的四种报文

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220815213532779.png)

> UPDATE 最常用

> 连接指 TCP 连接

三种路由协议比较：

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220823000402971.png)

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220823000331796.png)

IP 数据报格式
--------

### TCP/IP 协议栈

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220823133252247.png)

> ARP 协议为 IP 协议服务。IP 协议也要为 ICMP，IGMP 两个协议服务

### IP 数据报格式

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220823133638881.png)

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/Screen%20Shot%202022-08-03%20at%2011.57.41.png)

*   版本：IPv4 / IPv6?
    
*   首部长度：单位是 4B（4 字节），最小为 5
    
*   区分服务：指示期望获得哪种类型的服务
    
    > 比如想要优先发送某数据报，要强调数据报的优先级就在这进行规定。
    > 
    > 在实际应用中很少用
    
*   总长度：占 16bit，单位为 1B，表明整个 IP 数据报的长度
    
    > 总长度的最大值为 2 16 − 1 = 65535 B 2^{16}-1=65535B 216−1=65535B。但实际上不会达到，因为长度过大就要进行分片以满足数据链路层 MTU 的要求
    
*   标识、标志、片偏移：与 IP 数据报的分片有关
    
*   生存时间（TTL）：IP 分组的保质期。经过一个路由器 - 1，变成 0 则丢弃
    
*   协议：数据部分的协议  
    ![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/Screen%20Shot%202022-08-03%20at%2012.06.55.png)
    
*   首部检验和：只检验首部
    
    > 使用二进制求和方法检验，具体不要求
    > 
    > 数据报每经过一个路由器，路由器都要重新计算首部检验和，因为一些字段（如生存时间、标志、片偏移等）都可能发生变化，需要通过首部检验和检验发生变化之后 IP 数据报是否出错，如果出错就丢弃
    
*   源地址和目的地址：32 位
    
*   可选字段： 0 ∼ 40 B 0\sim40B 0∼40B，用来支持排错、测量以及安全等措施
    
*   填充：全 0，把首部补成 4B 的整数倍
    

IP 数据报分片
--------

### 最大传送单元 MTU

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220823140656372.png)

> MTU 不算头尾

> 过长但是 IP 数据报不同意分片则无法往下传递，就会返回 ICMP 差错报文

### IP 数据报格式补充

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220823141542308.png)

> 只有 DF=0，MF 才有意义

> 相对位置指距原数据报数据部分开始位置有多远

例题：

> 原数据报数据部分的第一个字节称之为 0 字节，后面依次是 1 字节、2 字节 …

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220823142808787.png)

IPv4 地址
-------

### IP 地址

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220823154042869.png)

> 并不是一个 IP 地址就标识一个主机，一个主机可以有很多个接口（比如分别用于有线上网的有线接口和无线上网的无线接口）。路由器可以连接很多个主机和路由器，这样一个路由器就会有很多个接口，每一个接口都会分配一个唯一的 IP 地址

### IP 编址的历史阶段

分类的 IP 地址 → \to → 子网的划分 → \to → 构成超网（无分类编址方法）

### 互联网中的 IP 地址

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220823154116438.png)

橘色区域都是路由器的一个接口所连接的一些主机以及链路层设备（如网桥）构成的一个局域网，每个局域网也会用一个主机号全 0 的 IP 地址来标识。同属一局域网范围的主机以及设备 IP 地址网络号相同，主机号不同

绿色区域称之为无编号网络 / 无名网络，之所以叫网络是因为这个网络当中有 IP 地址，但是这个网络是由一段连线构成的

### 分类的 IP 地址

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220823155105058.png)

### 特殊 IP 地址

这一系列 IP 地址不能用于标识主机或者路由器的具体接口，无法分配给主机

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220823155427024.png)

> 网络号全 0，主机号全 0：表示本网范围内的这台主机，如果一台主机在发送分组时不清楚自己的 IP 地址就填上全 0
> 
> 网络号全 0，主机号特定：全 0 网络号表示本网络
> 
> 网络号全 1，主机号全 1：不可以标识某一个主机或者路由器的接口，只能作为目的地址使用，向本网内的所有主机发送广播分组。路由器隔离广播域不转发分组
> 
> 拥有环回地址的数据报永远离开主机，不会进入到网络当中

### 私有地址

把这些地址放到互联网上是无效的，路由器不认。这些地址只适用于在内部网络当中使用，比如一个学校一个单位的内部网络使用这些地址

内部 IP 地址和外部进行通信需要借助 NAT 技术

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220823160858227.png)

> 网段个数指可以分配多少个网络号

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220823162551242.png)

> 2 7 − 2 2^7-2 27−2：网络号全 0 表示本网络，网络号 127 表示环回地址，均不能使用
> 
> 2 24 − 2 2^{24}-2 224−2：主机号全 1 表示广播地址，主机号全 0 和全 1 均不能使用

网络地址转换 NAT
----------

### 私有 IP 地址 / 本地 IP 地址

只可以在本地网、专用网当中使用，在外网、因特网当中是无效的

广域网当中的路由器以及其他的主机无法识别这些 IP 地址，路由器对目的地址是私有 IP 地址的数据报一律不进行转发

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220823163222061.png)

本地 IP 地址跟因特网上的主机进行通信需要 NAT 技术

### 地址转换 NAT

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220823163558510.png)

> WAN 端：广域网端，外网端
> 
> LAN 端：局域网端，内网端，本地网端

所有使用本地地址的主机在与外界通信时都要经历 NAT 路由器的地址转换

这些主机如果要把自己的数据发到网上去就要用 NAT 路由器的外部全球 IP 地址，要给本地网当中的主机发送数据 IP 数据报当中的目的地址也填 NAT 路由器的外部全球 IP 地址，由 NAT 路由器再分发给具体的主机

子网划分和子网掩码
---------

### 子网划分

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220823201848658.png)

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220823201900314.png)

> 子网号可以 1 位都没有，但是至少要留 2 位作为主机号分配给主机

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220823203514744.png)

当从外部发送 IP 分组给本单位某一个子网的某一台主机时，路由器需要从收到的 IP 分组当中提取出目的 IP 地址，进而根据目的 IP 地址判断是应该发给本单位的哪个子网

### 子网掩码

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220823204129940.png)

例题 1：

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220823205459651.png)

> 同样的 IP 地址和不同子网掩码可以相与得出相同的网络地址，但是这几种掩码所达到的效果不同，它们各自子网号和主机号所占的位数不一样，可以划分的子网个数以及每一个子网当中可以使用的最大主机数也不同

例题 2：

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220823205529592.png)

### 使用子网时分组的转发

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/Screen%20Shot%202022-08-03%20at%2016.32.24.png)

> 直接交付：直接给路由器所连的一个子网
> 
> 间接交付：路由器所连的网络当中并不存在目的地址，需要再转给别的路由器

> 直接交付用目的地址和各个子网的子网掩码相与，看结果是否和某个子网相对应，是则转发给这个子网

> 检测路径用目的地址和路由表当中每一行的子网掩码相与，看结果是否和某个目的网络地址相对应，是则按该行规定的下一条地址走

> 默认路由的 IP 地址和对应子网掩码均为全 0，通常是局域网当中的一个路由器，默认路由会发给另一个路由器再循环以上步骤

无分类编址 CIDR
----------

### 无分类编址 CIDR

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220823231342394.png)

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220823231423088.png)

> CIDR 地址块是主机号全 0 的最小地址，表示本网络

### 构成超网

路由表当中有几个路由都走的同一个接口就可以对这几个目的网络地址进行聚合

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220823231524028.png)

> 206.1.0.0/17 和 206.1.128.0/17 聚合后得到 206.1.0.0/16

例题：

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220823233453984.png)

### 最长前缀匹配

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220823231644098.png)

> 对于各个单位都分了地址块，学校的地址块由各个系进行路由聚合得到
> 
> 每个系下面可以继续再分，将网络前缀变长
> 
> 通过最长前缀匹配就可以将分组直接送达目标系而不让其他系和学校收到

例题：

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220823233411274.png)

> 所有路由表的目的网络当中，没有任何一个目的网络和分组的目的地址相匹配就走默认路由，默认路由接下来会交付给另一个路由器

ARP 协议
------

### 发送数据的过程

主机 1 向主机 3 发送文件，由于二者处于同一网络，链路层封装时目的 MAC 地址应填主机 3 的 MAC 地址

每一个主机和路由器都会有 ARP 高速缓存，存同一局域网内部主机和路由器连接该局域网端口的 IP 地址与 MAC 地址的映射

如果缓存中并没有主机 3 的 IP 地址与 MAC 地址映射，就需要使用 ARP 协议，ARP 协议通过接收方的 IP 地址查询其 MAC 地址。首先广播 ARP 请求分组，1 号主机会发送数据帧，该数据帧的目的 MAC 地址填全 1 代表在局域网内进行广播的帧，该帧经过交换机时会从所有端口转发出去，主机 2 和 3、路由器的这个端口都会收到

收到后只有主机 3 会响应，主机 3 返回单播 ARP 响应分组，内部包括主机 3 的 MAC 地址

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220824000214278.png)

若源主机和目的主机不在一个局域网内部，如主机 1 要和主机 5 通信时同样使用 ARP 协议，只不过 MAC 地址和之前有差别。链路层封装时主机 1 用自己的子网掩码和目的 IP 地址相与发现不在同一网络就会查询默认网关 IP6 的 MAC 地址 MAC6 填入目的 MAC 地址

> 主机和路由器端口才有的 MAC 地址，交换机没有 MAC 地址

> 默认网关就是与外界沟通的路由器，是局域网连入因特网的关口

传输到路由器进行数据封装和解封装时源 IP 地址和目的 IP 地址不变，但由于到了一个新的网络内，源 MAC 地址和目的 MAC 地址会改变

> 如果考虑 NAT，IP 地址也可能发生改变

> 当然这里两个路由器间是点对点式通信，应使用 PPP 协议，PPP 协议中目的 MAC 地址为全 1

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220824001622818.png)

### ARP 协议

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220824003022000.png)

数据最后要到达一个局域网内部，局域网内部只看得懂 MAC 地址

例题：

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220824003050932.png)

> 其中的路由器可能会连着很多个路由器和主机，不一定是点对点通信。这里就默认它都是要使用一次 ARP 协议

ARP 协议因为结合了 IP 地址和 MAC 地址，是处于链路层和网络层中间的协议，但是现在主要被划分成网络层协议，它给 IP 协议提供服务

DHCP 协议
-------

### 主机如何获得 IP 地址？

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220824095518949.png)

> 静态配置 —— 如学校机房内每一台主机都由管理员分配一个固定 IP 地址

> 默认网关通常指的是一个路由器的一个接口的 IP 地址。只有通过默认网关局域网内部的主机才能够跟外界进行通信

### DHCP 服务器

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220824100758574.png)

> 即插即用 —— 只要设备进入 DHCP 服务器所管辖的局域网内，就可以被动态地分配一个 IP 地址

> 地址重用 —— 每个 DHCP 服务器都有一个 IP 地址池，主机进入局域网中被分配 IP 地址，等离开后 DHCP 服务器可以把该 IP 地址分配给新的主机

> 在用地址续租 —— 通常 DHCP 动态分配地址是有时间性的，这段可以使用 IP 地址的时期叫租用期，过后可以重新向 DHCP 服务器请求一个 IP 地址或者续租

> 所有有地址的服务器都可以发送 DHCP 提供报文，广播 DHCP 请求报文就是为了告知其他 DHCP 服务器可以收回刚刚分配的 IP 地址

ICMP 协议
-------

为了更有效地转发 IP 数据报和提高交付成功的机会

### 网际控制报文协议 ICMP

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220824104908881.png)

> 代码字段是为了进一步区分某种类型当中一些不同的情况

> 检验和字段用来检验整个 ICMP 报文

### ICMP 差错报告报文

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220824105707201.png)

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220824105902946.png)

### 不应发送 ICMP 差错报文的情况

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220824110028474.png)

### ICMP 询问报文

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220824110056757.png)

### ICMP 的应用

PING:：测试两个主机之间的连通性，使用了 ICMP 回送请求和回答报文

Traceroute：跟踪一个分组从源点到终点的路径，使用了 ICMP 时间超过差错报告报文

> 源主机和目的主机之间有多个路由器，源主机会向目的主机发送一连串 TTL 依次被设置为 1，2，… 的数据报，链路上的路由器会将 TTL 减为 0 的数据报丢弃再返回给源主机 ICMP 时间超过差错报告报文

IP 组播
-----

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220824194705484.png)

### IP 数据报的三种传输方式

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220824161731550.png)

> 单播 IP 地址就是之前讲的 A、B、C 类里经常使用的一些 IP 地址
> 
> 单播 —— 源地址和目的地址均为单播 IP 地址
> 
> 广播 —— 源地址为单播 IP 地址，目的地址为全 1 的广播地址。只要一个 IP 数据报目的地址为全 1，它所对应的 MAC 地址也是全 1，这样的数据报会发给局域网内的全部主机，会从交换机的所有端口转发出去
> 
> 组播 —— 广播不管用户需求，组播则只会给有相同需求的一个组播组内的主机发送相同的数据报。比如看主播直播、腾讯会议时

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220824161933772.png)

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220824162010990.png)

> 在同一个物理网络 —— 在同一局域网内

> 组播路由器既可以运行组播协议也可以运行单播协议

### IP 组播地址

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220824224016144.png)

> 有些 D 类地址已经被指派了永久组地址

对 IP 组播进行分类，一种是只能在本局域网内进行的硬件组播，一种是没有进入局域网在因特网范围内的组播。现在大部分主机都是通过连在局域网然后再连入因特网，所以最后通过因特网范围内组播之后还是要进入到局域网内的硬件组播

### 硬件组播

> 如果现在发来一个单播数据报，进入局域网后看目标 MAC 地址决定应该交付给哪个主机。同样在硬件组播也需要根据 MAC 地址找到可以接收组播数据报的主机
> 
> 如果现在发来一个广播数据报，进入局域网后看到全 1 的目标 MAC 地址就会把数据报发给局域网中的所有主机，不管有没有交换机

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220824164908259.png)

> 之所以要过滤是为了要解决地址中这 5 位不一样，但最低 23 位一样的情况。此时会导致不同组播组但是映射得到的 MAC 地址相同

IGMP 协议和组播路由选择协议是因特网范围内组播要使用的协议，它们都使用 IP 数据报传输报文，都是网络层协议

### 网际组管理协议 IGMP

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220824194238586.png)

> 一个主机的多个进程都可以有对应的组播 IP 地址

> 加入组播组的几台主机的组播 IP 地址是 226.15.37.123。135.27.74.52，130.12.14.56 这些是主机本身就有的全球唯一的 IP 地址，要注意区分

每一个路由器通过使用 IGMP 协议就可以判断接收到组播组时是否要给局域网当中的主机

> IGMP 协议不知道局域网当中组播组的成员个数，同时也不知道这些成员在哪些网络上面，它只能让路由器知道是否有主机参加或者退出了组播组

### IGMP 工作的两个阶段

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220824194313377.png)

> Round1：路由器以及同属于组播组的成员都会收到报文
> 
> Round2：探询是在发送 IGMP 询问报文。其他主机只要监听到有一台主机先响应就不需要再发送响应

### 组播路由选择协议

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220824194357327.png)

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220824194434835.png)

> 协议无关 —— 虽然在建立转发树时使用单播数据报和远程路由器联系，但是并不要求使用相同的单播路由选择协议
> 
> 稀疏 / 密集 —— 一个组播组的主机间离的远近

IPv6
----

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220824161659067.png)

### IPv6 产生原因

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220824150356585.png)

### IPv6 数据报格式

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220824150631564.png)

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220824150711168.png)

> 下一个首部字段 —— 假如有一个 IP 数据报除了基本首部外还有若干个扩展首部，每个首部内都有下一个首部字段，指向下一个扩展首部，最后一个扩展首部指向数据部分

### 和 IPv4 的区别

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220824150727129.png)

### IPv6 地址表示形式

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220824150818829.png)

### IPv6 基本地址类型

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220824150936846.png)

> 多播 —— 一台主机要跟多播组内的所有主机进行通信，把多播地址放入 IPv6 数据报的目的地址字段。IPv6 并没有使用 IPv4 的广播地址，因为多播地址可以包括广播地址，IPv4 当中的广播发给本局域网当中的所有节点，对应于 IPv6 可以把广播想象成一组多播组当中的所有主机
> 
> 任播 —— 是 IPv6 独有一种的地址。假如一台主机 IP 数据报当中封装的目的地址是任播地址，它会给任播组内的一台主机发送数据报，通常是离它最近的一台

### IPv6 向 IPv4 过渡的策略

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220824151023454.png)

> 上图中不同的路由器使用不同版本的 IP 协议，使用 IPv4 协议的路由器收到 IPv6 数据报时会将其作为数据报封装到一个 IPv4 首部的数据报当中进行传输，进入 IPv6 网络时再去掉首部

移动 IP
-----

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220824194939953.png)

> QQ 依据 IP 登录，没有在你开通手机号的地区登录就会因为 IP 地址发生变化而显示异地登录提醒

### 移动 IP 相关概念

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220824200909677.png)

> 归属代理和外部代理都可以是一个路由器

### 移动 IP 通信过程

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220824201208065.png)

> 转交地址的获得有两种形式，被动获得和主动获得
> 
> 被动获得：外部代理会在外部网络内广播 ICMP 报文，内部包含转交地址
> 
> 主动获得：移动结点主动发送广播报文获得转交地址

> 注册之后，发给移动结点的数据报到达归属代理都会被封装，并且以隧道的形式发送给外部代理，外部代理再根据永久地址发送给移动结点

网络层设备
-----

### 路由器

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220824201448830.png)

> 转发：把分组从一个输入端口转发到另一个输出端口，在路由器内部
> 
> 路由选择：在路由之间选择一个合适的路径把数据从源主机发送到目的主机，在路由器外部

### 输入端口对线路上收到的分组的处理

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220824214733985.png)

### 输出端口对交换结构传送来的分组发送到线路

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220824214844942.png)

### 三层设备区别

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220824214913479.png)

> 对于任何层次的设备，都可以互联它所在的层次以及以下层次不同协议的网段 ×

> 集线器是直通式设备，来什么就发什么
> 
> 交换机的每一个端口都是一个冲突域

### 路由表与路由转发

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220824214957296.png)

> 转发表由路由表得来，要结合主机的一些具体信息确定输出端口

> 某些 MAC 地址可以是下一跳以太网的地址

SDN 的基本概念
---------

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220824222702102.png)

### 路由器功能：转发 & 路由选择

数据平面对应转发过程，控制平面对应路由选择过程

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220824222008822.png)

### 数据平面

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220824222051053.png)

### 控制平面（传统方法 / 每路由器法）

控制平面和数据平面都在一个路由器内进行

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220824222219197.png)

### 控制平面（SDN 方法：Software-Defined Networking）

数据平面和传统方法一样，控制平面从路由器物理上分离

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220824222256607.png)

> 这里的交换器其实指的是路由器

### 控制平面中的路由选择处理器

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220824222410543.png)

### SDN 控制平面

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220824222522146.png)

### SDN 控制器的三个层次

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220824222445504.png)

例题：

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220824222555901.png)