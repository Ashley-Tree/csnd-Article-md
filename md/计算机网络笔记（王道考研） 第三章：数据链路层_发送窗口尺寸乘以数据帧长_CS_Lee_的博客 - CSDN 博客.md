> 本文由 [简悦 SimpRead](http://ksria.com/simpread/) 转码， 原文地址 [blog.csdn.net](https://blog.csdn.net/zimuzi2019/article/details/126634296)

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

数据链路层
=====

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220824235917003.png)

数据链路层功能概述
---------

### 研究思想

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220824235958998.png)

### 基本概念

*   结点：主机、路由器
*   链路：网络中两个结点之间的**物理通道**，传输介质有双绞线、光纤、微波。分为有线链路、无线链路
*   数据链路：两个结点之间的**逻辑通道**，把实现控制数据传输**协议**的硬件和软件加到链路上就构成数据链路
*   帧：链路层的协议数据单元，封装网络层数据报

数据链路层负责通过一条链路从一个结点向另一个物理链路直接相连的相邻结点传送数据报

### 数据链路层功能概述

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220825000520548.png)

组帧
--

### 封装成帧

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220825094422983.png)

### 透明传输

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220825094453580.png)

### 字符计数法

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220825094606807.png)

缺点：若计数字段出错，会导致后面所有帧全部发生错误

### 字符填充法

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220825094716860.png)

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220825094747304.png)

> 键盘上的 ASCII 码和帧开始和结束定界符对应的比特组合

### 零比特填充法

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220825094811147.png)

### 违规编码法

用两个编码当中不会用到的电平方式来标志帧的起始和终止

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220825094911440.png)

> 局域网的 IEEE802 标准就采用这种方法

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220825094955511.png)

差错控制（检错编码）
----------

### 差错从何而来？

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220825154021453.png)

> 无确认无连接服务保证可靠传输需要传输层解决

### 数据链路层的差错控制

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220825154824955.png)

### 检错编码 —— 奇偶校验码

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220825154346004.png)

### 检错编码 —— CRC 循环冗余码

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220825154443041.png)

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220825154534878.png)

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220825154555527.png)

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220825154930741.png)

> 位错 / 比特错的差错控制虽然能保证接收每个帧时都能无差错，实现无比特差错的传输，但是有些帧被丢弃没有进行处理，发送端发送的数据并没有被全部接收，所以不是可靠传输

纠错编码 —— 海明码
-----------

海明码能够发现错误，找到位置并纠正错误

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220825161231439.png)

### 海明距离

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220825161250945.png)

> 检验 d 位错：码距 ≥ d + 1 \ge d + 1 ≥d+1
> 
> 纠正 d 位错：码距 ≥ 2 d + 1 \ge 2d + 1 ≥2d+1

### 1. 确定校验码位数 r

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220825161350540.png)

### 2. 确定校验码和数据的位置

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220825161433166.png)

### 3. 求出校验码的值

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220825161951517.png)

### 4. 检错并纠错

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220825204651360.png)

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220825162841234.png)

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220825163008276.png)

流量控制与可靠传输机制
-----------

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220825205128586.png)

### 数据链路层的流量控制

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220825204739102.png)

### 流量控制的方法

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220825203504631.png)

> 链路层的滑动窗口协议中窗口大小在传输过程中是固定的

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220825203446402.png)

> 滑动窗口协议中的帧序号是重复利用的

### 可靠传输、滑动窗口、流量控制

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220825205111064.png)

停止 - 等待协议
---------

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220826204748434.png)

### 停止 - 等待协议究竟是哪一层的？

> 《[计算机网络](https://so.csdn.net/so/search?q=%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C&spm=1001.2101.3001.7020)》和《计算机网络 自顶向下方法》放在传输层，王道考研的辅导书放在链路层

在计算机网络发展的前期，通信链路质量不好，所以链路层需要保证可靠传输，因此链路层会使用停止 - 等待协议、后退 N 帧协议、选择重传协议等等。随着技术的发展通信链路的质量越来越好，出现差错的可能性变小，因此链路层就可以主要负责差错控制，可靠传输交给传输层实现，这样数据在链路上传递的速度更快，延迟更小

因此不需要太纠结停止 - 等待协议属于哪一层次，因为它在哪一层次最后只会影响数据传输的对象是分组还是帧

### 停止 - 等待协议

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220826203413249.png)

