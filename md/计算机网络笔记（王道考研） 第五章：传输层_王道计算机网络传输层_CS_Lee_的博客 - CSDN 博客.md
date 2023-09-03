> 本文由 [简悦 SimpRead](http://ksria.com/simpread/) 转码， 原文地址 [blog.csdn.net](https://blog.csdn.net/zimuzi2019/article/details/126634511)

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

传输层
===

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220815214218295.png)

传输层概述
-----

### 传输层

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220821203432929.png)

> 中间的网络设备最多只能到网络层

> 进程和进程之间的逻辑通信 —— 表面上是两个主机的进程之间在通信。但实际是把数据从上层进行步步封装传给物理层，物理层放到链路上传输，到对端再至下而上把数据解封装交付给上层

> 复用：发送方不同的应用进程可以使用同一个传输层协议来传输数据
> 
> 分用：接收方在传输层去掉报文首部后能够把数据送交给正确的进程

> 网络层的首部校验和只校验 IP 数据报头部没有校验数据部分，需要高层实现对数据的检错。网络层的数据部分就是传输层的报文段，因此传输层如果对报文进行差错检测，那网络层就不需要再对报文进行差错检测。网络层 + 传输层可以实现可靠传输
> 
> 传输层并不一定会实现可靠传输

### 传输层的两个协议

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220821204900949.png)

> 方便起见可将两个协议的传输单元都称为报文段

> QQ 发送一条消息即使用 UDP 协议

### 传输层寻址与端口

复用：应用层所有的应用进程都可以通过传输层再传输到网络层

分用：传输层从网络层收到数据后交付指明的应用进程

如果要发送数据给一台主机，在网络当中根据其 IP 地址寻找到它所在的网络，进入它所在的网络后再根据 MAC 地址再定位到具体的主机。找到主机后还应根据端口交付给具体的应用进程

端口：逻辑端口 / 软件端口，是传输层的 SAP，标识主机中的应用进程

> 路由器和交换机上那种可以直接插拔的端口叫做硬件端口。而传输层的端口是看不见摸不着的，所以叫软件端口

用端口号来标识端口，端口号只有本地意义，在因特网中不同计算机的相同端口没有联系

端口号长度为 16bit，可以表示 2 16 = 65536 2^{16}=65536 216=65536 个不同的端口号

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220821210557750.png)

> 客户端使用的端口号只有在使用时才会由操作系统随机分配，进程结束就会端口号被回收

一些常用的端口号：

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220815214311155.png)

在网络中采用发送方和接收方的套接字组合来识别端点，套接字唯一标识了网络中的一个主机和它上面的一个进程

套接字 Socket= (主机 IP 地址, 端口号)

UDP 协议
------

### 用户数据报协议 UDP 概述

UDP 只在 IP 数据报服务之上增加了很少功能，即复用分用和差错检测功能

UDP 的主要特点：

1.  UDP 是无连接的，减少开销和发送数据之前的时延
    
2.  UDP 使用最大努力交付，即不保证可靠交付，可靠性由 UDP 上层即应用层保证
    
3.  UDP 是面向报文的，适合一次性传输少量数据的网络应用
    
    ![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220815214322904.png)
    
    > 因此应用程序需要选择大小合适的报文，报文太长则网络层需要分片以满足链路层 MTU 的要求，这样就会降低网络层的效率
    
4.  UDP 无拥塞控制，适合实时应用（比如 IP 电话、视频会议）
    
5.  UDP 首部开销小，只有 8B，TCP20B
    

### UDP 首部格式

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220815214332362.png)

> 一定会有首部字段，数据字段可以为 0

> 16 位源端口号可有可无。如果期望收到对方的回复则添上，如果不需要就可以是全 0。目的端口号一定要有
> 
> 16 位 UDP 长度单位是 1B

### UDP 校验

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220815214344022.png)

> 17 就是 IP 数据报首部的协议字段，这个协议字段说明 IP 数据报数据部分使用什么协议，这里数据部分使用 UDP 协议，对应的协议字段值是 17

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220821231310346.png)

TCP 协议特点和 TCP 报文段
-----------------

### TCP 主要特点

1.  TCP 是面向连接（虚连接）的传输层协议
    
    > 虚连接 —— 并不是实际的物理连接，只是使用时就好像两个进程之间直接建立了点对点的连接。实际上连接过程是把数据报加上各个层次的首部之后放到链路上传输，然后在接收端进行步步解封装，这是一个完整的物理连接
    
2.  每一条 TCP 连接只能有两个端点，每一条 TCP 连接只能是点对点的
    
    > TCP 协议不能用于广播和多播通信方式
    
3.  提供可靠交付的服务，无差错、不丢失、不重复、按序到达。可靠有序，不丢不重
    
4.  提供全双工通信
    
    > 发送方和接收方角色不定，双方可以同时发送数据也可以同时接收数据
    
    > TCP 协议连接的两端都会设置发送缓存，接收缓存
    > 
    > 发送缓存：应用层准备发送的数据 & 已发送但尚未收到确认的数据
    > 
    > 接收缓存：按序到达但尚未被应用程序读取的数据 & 不按序到达的数据
    
