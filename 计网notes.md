---
typora-root-url: pic

---

### 计网

LAN： Local Area Networks；

WAN：Wide Area Networks;

OSI model : [开放式系统](https://baike.baidu.com/item/开放式系统/7899385)互连（OSI）标准模式

protocal:网络数据交换规则：

组成部分：在因特网上，通用[TCP/IP协议](https://baike.baidu.com/item/TCP%2FIP协议)，它由以下部分组成:一.[传输控制协议](https://baike.baidu.com/item/传输控制协议)（TCP），使用一组规则与其他的因特网[节点](https://baike.baidu.com/item/节点)在[数据包](https://baike.baidu.com/item/数据包)水平上交换信息。二.[因特网协议](https://baike.baidu.com/item/因特网协议)（IP），使用一套规则来在因特网地址水平上发送和接收消息。

其他协议：另外还包括[超文本传输协议](https://baike.baidu.com/item/超文本传输协议)（HTTP）和[文件传输协议](https://baike.baidu.com/item/文件传输协议)（FTP），以及[边界网关协议](https://baike.baidu.com/item/边界网关协议)（BGP）和[动态主机配置协议](https://baike.baidu.com/item/动态主机配置协议)（DHCP），简易邮件传输通讯协议（SMTP），邮局通讯协定（POP3）,网络通讯协议（TCP/IP）,[用户数据报协议](https://baike.baidu.com/item/用户数据报协议/8535496)（UDP）

OSI Reference Model：7层

TCP/IP Model：4层

六种网络拓扑结构：[六种基本网络拓扑结构 - 知乎 (zhihu.com)](https://zhuanlan.zhihu.com/p/267710797)



[TOC]



#### 一.物理层		设备：hubs, repeater(中继器)，

双绞线线序[(12条消息) 双绞线_weixin_34384557的博客-CSDN博客](https://blog.csdn.net/weixin_34384557/article/details/92872906)补充P48

波特率，比特率

模拟信号即连续信号；数字信号即离散信号

编码（coding）：将一种数字信号转变成另一种数字信号

编码方式：1.不归零制	2.归零制	3.曼彻斯特编码	4.差分曼彻斯特编码

信道复用：1.频分复用FDM	2.时分复用TDM（同步；异（STDM））	3.波分复用（不同波长光信号）	4.码分复用（不同码型）



#### 二.数据链路层		设备：switches, bridges

![image-20220409161926947](https://s2.loli.net/2022/04/19/qpxdaXU9LvDCBW8.png)

PPP协议：[(12条消息) 计算机网络——数据链路层PPP、CSMA/CD协议_T-aurora的博客-CSDN博客_ppp和csma/cd](https://blog.csdn.net/weixin_43419753/article/details/103657096)

封装成帧：（帧：frame）

透明传输：帧首：SOH定界控制字符，帧尾：EOT

差错检测：

数据链路层拆成两个子层：LLC（逻辑链路控制），MAC（媒体接入控制）

##### CSMA/CD协议：

​	Carrier Sence Multiple Acess with Collision Detection载波监听多点接入/碰撞检测：{

​	多点接入：表示采用的是总线型网络；	载波监听：即检测信道，检测总线上是否有其他计算机正在发送，不论发送前还是发送中每个站都必须不停检测信道。		碰撞检测：边发送边监听，判断是否有其他站也在发送数据。

使用CSMA/CD协议时，一个站点不可以同时接收和发送，因此使用CSMA/CD协议的以太网不可能进行全双工通信，只能进行双向交替通信（半双工通信）。【全双工和半双工的区别是：

​	1、全双工允许数据在两个方向上同时传输。

​	2、半双工允许数据在两个方向上传输，但是同一时间数据只能在一个方向上传输，实际上是切换的单工。】

}

单播：一对一；	多播：一对多；	广播：一对全体

MAC地址（硬件地址）：即适配器地址，与主机所在地点无关。源地址与目的地址都是48位

计算机通过适配器（网卡）与局域网通信

拓展以太网：使用网桥，交换机

以太网发送的数据都采用**曼彻斯特编码**的信号。

CSMA/CA



#### 三.网络层		设备: routers

数据报：datagram

![image-20220418140855045](https://s2.loli.net/2022/04/19/5VlUOHzBcdifSnC.png)

##### IP地址：

{32位标识符，网络号+主机号（点分十进制记法）

![image-20220411151632737](https://s2.loli.net/2022/04/20/ZhOGXQqse6pFHTw.png)

******A，B，C级ip地址所能指派的网络号和主机号：

******多播ip地址范围：

}

##### ip数据报格式：

{

![image-20220411161304746](https://s2.loli.net/2022/04/20/Gz2l86AqsQegvVw.png)

IP数据报越短，路由转发的速度越快。

}

##### 子网：

ip地址 = 网络号+子网号+主机号

子网数，每个子网的主机数计算（需要留意是否子网号能为全0/全1）

##### 无分类编址CIDR：

{IP地址 = 网络前缀 + 主机号

斜线记法

网络前缀相同的连续IP地址记为一个 地址快 

32位地址掩码

}

##### 网际控制报文协议ICMP：

{ICMP报文构成ip数据报的数据部分；IP数据报 = 首部 + 数据部分（ICMP报文）

ICMP报文种类：ICMP差错报告报文  ， ICMP询问报文

![image-20220418141901987](https://s2.loli.net/2022/04/20/3ZILCxEYk6Vj7GB.png)

![image-20220418141106221](https://s2.loli.net/2022/04/20/mcMzJ6iWoVUqlxt.png)

![image-20220418141435554](https://s2.loli.net/2022/04/20/t9H4YvNx2rGinfa.png)



应用： 1. PING（ICMP回送请求或回答报文）

​			2.traceroute(或tracert)（ICMP时间超过差错报告报文）

}

##### ARP协议（MAC地址和IP地址的映射）：

![image-20220418134342174](https://s2.loli.net/2022/04/20/URzis5DAaTYQkNr.png)



##### DHCP协议（动态获取IP地址）：

![image-20220418140750712](https://s2.loli.net/2022/04/20/FcJ3kBw6CDSzvTE.png)



##### IPv6

128位，8字节对齐

地址表示：冒号十六进制表示法（零压缩只能使用1次），CIDR斜线表示法

数据报格式：

![image-20220418152401122](https://s2.loli.net/2022/04/20/yn2ldwoKIAkic1J.png)

ipv4与ipv6区别：

![image-20220418152545790](https://s2.loli.net/2022/04/20/w5keaOz4JQ6Ytrp.png)

##### RIP协议：

小规模互联网

仅和相邻路由器交换信息，交换的信息为路由表，每30s相邻路由器交换信息。

跳数为16表示不可达

好消息传得快，坏消息传得慢

RIP 协议是应用层协议，通过UDP 传送数据

##### OSPF协议：

![image-20220418170210523](https://s2.loli.net/2022/04/20/HbpN7oEcwv8VkY6.png)

OSPF直接用IP数据报传送。

##### 多播

多播地址范围：224.0.0.0~239.255.255.255 (D类地址)

一个D类地址表示一个多播组



#### 四：传输层

端口：是传输层的SAP，标识主机中的应用进程

端口号只有本地意义，不同计算机的相同端口没有联系

端口号长度16bit,共能表示65536个不同的端口号。熟知端口号：0~1023

套接字socket = （主机IP地址，端口号），唯一标识了网络中的一个主机和它上面的一个进程。



##### UDP协议

无连接的用户数据报协议UDP

不保证可靠交付，无连接，时延小，面向报文适用于小文件

![image-20220418221436099](https://s2.loli.net/2022/04/20/HcaIfRGCwD4mV3U.png)

UDP首部格式：8字节固定首部

![image-20220418222111047](https://s2.loli.net/2022/04/20/wMN8rCvjHpyc1XK.png)

##### TCP

面向连接的传输控制协议TCP

可靠交付，面向连接，时延大，适用于大文件，全双工

TCP报文首部格式：20字节固定首部

![image-20220419094810364](https://s2.loli.net/2022/04/20/eTdvZofRzw3AytW.png)