### 停止等待 —— 无差错情况

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220826203500313.png)

> 虽然都叫 0 帧，但这是两个完全不一样的帧，只是用相同的编号表示

### 停止等待 —— 有差错情况

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220826203537851.png)

> 通过编号来判断是否发生了帧丢失和帧重复，停止 - 等待协议中如果连续收到相同发送序号的数据帧说明发送端进行了超时重传，连续出现相同序号的确认帧表明接收方收到了相同的重复帧

> 接收方会丢弃出错帧不做处理，不返回确认帧

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220826203621857.png)

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220826203650945.png)

### 停等协议性能分析

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220826204027295.png)

> T D T_D TD​：发送方发送一个数据帧的发送时延
> 
> RTT：往返时延
> 
> T A T_A TA​：确认帧的发送时延

### 信道利用率

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220826204126108.png)

> 数据传输率即数据发送速率

> 例题忽略了确认帧的发送时延

后退 N 帧协议（GBN）
-------------

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220827101855158.png)

### 停等协议的弊端

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220827103639756.png)

### 后退 N 帧协议中的窗口

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220826205012597.png)

### GBN 发送方必须响应的三件事

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220826205115213.png)

### GBN 接收方要做的事

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220826205307301.png)

### 运行中的 GBN

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220826205523902.png)

### 滑动窗口长度

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220826210114170.png)

### GBN 协议重点总结

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220826205852512.png)

习题 1：

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220826205929080.png)

习题 2：

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220826210538699.png)

> 信道带宽即发送方发送数据的理想状态速度

甲发送数据的理想状态是可以一直发送，滑动窗口一直前移，那么就可以达到 100Mb/s，但这是永远达不到的。还有一种情况是甲已经把发送窗口里的帧全部发送出去，但是还没有等到第一帧的确认帧，所以甲发送完所有帧之后就要等待，等到接收方发来对于第一帧的确认帧才进行滑动窗口前移，进而再发送写一批数据。这里看一下是否会出现第二种情况：

甲把发送窗口里的全部数据发送出去需要多久：

发送窗口尺寸 × 数据帧长 甲的发送速率 = 1000 × 1000 × 8 b 100 × 1 0 6 b / s = 80 m s \frac{发送窗口尺寸 \ times 数据帧长}{甲的发送速率}=\frac{1000\times 1000\times 8b}{100\times 10^6 b/s}=80ms 甲的发送速率发送窗口尺寸 × 数据帧长​=100×106b/s1000×1000×8b​=80ms

> 用信道带宽来近似代替发送速率

甲在发送第一帧之后多久才能收到确认帧：

传播延迟 + 甲发送第一帧的发送时长 (第一帧的传输延迟) = 传播延迟 + 甲发送第一帧的发送时长 (第一帧的传输延迟)= 传播延迟 + 甲发送第一帧的发送时长 (第一帧的传输延迟)=

2 × 50 m s + 1000 × 8 b 100 × 1 0 6 b / s = 100.08 m s 2\times 50ms+\frac{1000\times 8b}{100\times 10^6 b/s}=100.08ms 2×50ms+100×106b/s1000×8b​=100.08ms

可以看出甲发送完窗口里的所有帧之后还没有收到第一帧的确认帧，需要再等待 20ms 左右才能进行窗口前移。接下来的流程也跟这段很类似一直循环。所以我们现在就可以根据第一次发送的情况得出答案：

发送窗口尺寸 × 数据帧长 从刚开始发送第一帧到收到它的确认帧的时长 = 1000 × 1000 × 8 100.08 m s ≈ 80 M b / s \frac{发送窗口尺寸 \ times 数据帧长}{从刚开始发送第一帧到收到它的确认帧的时长}=\frac{1000\times1000\times8}{100.08ms}\approx 80Mb/s 从刚开始发送第一帧到收到它的确认帧的时长发送窗口尺寸 × 数据帧长​=100.08ms1000×1000×8​≈80Mb/s

解决这种问题时需要把整个发送数据的过程想清楚，同时要抓住第一帧，最后一帧还有第一帧的确认帧这几个重要的帧

### GBN 协议性能分析

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220827102052613.png)

选择重传协议（Selective Repeat）
------------------------

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220827112312523.png)

### GBN 协议的弊端

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220827103714421.png)

> 窗口的下界是否收到或者被确认决定滑动窗口会不会往前移