5.  TCP 面向字节流
    
    > 流：流入到进程或从进程流出的字节序列
    
    > 虽然进程和 TCP 交互时一次发送一个数据块，数据块可能大小不一样，但 TCP 把应用程序交下来的数据看成仅仅是一连串的无结构的字节流
    > 
    > ![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220815214405549.png)
    > 
    > 发送方发送文件时会把文件按照字节排序编号并放入 TCP 缓存，再取几个字节加上 TCP 头形成 TCP 报文段再放到链路上传输
    

### TCP 报文段首部格式

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220815214414774.png)

> ![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220815214423770.png)
> 
> 以上图为例发送”123“报文段时，该报文段首部序号字段填 1
> 
> ![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220822002830429.png)
> 
> 接收端已经收到了”123“报文段就会给发送端发送首部确认号字段为 4 的报文段
> 
> 由数据偏移字段可知首部最大为 60B

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220822003347217.png)

> 将 RST 置为 1 还可以用来拒绝一个非法报文段，或者拒绝打开一个链接

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220822100012476.png)

> 发送方根据接收方报文的窗口字段设置发送窗口大小
> 
> 检验时加上的伪首部的第四个字段其实就是协议字段，在 UDP 当中是 17，而在 TCP 当中应该是 6
> 
> 紧急指针指出紧急数据的末位在报文段当中的位置。如紧急指针值为 50，则 TCP 数据部分的前 50 个字节均为紧急数据，剩下的为普通数据
> 
> ![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220815214509133.png)
> 
> MSS 指的是每一个 TCP 报文段当中数据字段的最大长度
> 
> 填充字段保证首部是 4B 整数倍，通常填充全 0 字段

TCP 连接管理
--------

### TCP 连接管理

TCP 连接传输分为三个阶段：

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220815214518622.png)

TCP 连接的建立采用客户服务器方式，主动发起连接建立的应用进程叫做客户，而被动等待连接建立的应用进程叫服务器

### TCP 的连接建立

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220822101501656.png)

> Round1 ACK=0，ack 无效
> 
> Round2 由于连接请求报文段没有数据部分，ack=x+1
> 
> Round3 SYN 只在请求连接和连接接受时置 1，SYN=0

### SYN 洪泛攻击

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220815214548655.png)

> 解决方案：SYN cookie

### TCP 的连接释放

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220822102856183.png)

> Round1 由于 TCP 为全双工，此客户端也有可能为之前的服务端。由于连接释放报文段通常没有数据，所以序号 u 也可以标识报文段
> 
> Round2 此时服务器端仍可以发送数据
> 
> Round4 如果客户端发送的确认报文段没有到达服务器端，服务器端会重传连接释放报文段，客户端在 2MSL 内收到就会重传确认报文段并重新启动 2MSL 计时器。如果客户端不等待 2MSL 的时间而是在发送完确认报文段后直接释放连接，报文段丢失时客户端就无法接收服务器端重传的连接释放报文段，服务器端会一直发连接释放报文段而无法正常关闭

TCP 可靠传输
--------

### TCP 可靠传输

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220831220541002.png)

### 序号

TCP 协议面向字节流，因此 TCP 传输时以字节为单位，对字节依次编号。实际发送会把多个字节放在一起组成报文段发送，报文段大小不定，取决于链路层 MTU

> 对于文件或者要发送的数据，第一个字节的序号可以是随机的

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220815214639597.png)

### 确认

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220815214650296.png)

发送方在收到对发送报文段的确认之前，TCP 缓存区应保留报文段

> 接收方此时收到了 “123” 报文段，就会发送一个首部确认号字段为 4 的确认报文段，在发送方收到后把 TCP 缓存中的 “123” 报文段删去

接收方可在合适时候发送确认报文段，也可在要发送数据时把确认信息捎带上，即捎带确认

接收方采用累计确认，只确认数据流当中至第一个丢失字节为止的字节

> 假如发送端此时发送了 “456” 和“78”两个报文段，但接收端只接收到了 “78” 报文段，接收端还是会一直发送确认号为 4 的报文段。在收到确认号为 4 的报文后，发送端会重传”456“报文段。在接收端收到”456“报文段后，下次发送的确认号应为 9

### 重传

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220822123207691.png)

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220822123227486.png)

> TCP 协议也有发送窗口和接收窗口的概念，在发送过程中会使用 GBN 协议和 SR 协议，使用时同链路层讲过的大同小异

TCP 流量控制
--------

### TCP 流量控制

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220822151500294.png)

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220815214732683.png)

TCP 拥塞控制
--------

### TCP 拥塞控制

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220822152007225.png)

> 拥塞控制是全局性问题，接收方并不知道拥塞情况具体是哪几台主机发送数据过多造成的。而流量控制是点到点之间的问题，接收方知道找哪个发送方

### 拥塞控制四种算法

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220822153020564.png)

### 慢开始和拥塞避免

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220822154820577.png)

> cwnd=n 表示为 n 个报文段，长度都为 MSS

> 慢开始 cwnd 翻倍在收到之前发送报文的确认后立刻发生

### 快重传和快恢复

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220822154738033.png)