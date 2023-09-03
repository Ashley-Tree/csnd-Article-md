> 本文由 [简悦 SimpRead](http://ksria.com/simpread/) 转码， 原文地址 [blog.csdn.net](https://blog.csdn.net/zimuzi2019/article/details/126634063)

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

物理层
===

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220829144408782.png)

物理层基本概念
-------

### 物理层接口特性

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220829144451261.png)

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220829144526008.png)

> 功能特性有的时候可能不会出现数字，电气特性通常都会结合数字

数据通信基础知识
--------

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220829152932490.png)

### 典型的数据通信模型

假如我们是拨号上网，我们的电脑就会通过公用电话网把我们要传的数据经过一系列过程传给另一个端系统

计算机网卡所发出的数据是数字信号，调制解调器把数字信号调制成模拟信号。在这个例子当中数据要经过公用电话网，这是一个广域网，在广域网中有很多条模拟信道，这些模拟信道只能传模拟信号不能传数字信号，所以要调制成模拟信号。调制解调器后面又会把模拟信号解调成数字信号

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/Screen%20Shot%202022-07-25%20at%2020.28.42.png)

### 数据通信相关术语

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220829151816483.png)

### 设计数据通信要考虑的 3 个问题

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220829152013247.png)

### 三种通信方式

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220829152048326.png)

### 串行传输 & 并行传输

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220829152136087.png)

### 同步传输 / 异步传输

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220829152425203.png)

> 异步传输 —— 在键盘上敲字

### 码元

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220829153007028.png)

> 不同进制的码元区别在于能携带多少信息量，信息量 = l o g 2 =log_2 =log2​离散状态（bit)

### 数字通信系统数据传输速率的两种表示方法

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220829154009980.png)

> 码元传输速率与进制数无关

例题 1：

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220829154503340.png)

例题 2：

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220829154538780.png)

> 二进制信号指的其实就是二进制码元，一个码元对应 1 个 bit。四进制信号有 4 种码元，或者说 4 种信号波形，一个码元对应 2 个 bit

### 带宽（Bandwidth）

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220829154612665.png)

### 奈氏准则 香农定理

### 失真

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220829162104704.png)

> 码元传输速率越大失真越严重

### 码间串扰

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220829162217259.png)

振动频率太低，在电话线上传输时容易衰减

振动频率太大，导致接收端接收时区分不出波形之间的差异

### 奈氏准则（奈奎斯特定理）

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220829162649124.png)

例题：

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220829163418714.png)

### 香农定理

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220829163606006.png)

![](https://img-blog.csdnimg.cn/355349f5aad7473b8d7a60da8e5044a0.png)

例题：

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220829164015551.png)

### 对比

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220829164114422.png)

题目中如果给了噪声的条件就用香农定理，如果没有噪声条件就用奈氏准则。如果给了信噪比也给了 V(一个码元对应多少个 bit)，两个准则就要都算一下取其最小值

编码和调制
-----

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220830142000275.png)

### 基带信号和宽带信号

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220829164820088.png)

收音机播放 “欢迎收听 FM***”，这里的 FM 就是一种调制的手法

信源有很多种，可以是人类也可以是计算机。计算机会通过网卡发出数字信号，而人类说话时发出的声波是模拟信号。所以基带信号既可以是数字信号也可以是模拟信号，但我们在[计算机网络](https://so.csdn.net/so/search?q=%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C&spm=1001.2101.3001.7020)当中用的就是数字信号，因为网卡发出的是数字信号，而这些发出的数字信号放到数字信道上进行传输就叫做基带传输，所以只需记住基带传输对应数字信道就行

宽带信号其实是对最开始的基带信号进行调制，调制后才可以放到复杂和比较危险的信道上进行传输

总之，放到数字信道上进行传输就是基带传输，放到模拟信道上进行传输就是宽带传输

> 宽带传输一定采用频带传输技术

### 编码和调制

编码和调制把数据转成信号

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220829165619419.png)

### 数字数据编码为数字信号

数字数据编码用于基带传输，编码方式规定 0 和 1 分别对应什么样的数字信号波形

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220830135124773.png)