### 选择重传协议中的滑动窗口

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220827111329514.png)

### SR 发送方必须响应的三件事

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220827111404848.png)

### SR 接收方要做的事

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220827111440231.png)

### 运行中的 SR

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220827111524429.png)

### 滑动窗口长度

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220827111934407.png)

### SR 协议重点总结

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220827112204952.png)

习题：

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220827112239558.png)

信道划分介质访问控制
----------

### 传输数据使用的两种链路

广播式链路适用于网络范围比较小的局域网，而点对点链路适合于通信范围比较大的广域网

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220827183341662.png)

> 移动设备上网时就使用无线局域网

> 星型中间在局域网当中常用集线器

### 介质访问控制

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220827183436100.png)

### 信道划分介质访问控制

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220827183637754.png)

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220827184218293.png)

### 频分多路复用 FDM

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220827184307989.png)

### 时分多路复用 TDM

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220827184648219.png)

### 改进的时分复用 —— 统计时分复用 STDM

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220827184734763.png)

> 集中器搜集所有用户的数据在一条信道上发送

假如线路传输速率是 8000b/s，对应于 TDM 中每个用户可能平均速率最高只分到 2000b/s，STDM 中一个人最高则可以达到 8000b/s

如果有的用户经常发送数据，有的用户偶尔会发送数据就比较推荐使用统计时分复用，可以让信道的利用率大大地提高

### 波分多路复用 WDM

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220827185006401.png)

### 码分多路复用 CDM

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220827185039046.png)

> A，B 是发送数据的源站，C 是接收数据的目的站

> 发 1 个 bit 需要一段时间，我们称之为 1bit 的时隙时间，把这段时间分割成 n 位的芯片序列，这样就分成了 n 个微小的时隙。对于每一个 bit 都可以把它分为唯一的 n 位的芯片序列。可以把芯片序列理解成向量

> 规格化内积其实就是在内积的基础之上除以一个向量的分量个数

ALOHA 协议
--------

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220827185155254.png)

### ALOHA 协议

分为纯 ALOHA 协议和时隙 ALOHA 协议

### 纯 ALOHA 协议

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220827185407759.png)

> T 0 T_0 T0​用帧的发送时间描述帧的长度，这里的发送时间既包括传输时延也包括传播时延。上图假设每一个站点所发送的每一个数据帧的 T 0 T_0 T0​都相同

> 信道上有两个站点在同时发送数据就必然会发生冲突。由于站点并没有在发送数据时进行监听，所以不知道是否发生冲突

### 时隙 ALOHA 协议

每一个站点只能在时间片的开头发送帧

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220827185453462.png)

> 时间片对应 T 0 T_0 T0​，也叫做时间槽

### 关于 ALOHA 要知道的事

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220827185525359.png)

> 用吞吐量来形容数据帧的发送成功率，指在一段时间内成功发送的平均帧数

CSMA 协议
-------

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220827233223306.png)

### CSMA 协议

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220827233411319.png)

### 1 - 坚持 CSMA

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220827233431251.png)

### 非坚持 CSMA

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220827233454100.png)

### p - 坚持 CSMA

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220827233532270.png)

### 三种 CSMA 对比总结

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220827233602425.png)

CSMA/CD 协议
----------

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220827234726334.png)

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220827233844085.png)

### CSMA/CD 协议

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220827233919489.png)

### 传播时延对载波监听的影响

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220827234121513.png)

> 信号还没有到达 B 时，B 检测发现并没有信号进入站点，会认为信道空闲

> 对于数据帧有差错控制，B 会根据收到的 A 所发来的数据帧检测它是否发生碰撞出错

上图中经过 t = 2 τ − δ t=2\tau -\delta t=2τ−δ时间 A 得知自己发生了碰撞，经过 t = δ t=\delta t=δ时间 B 得知自己发生了碰撞，因此最迟要经过 2 τ 2\tau 2τ（此时 τ → 0 \tau \to 0 τ→0）时间才能够知道自己发送的数据没有发生碰撞

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220827234230993.png)

### 如何确定碰撞后的重传时机？

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220827234452676.png)

### 最小帧长问题

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220827234623970.png)

故需要定义最小帧长，希望检测到碰撞时帧还没有发送结束。考虑到最迟在争用期 2 τ 2\tau 2τ时可以检测到碰撞：

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220827234647649.png)

> 以太网为了达到最小帧长，会对较短帧进行填充再放到链路上传输

CSMA/CA 协议
----------

### CSMA/CA 协议

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220828091606825.png)

> CSMA/CD 常用于总线式以太网，属于有线网络

### CSMA/CA 工作原理

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220828091651413.png)

> RTS 和 CTS 都是一种帧

> 建立连接后其他站点再向接收端发送 RTS 接收端不返回 CTS，这样就解决了隐蔽站问题

### CSMA/CD 与 CSMA/CA

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220828091738525.png)

轮询访问介质控制
--------

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220828092054211.png)

### 轮询协议

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220828092207833.png)

> 询问的过程就是在发送短数据帧

> 实际网络当中会多建立一些备用主结点

### 令牌传递协议

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220828092232444.png)

> TCU 是传递数据帧时的转发接口，可以传递所有经过的帧，并为接入站发送和接收数据提供接口

网络空闲，没有主机要发送数据时，令牌在各个主机之间传递，直到有一个主机要发送数据。该主机会修改令牌的标志位，把令牌从空闲状态变成忙状态，并在令牌控制帧后面加上数据构成数据帧发送出去。传递时其他主机不做处理，到目的主机就会被复制一份，传递回发送主机后会先检查数据帧是否出错，如果出错可能还要再重传，如果没有就会回收数据帧不再转发，并将令牌调回空闲状态传递出去

> 一些书也会说在源站点传送完数据后还会产生新的令牌

> 可以设置替代机应对可能的单点故障

局域网基本概念和体系结构
------------

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220828165009076.png)

### 局域网

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220828164050761.png)

### 局域网拓扑结构

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220828143139785.png)

> 星型拓扑共享能力差是相对于总线型拓扑来说的，总线型拓扑中所有人都在共享一条主干信道

> 树形拓扑和环形拓扑构建好后通信的方向就已确定，如之前的令牌环网

综合这几种拓扑，总线型拓扑优势最大。以太网就是逻辑上的总线型拓扑结构

### 局域网传输介质

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220828164159876.png)

### 局域网介质访问控制方法

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220828164247438.png)

### 局域网的分类

> 按照介质访问控制方法分类

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220828164321874.png)

> 令牌环网和 FDDI（光纤分布式数据接口）网造价较高
> 
> 通信时每一个数据会被分成小单元，ATM 网当中长度单元固定为 53B，其他几种网络交换的信息单元长度是可变的
> 
> WIFI 是无线局域网的一种技术上的应用，无线局域网可以的覆盖范围要比 WIFI 更广一些，可能是几千米

### IEEE802 标准

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220828164418693.png)

IEEE802.3：以太网介质访问控制协议（CSMA/CD）及物理层技术规范

IEEE802.5：令牌环网（Token-Ring）的介质访问控制协议及物理层技术规范

IEEE802.8：光纤技术咨询组，提供有关光纤联网的技术咨询

> FDDI 网使用的标准是 IEEE 802.8

IEEE802.11：无线局域网（WLAN）的介质访问控制协议及物理层技术规范

### MAC 子层和 LCC 子层

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220828164932048.png)

以太网
---

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220828170226794.png)

### 以太网概述

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220828165111927.png)

> 题目当中用 E1 标识的一个网络就是以太网

> 局域网采用 CSMA/CD 技术就可以说是一个以太网

### 以太网提供无连接、不可靠的服务

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220828165142260.png)

> 这里的高层通常指的是传输层

> 无差错接收 —— 假如说发送方发送 1010，那接收方也要按照 1010 接收，如果接收方通过差错检测发现帧出错就干脆拒收或者丢弃该帧
> 
> 可靠传输 —— 只要是发送方发来的帧都要接收，即要解决帧丢失和帧重复，帧失去等问题

### 以太网传输介质与拓扑结构的发展

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220828165326412.png)

### 10BASE-T 以太网

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220828165354320.png)

> Base —— 基带传输，传送基带信号（数字信号）
> 
> T —— Twisted，双绞线
> 
> 10 —— 传输速率

### 适配器与 MAC 地址

MAC 地址是在数据链路层上标识每一个主机或者设备的标识符

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220828165428982.png)

> 适配器就是网卡。现在的计算机主板上都已经嵌入了适配器，不再需要单独再使用网卡