1.  **非归零编码（NRZ）**：**高 1 低 0**。编码容易实现，但没有检错功能，且无法判断一个码元的开始和结束，以至于收发双方难以保持同步
    
    > 什么叫难以保持同步？
    > 
    > 假设发送的数据是连续 1 或者连续 0，那接收端接收到的可能就是一长条特别长的直线，它不知道这条直线到底有多少个 1 和多少个 0，所以就需要发送端告诉它每一段时钟周期是多久才能对这一长条直线进行处理算出发送了多少个 1 和多少个 0，这种方式就需要发送端和接收端之间再建立一条信道用于传输时钟周期信号，这就是两者建立一个同步的过程
    > 
    > 非归零编码要建立同步比较困难，所以这种编码方式并不是很常用
    
2.  **曼彻斯特编码**：将一个码元分成两个相等的间隔，前一个间隔为低电平后一个间隔为高电平表示码元 1；码元 0 则正好相反。也可以采用相反的规定。该编码的特点是在每一个码元的中间出现电平跳变，位中间的跳变既作时钟信号（可用于同步），又作数据信号，但它所占的频带宽度是原始的基带宽度的两倍。每一个码元都被调成两个电平，所以数据传输速率只有调制速率的 1/2
    
    > 数据传输速率只有调制速率的 1/2 —— 在一个时钟周期当中信号变化了 2 次（2 个脉冲），而 bit 只传了一位，故数据传输速率只有调制速率（或者是码元传输速率）的 1/2
    > 
    > eg：若码元传输速率为 40B，则信息传输速率为 20bit/s
    
3.  **差分曼彻斯特编码**：**同 1 异 0**。常用于局域网传输，其规则是：若码元为 1，则前半个码元的电平与上一个码元的后半个码元的电平相同，若为 0，则相反。该编码的特点是，在每个码元的中间，都有一次电平的跳转，可以实现自同步，且抗干扰性强于曼彻斯特编码
    
4.  归零编码（RZ）：信号电平在一个码元之内都要恢复到 0 的这种编码成编码方式
    
    > 整个传输过程中处于低电平的情况可能非常多且时间久，相当于没怎么利用信道，所以并不怎么推荐使用
    
5.  反向不归零编码（NRZI）：信号电平翻转表示 0，信号电平不变表示 1
    
    > 如果是对于全 0 的话，信号电平会一直翻转，利于接收端接收。如果是对于全 1 的情况，就会出现和非归零编码一样的问题，还是要建立一个新的信道让发送端和接收端确定好每一个时钟周期是多长
    
6.  4B/5B 编码：
    
    比特流中插入额外的比特以打破一连串的 0 和 1，就是用 5 个比特来编码 4 个比特的数据，之后再传给接收方，因此称为 4B/5B。编码效率为 80%
    
    只采用 16 种对应 16 种不同的 4 位码，其他的 16 种作为控制码（帧的开始和结束，线路的状态信息等）或保留
    
    ![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/Screen%20Shot%202022-07-25%20at%2022.04.07.png)

### 数字数据调制为模拟信号

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220830141127012.png)

> 产生的不同种类码元个数 = 相位数 × \times × 振幅数
> 
> 共有 4 × 4 = 16 4\times 4=16 4×4=16 种波形， 2 × W × l o g 2 16 = 4800 b i t / s 2\times W\times log_ 216=4800bit/s 2×W×log2​16=4800bit/s

### 模拟数据编码为数字信号

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220830141422856.png)

> PCM —— 脉冲编码调制

> 人所能听到的声波是从 20Hz 到 20000Hz，听音乐的时候为了让音乐尽可能地保真，耳机等音乐设备对于音乐的采样频率就尽量要达到人所能听到的信号最高频率的二倍以上

### 模拟数据调制为模拟信号

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220830141859685.png)

数据交换方式
------

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220830163103295.png)

### 为什么要数据交换？

提高设备交换效率，降低成本

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220830153850100.png)

> 交换设备可以是交换机，路由器等等。比如说在局域网内部就是交换机，如果涉及到广域网的问题那交换设备可以是路由器

> 注意，以下交换方式不一定属于物理层

### 电路交换

主机 A 首先向最近的交换设备 A（也就是节点 A）发送呼叫请求，呼叫请求当中包含需要建立线路的源主机 A 和目的主机 B 的 IP 地址，节点 A 执行一种路由选择算法选择下一个节点转发呼叫请求，接下来的过程都类似，直到传到目的主机 B。如果 B 接受 A 的连接请求就会发送呼叫应答原路返回。至此 AB 两台主机之间线路连接成功