> MAC 地址随着网卡烧制结束就已经确定
> 
> 根据 MAC 地址就可以验证买的鼠标等设备是否是正品。在相关网站输入自己设备的 MAC 地址的前 24 位进行搜索，看是否是对应的厂商
> 
> ![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220828165624627.png)

### 以太网 MAC 帧

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220828165652345.png)

> 为了使发送方和接收方能够保持同步需要在从 MAC 层往物理层传递的帧前面插入一个 8B 的前导码，8B 前导码并不是以太网 MAC 帧的一部分
> 
> 前同步码前面的 1010 … 使发送方和接收方能够进行一个时钟的同步，而最后面的两位 1 告诉接收方可以开始准备接收 MAC 帧

> 目的地址会有单播地址（专有 MAC 地址），广播地址（全 1），多播类型三种情况。所有的主机看到广播地址都会接收
> 
> 类型指明网络层使用的协议，以便把收到的 MAC 帧的数据上交给上层的协议
> 
> 1500B 是链路层的 MTU。46B 由以太网最小帧长 64B 得来
> 
> FCS 是 CRC 帧检验序列

> 为什么没有帧结束定界符？以太网使用曼彻斯特编码作为编码形式，且每一个发送帧之间都会有一个最小间隔，并不会紧挨着发送。曼彻斯特编码 1bit 对应 2 个码元（或者说在一个 bit 时间范围内会有 2 次信号变化），发送数据时适配器能感受到电压的变化，不发送数据时电压就没有变化

### 高速以太网

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220828165727997.png)

> 集线器只会从每一个端口简单转发比特流。100BAST-T 以太网星型拓扑当中的中心结点变成了交换机。交换机可以隔离冲突域，交换机的每一个端口都是一个冲突域，一个主机在一个交换域当中肯定就不会发生冲突，所以在全双工方式下不用使用 CSMA/CD 协议

IEEE802.11 无线局域网
----------------

### IEEE802.11

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220828191203130.png)

> 无线局域网所覆盖的范围能比 WIFI 范围大的多。WIFI 满足 IEEE802.11b 和 IEEE802.11g 标准

### 802.11 的 MAC 帧头格式

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220828191235821.png)

AP 指无线接入点，也称作基站，是主机想要访问网络时通过无线介质可以接入的设备。假如现在 A 主机给 B 主机发送数据，A 附近有基站 AP1，B 附近有基站 AP2，AP1 和 AP2 之间是一个无线或有线网络。A 先把信息通过电磁波发给 AP1，然后 AP1 再发给 AP2，AP2 再通过电磁波传给 B

此时 DA 是 MAC B，SA 是 MAC A。接收端和发送端是在实际通信过程当中实现接收和发送数据的两个基站，因此 RA 是 MAC AP2，TA 是 MAC AP1

> 为什么到一个新的地方能收到欢迎短信？
> 
> 中国移动和中国电信在全国各地分布有非常多的基站，基站的数据库会经常更新。我们手持移动设备行走时保持电话号码被注册在离手机最近基站的数据库当中

上面只是 802.11 标准当中的一种帧类型，802.11 会把帧分成四种类型，不同的帧类型对应不同的地址字段：

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220828192021908.png)

> To AP 是要发往 AP 的帧，接收端是 AP 的 MAC 地址 BSSID
> 
> From AP 是从 AP 发来的帧，发送端是 AP 的 MAC 地址 BSSID

### 无线局域网分类

分为有固定基础设施无线局域网和无固定基础设施无线局域网的自组织网络

### 有固定基础设施无线局域网

一个 AP 包括所覆盖范围内的各个主机构成一个基本服务集 BSS

AP1 和 AP2 可以实现 BSS 范围内的各个主机之间进行通信。如 A 主机可以和 C 主机进行通信，因为都在 AP1 所覆盖的范围内。A 会发送信号给 AP1，AP1 根据它所发送的数据帧找到对应端口发出给 C

也可以实现漫游，让不同 BSS 范围内的主机进行通信。如 A 主机可以借助分配系统 DS 和 B 主机进行通信，DS 把无线和有线结合在一起，AP 都会接入到一个有线线缆上，A 先把数据发给 AP1，通过线缆到 DS 当中进行有线通信，数据通过线路到 AP2，再由 AP2 转发给 B

这样几个 ESS 组合在一起就形成了一个扩展的服务集 ESS

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220828194208234.png)

我们在连 WIFI 时可以看到很多 WIFI 名，WIFI 名又叫服务集标识符，每一个分别对应一个 AP

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220828192923749.png)

### 无固定基础设施无线局域网的自组织网络

没有任何转发器、集线器、路由器、基站等等，一些主机自己组成一个网络，每一台主机都可以充当路由器的功能，既可以发送数据也可以帮忙转发数据，各结点之间地位相互平等，而且每一个结点都可以任意地移动

组网的过程也非常简单，只需要把所有主机安排在一个网段

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220828195142229.png)

广域网及相关协议
--------

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220829001426286.png)

### 广域网

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220829000354078.png)

> 结点交换机是链路层设备，和路由器的区别在于只能在单个网络中转发分组

> 局域网和广域网的区别：
> 
> 在广域网当中可以有交换机、集线器、路由器，覆盖的网络体系结构层次从物理层一直到网络层。而局域网只覆盖物理层和链路层
> 
> 局域网普遍采用逻辑上为总线型的多点接入技术。广域网多采用点对点链路，全双工或半双工通信模式
> 
> 广域网强调资源共享，局域网强调数据传输

### PPP 协议的特点

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220829000430012.png)

> 使用拨号上网，宽带入网时一般都使用 PPP 协议

### PPP 协议应满足的要求

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220829000527788.png)

> 在设计因特网体系结构时，把最复杂的部分都放在了 TCP 协议当中，而 IP 协议较简单，主要提供不可靠的传输服务，因此链路层就没有必要在 IP 层之前实现可靠传输
> 
> 实际生活应用当中主要靠 TCP 协议实现差错控制和流量控制，而网络层和链路层基本实现的都是不可靠，尽最大努力交付的传输，原因在于现在对网络的速率要求比较高

> 异步线路在传输过程中逐个字节或逐个字符发送，同步线路是一位位 bit 发送

> 差错检测使用 CRC 码

> MTU 默认不超过 1500B，因为是全双工通信不使用 CSMA/CD 协议，不需要最短帧长

> 数据压缩协商 —— PPP 协议需要在发送数据时对数据进行压缩

### PPP 协议无需满足的要求

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220829000632946.png)

> 不支持多点线路 —— 只需要满足点对点之间的连接过程

### PPP 协议的三个组成部分

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220829000659033.png)

> 身份验证 —— 比如拨号上网时要输入账号和密码，否则无法满足 LCP 协议连不上网

### PPP 协议的状态图

点开宽带连接输入账号密码建立物理链路，LCP 把物理链路构造成 LCP 链路，LCP 链路再经过 NCP 的配置协商形成 NCP 链路，此时才能正式访问网络上的内容

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220829000736568.png)

### PPP 协议的帧格式

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220829000849092.png)

> 遇到转义字符也在它前面插入一个转义字符
> 
> PPP 协议既可以用 0 比特插入法，也可以用插入转义字符实现透明传输

> A 地址字段和 C 控制字段没有携带有用信息

> 面向字节 —— 帧格式以字节为单位，传输时逐个字节发送
> 
> 面向比特 —— 帧格式以 bit 为单位，传输时是一连串连续的 bit 位
> 
> 每个 PPP 帧都是整数个字节

### ~HDLC 协议~

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220829001119108.png)

HDLC 的站

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220829001213582.png)

HDLC 的帧格式

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220829001238102.png)

PPP 协议 & HDLC 协议

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220829001329393.png)

数据链路层设备
-------

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220829112033925.png)

> 网桥核心功能和交换机类似，非 408 考点

### 物理层扩展以太网

主机和集线器之间的距离不能超过 100m，否则就会严重失真无法恢复。为了使距离比较远的主机之间进行通信，就要在物理层次上扩展以太网

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220829001608438.png)

> 光纤调制器把电信号转换成光信号，光纤解调器把光信号转换成电信号

> 集线器会通过所有的端口转发出去

> 冲突域 —— 在这个物理层设备所连的这些主机之内如果进行通信，同一时间只能有一台主机在发送信息，否则就会发生冲突

这样虽然能实现跨冲突域的远距离通信，扩大以太网的地理范围。但是共享通信信道主机数增多，发生冲突的概率更高，降低通信效率

### 链路层扩展以太网

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220829001733114.png)

> 网桥可以有多个端口，但不会很多

> 若每个网段的带宽是 10Mb/s，那么这三个网段合起来最大的吞吐量就变成了 30Mb/s。如果把网桥换成物理层设备，那么整个网络是一个冲突域，整个冲突域的最大吞吐量仍然是 10Mb/s