虽然上面是 A 主机发送呼叫请求，但是 A 和 B 两台主机都可以发送数据，即采用全双工通信方式

假如 A 主机要切断连接，A 主机会先发送一个释放请求，该请求在之前选好的路径上进行转发最后发给 B 主机。当 B 主机收到释放请求之后就返回一个释放应答并且沿原路径将连接依次释放

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220830154220330.png)

> 独占资源 —— A 和 B 在通信过程当中中间的链路是不能被其他主机所占用的

### 电路交换的优缺点

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220830154331791.png)

> 电路交换的设备主要采用交换机

> 无数据存储能力，难以平滑通信量 —— 电路交换的设备没有存储能力，如果有大量数据涌入到交换设备当中，交换设备无法存储它们就可能会导致数据的丢失等问题。这其实也是电路交换和分组交换以及报文交换的一个主要不同点

### 报文交换

若源主机有一要传输的数据块，称这个数据块为信息，信息加上报头封装成一个完整报文传输，里面包括源地址以及目的 IP 地址还有一些相关的控制信息

存储相当于对这个报文进行复制，拷贝报文的副本放到交换设备缓存当中

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220830155713920.png)

> 路由信息指的是交换设备会获得一张路由表，根据路由表它就可以判断接下来走哪几个路由器到目的主机距离最短

> 每两个节点之间的链路不被独占，所有人共享

### 报文交换的优缺点

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220830155837973.png)

### 分组交换

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220830155900591.png)

### 分组交换的优缺点

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220830160234942.png)

### 数据交换方式的选择

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220830160307817.png)

### 数据报方式

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220830161558789.png)

### 数据报方式的特点

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220830161733821.png)

> 在这种无连接的这种情况下如果丢弃了部分分组会有一定的机制让分组再重新发送

> 会话式通信通常采用电路交换

### 虚电路方式

> 是电路交换和报文交换的结合

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220830162418043.png)

如果主机 B 可以应答就会返回一个呼叫应答分组。注意在建立连接阶段呼叫请求以及呼叫应答都是分组，而这个分组要包含目的地址以及源主机地址

传输时每个分组不需要携带目的地址，因为连接建立好后路径就唯一确定了，分组只能沿着这条路径走，但是它要携带一个新的标识虚电路号。虚电路号表明分组是哪一条电路过来的，它的意义主要在于如果主机 B 收到了大量的分组，而且这些分组当中有些可能是其他主机发来的，那么主机 B 就需要根据虚电路号对这些分组进行分类，再根据分组号还原成完整的报文后交付给相应的进程

> 释放连接的过程和电路交换很像

### 虚电路方式的特点

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220830162608064.png)

> 电路交换是物理线路

> 虚电路包括永久性的（PVC）和临时性的（SVC）

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220830163005033.png)

物理层传输介质
-------

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220830203520833.png)

### 传输媒体及分类

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220830190030404.png)

### 导向性传输介质 —— 1. 双绞线

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220830190130566.png)

### 导向性传输介质 —— 2. 同轴电缆

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220830202700003.png)

### 导向性传输介质 —— 3. 光纤

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220830202803024.png)

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220830203107447.png)

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220830202833702-16618626428601.png)

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220830203328009.png)

### 非导向传输介质

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220830203440252.png)

物理层设备
-----

### 中继器

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220830203556973.png)

> 放大器可以放大模拟信号

> 对于这种不会存储转发的设备，它们两端的协议一定是要相同的
> 
> 要求在物理层互联，只需要端口速率相同即可。要求在数据链路层互联，则还要求协议相同

> 5-4-3 规则
> 
> 在通常使用的 10 兆以太网当中使用 5-4-3 规则，5 指的是最多只能有 5 个网段。每个中继器两端是连接两个网段，4 指的是在这 5 个网段内最多只能有 4 个物理层设备（中继器或者是集线器），3 指的是只有 3 个网段可以挂计算机

### 集线器（多口中继器）

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220830203814821.png)

> 不具备信号的定向传送能力 = 广播，因而容易产生冲突