### 网桥分类 —— 透明网桥

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220829103819617.png)

> ![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/Screen%20Shot%202022-07-30%20at%2000.29.59.png)
> 
> 通信的过程中会逐步填满转发表。若上图中主机 A 要给主机 B 发送数据帧，设两网桥的左接口为 1，右接口为 2
> 
> 1.  A 发送的数据帧在网段当中广播出去，
>     
> 2.  左网桥接口 1 收到 A 帧，按照 MAC A 查找转发表
>     
> 3.  发现转发表当中没有源地址 MAC A，于是把地址 A 和收到帧的接口 1 写入到转发表当中
>     
>     ![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220829104648659.png)
>     
>     如果以后收到发往 A 的数据帧，经过左网桥处理就知道应从接口 1 发送出去
>     
> 4.  按照目的地址 MAC B 查找转发表，发现没有。因此从除了左网桥接口 1 之外的所有接口转发出去
>     
> 5.  转发出的帧会到达 C 和 D，C 和 D 发现不是给自己的就不予处理直接丢弃
>     
> 6.  帧到达右网桥接口 1，右网桥按照同样的方式处理该帧
>     
>     ![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220829105502848.png)
> 
> 为什么 A 和 B 在一个网段，还要从网桥转发出去？
> 
> 这两个网桥并不知道当时网络的拓扑情况，需要自学习算法构建转发表，这样就可以方便以后发送数据时从哪个接口转发数据帧，因此尽管帧已经被目的主机正确接收，但是发送不会停止
> 
> 若 F 要给 C 发送数据帧，B 要给 A 发送数据帧
> 
> ![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220829110347710.png)
> 
> 显然如果这个网络上每一个站都发送过帧，每一个站的地址最终都会被记录在转发表当中
> 
> 转发表几分钟更新一次，把之前的记录全部删除

### 网桥分类 —— 源路由网桥

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220829001844841.png)

> 源站以广播方式向欲通信的目的站发送一个发现帧，每个发现帧到达目的站后会原路返回或者目的站返回一个响应帧，从多个返回帧中选取需要的方案

### 多接口网桥 —— 以太网交换机

> 网桥通常只有 2 个端口

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220829002025138.png)

> 每一个端口都是一个冲突域

> 独占媒体带宽
> 
> ![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220829110929524.png)

### 以太网交换机的两种交换方式

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220829002105060.png)

> 实际生活中通常都使用存储转发式交换机

### 交换机的自学习功能

> 与网桥区别在于网桥只有两个端口，交换机有多个端口

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220829002211091.png)

### 冲突域和广播域

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220829002257561.png)

例题：

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220829002330615.png)

> 广播域：看路由器
> 
> 冲突域：看路由器和交换机。链路层设备，一个端口就是一个冲突域

VLAN 的基本概念与基本原理
---------------

### 传统局域网的局限

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220828212334063.png)

### VLAN 基本概念

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220828212357573.png)

> 可见不仅可以在一个交换机所连接的这些主机上进行划分，可以在一个大局域网中进行划分

### VLAN 实现

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220828212425679.png)

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220828212520484.png)

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220828212556810.png)

比如 A 主机要发送给 E 主机，A 主机先准备好普通的 MAC 帧，交换机 1 会在帧上新增一个 VLAN 标记字段，令其中的 VID=1 表示该帧属于 VLAN1。将该帧从 trunk 端口发出通过链路到交换机 2，交换机 2 识别出要发给 VLAN1 当中的主机，再结合 MAC 地址字段等决定发给 E 还是 F，选定 E 后会把 VLAN 标记字段去掉还原成普通的 MAC 帧再发出

> trunk 端口让这个链路当中不把 VLAN 标记字段去掉，这种交换机和交换机之间连接的端口常用 trunk 端口

### VLAN 实现 —— IEEE802.1Q 帧

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220828213042670.png)

> 用户主机和交换机之间交流和通信都是普通的 MAC 帧，不是 802.1Q 帧

练习 1：

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220828213325866.png)

练习 2：

![](https://xdu-cslee-blog.oss-cn-hangzhou.aliyuncs.com/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%E7%AC%94%E8%AE%B0%E5%9B%BE%E7%89%87/image-20220828213404783.png)

> 一个逻辑工作组也可以说是一个子网，或者说是一个广播域