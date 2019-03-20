+++
title = "Skywire - 天空币网状网项目"
tags = [
    "Skywire",
]
date = "2017-08-29"
aliases = [
	"/zh/overview/skywire-skycoin-meshnet-project"
]
+++

- [简介](#简介)
- [路由: 概览](#路由-概览)
- [激励措施：付款协议](#激励措施付款协议)
- [源路由：链路层加密](#源路由链路层加密)
    - [协议例子，节点A和B通信](#协议例子节点a和b通信)
    - [可能的改进：](#可能的改进)
- [IPv4网关：绕过现有的ISPs](#ipv4网关绕过现有的isps)
    - [例子1:](#例子1)
    - [例子2:](#例子2)
- [Skywire守护进程服务架构：](#skywire守护进程服务架构)
    - [示例服务：区块链同步](#示例服务区块链同步)
        - [查找Peers：](#查找peers)
        - [发送接收消息。](#发送接收消息)
- [多主路由和链路聚合：](#多主路由和链路聚合)
- [Meshnet路由：存储和转发](#meshnet路由存储和转发)
- [存储和转发：容量利用率](#存储和转发容量利用率)
- [存储和转发：示例](#存储和转发示例)
    - [正常运行示例](#正常运行示例)
    - [拥塞的例子](#拥塞的例子)
    - [丢包的例子](#丢包的例子)
- [存储和转发：带宽延迟产品](#存储和转发带宽延迟产品)
- [存储和转发：容量利用，质量和服务](#存储和转发容量利用质量和服务)
- [源路由：多路由移动连接](#源路由多路由移动连接)
- [源路由：多路可靠性](#源路由多路可靠性)
- [源路由：Guard节点](#源路由guard节点)
- [源路由：BGP的限制](#源路由bgp的限制)
- [虚拟路由：Skywire网络拓扑扩展性](#虚拟路由skywire网络拓扑扩展性)
- [源路由：虚拟路由，SONET拓扑](#源路由虚拟路由sonet拓扑)
- [源路由：不对称连接](#源路由不对称连接)
- [源路由：路由发现](#源路由路由发现)

## 简介

Skywire 项目目标:

* 针对最后一公里的宽带网络，提供一个当前互联网接入提供商们(ISPs)的额外选择，以增加带宽竞争
* 激励社区来构建运行在用户操作基础架构上的ISPs.

Skywire 是一个新的暗网协议.

* 低延迟 (和TCP/IP一样快，如运行在原生网络则理论上比TCP/IP更快)
* 高性能(被设计用来处理视频、文件共享和其它高吞吐的应用)
* 隐私保护
* 支持在WIFI上运行 (网状网)
* 支持在明网上运行 (叠加暗网)

Skywire解决了网络部署的激励和逃离问题。

* 用户通过提供网络资源来获得天空币
* 用户通过消耗网络资源来花费天空币

Skywire 是开放接入的.

* 任何人通过一个客户端，都可以接入Skywire节点
* 目标是要创建一个全球性的开放接入的网状网

Skywire 是隐私保障的.

* 在Skywire网络节点转发的流量不会被反向跟踪到你IP地址
* 数据中转的节点只能看到上一个节点和下一跳的节点
* 第三方被动监测无法将单独的数据包链接到流或用户
* 第三方和数据转发节点不能够读取到流量的内容

## 路由: 概览

Skywire网状网使用源路由的存储和转发协议

叠加网络的核心是一些列的节点

* 每一个节点用公钥地址标识
* 每一个节点接收和转发消息
* 节点转发流量会获得天空币

比如节点A和C通过节点B来通讯A->B->C

* 节点 A 连接到 节点 B， 建立路由
* 节点 A 扩展路由到节点 C
* 在节点A上通过该路由的流量会到达节点C

针对路由 `A -> B -> C -> D`:

* 节点只知道前一条和下一跳.
* C 知道消息是从B发送过来的并且要发送到D，但是C不知道节点A的标识信息
* B 不能够推测A是消息的最初发送节点.
* C 不能确定D是消息的最终节点
* B 和 C 不能读取消息的内容 (端到端加密)
* 一个被动观察者不能获得传递消息的内容信息(链路层加密).
* 可以捆绑多条路由到同一目的地址的多条消息，从而降低被动观察者进行流量分析的能力。


最简单的实现是路由有一个128比特的前缀，每个节点通过前缀查路由表确定数据包传送的下一个地址

源地址对路由有完全对控制

* 每个节点可以独立对升级它对路由协议来适应新对需求
* 源路由可以针对延迟来优化网络路径来优化游戏和VOIP应用等
* 源路由可以针对吞吐量优化网络路径，比如文件传输和视频应用
* 源地址可以绑定多个到目的路由来提高冗余、减少延迟、提高吞吐量
所以，应用程序可以在应用层绑定多个并行的路由达到
* 更好对隐私 (网关节点，类似tor网关匿名服务等等)
* 高吞吐量
* 降低延迟
* 冗余


这是Skycoin覆盖网络的核心。 这是非常简单，但非常强大的。
技术和实施细节将在下面讨论。

Skywire通过简单地将数据包增加一个路由ID的前缀来实现。

* 路由是非常简单的表查询
* 每个包的额外头信息是一个常数，不管这个路由有多长


注意:

* 目的地不知道原始发送地的标识，标识不在路由层, 但是在应用层，标识必须通过公钥体系确认
* 中间人攻击不可能发生，源地址可以通过公钥来验证目的地.
*  隐私相对于IPV4得到了极大的提高，在ipv4中，任何人都可以查看数据包的内容、源地址和目的地址.
* 性能好过IPv4/BGP，因为大部分ISPs 使用 hot-potato路由算法
* 端到端的加密消除了包注入攻击和欺骗，因为要做流量欺骗必须有每个连接通道的各自的私钥
* 加密快速. 使用FPGA必须支持10Gb/s的线速，ARM处理器支持250Mb/s

## 激励措施：付款协议


![Skywire 矿机](https://i.imgur.com/2zj4CUV.jpg)

*[Skywire "矿机"](/statement/skywire-miner-hardware-for-the-next-internet/)*

节点通过转发流量来获得天空币。 这相当于Skycoin中的“采矿”，有许多用户会因此获得第一批天空币。

付款的传送路径不应显示源节点的身份。 Skycoin将通过第三方使用并盲注托管付款，直到开发出更好的协议。


路由中的每个节点记录流量，源节点记录流量。他们定期处理带宽支付。


源地址用第三方持有天空币。 假名帐户是与第三方一起创建的。 每个节点可以通过第三方验证起源地址的支付能力和声誉，而无需研究对方的身份。 对于第三方，每个来源将显示为多个未链接的假名帐户。 每个传输节点将显示为多个未链接的假名帐户。


小额交易将在内部交易中进行结算。 一旦平衡超过阈值（目前为1个Skycoin），这些链下(既不在区块链网络上)交易可以提取到新生成的，从未使用过的地址。 这减少了区块链膨胀，并鼓励微支付交换通过链下进行。

## 源路由：链路层加密

在多跳节点之间和端到端之间存在默认的链路层加密。 典型的应用将使用链路层加密，端到端加密，适当的应用层加密


节点之间加密应该快速，使用FPGA必须支持10Gb/s的线速，ARM处理器支持250Mb/s

当前最好的候选算法是：ChaCha20 with ECC secp256k1 短暂密钥交换.


ChaCha20仅使用简单的算术运算，在嵌入式设备上比AES更快，比AES更能抵抗定时通道攻击

现代CPU可以每秒执行6000 secp256k1 ECDH操作。 会话密钥轮换应该是每秒一次或两次在节点之间的往返， 每个通信方向应该有一个单独的密钥。

上一个会话密钥应该被累积到通过ECDH秘密接收。


通过公共密钥加密（ECC）建立的会话密钥用于使用更快的非对称加密算法（AES，ChaCha20）加密通信。 这是节点之间的基本链路层加密。

### 协议例子，节点A和B通信

- 节点A生成一个会话密钥用于传递加密数据给节点B
- 节点B有一个公钥P，对应的私钥p，P是ECC sep256k1曲线上的一个点。p是256位整数。 P是基点b，用曲线加法运算提高到p的幂。
- 节点A生成具有私钥q的短暂公钥Q， （节点A随机生成一个20字节的整数，这是私钥q，节点A将基点提高到q的幂，生成公钥Q，这是曲线上的一个点）
- 节点A发送P * q（曲线P上的点，B为公钥，提升为q的幂）
- 节点A发送P到节点B
- 节点B接收P并计算P * q，节点A可以计算p * Q，结果是相等的，这是共享密钥，它被哈希生成会话密钥。
- P = b*q, 于是 P*q 等于 (b*p)*q.  P*q = (b*p)*q = (b*q)*p = Q*p, 既然 Q=b*q. 节点A 知道 q,Q 和 P, 节点 B 知道 p,P 和 Q. 于是节点 A 和 B 都可以计算 P*q 和 Q*p 并使用它作为秘钥 . 但是，第三方不知道节点A的私钥q 和节点B的私钥p，所以第三方无法计算出“秘钥” 不能够读取加密的内容
- 节点B确认会话密钥的更新接收，一旦从B收到确认，节点A开始在新的会话密钥下进行发送
- 节点A使用会话密钥和ChaCha20算法将消息加密发送到节点B。

### 可能的改进：

- 频繁的会话密钥更新。 ECDH密钥交换每隔几秒钟或几分钟
- 使用新的ECDH密码散列旧会话密钥以生成新的会话密钥
- 将随机数添加到数据包，并将哈希秘密添加到随机数中，以生成每条消息的密钥。 相同的钥匙永远不会重复使用。 减少已知明文攻击的影响。
- 消除消息中已知的纯文本。
- 将消息填充到16或32字节的倍数


## IPv4网关：绕过现有的ISPs

许多用户只有唯一的ISP可使用。 这简单介绍了Skywire如何增加竞争


某些应用程序可以在Skywire网络地址空间上原生运行。 一些应用程序，如Bittorrent，文件同步和通信应用程序，可以从Skywire基础架构中受益匪浅，并将可以被修改为在Skywire网络s上运行。


Netflix，Facebook，Twitter等传统应用程序需要网络网关将Skywire覆盖网络与IPv4和IPv6网络相连接。


用户选择在本地托管中心的服务器上运行的Skywire网关。 用户IPv4流量将通过网关进行隧道传输（类似于VPN）。 用户IP将显示为网关服务器的IP。 该服务器具有千兆连接到多个快速互联网主干，在不限制Netflix的提供商。 用户可以为Skywire IPv4网关提供多种选择。 网关提供商将按照计量的方式收到Skycoin来支付(成本等)。

用户家中的Skywire节点通过所有可能的路由连接到网关。 Skywire节点将路由器的IPv4流量隧道传输到托管中心的网关。 网关节点的IP地址是用户显示的IP地址。

### 例子1:

用户有一个10 Mb / s的电缆调制解调器。 他们安装了Skywire路由器。 路由器连接他们的计算机，进入Skywire Wifi节点并连接电缆调制解调器。 路由器配置为Skywire作为IPv4隧道。他们将计算机接入路由器。

Skywire wifi节点通过wifi连接到他们的邻居Skywire节点，该节点连接到10 Mb / s电缆调制解调器。 邻居还有一个200 Mb / s的5 GHz wifi，通过定向的点对点天线连接到一条在街上运行Skywire WiFi节点的业务。
用户Skywire路由器进行递归广度优先搜索具有明网连接的节点并按照下面的优先次序建立路由

- 电缆调制解调器
- wifi - >他邻居的有线调制解调器
- wifi - > 5 GHz点对点 - > 100/30 Mb / s业务/光纤
在连接到IPv4隧道时，用户将能够通过所有路由访问聚合带宽。 在总体带宽和可靠性达到一定水平的社区，用户不再需要电缆调制解调器进行连接


### 例子2:

街上的商家有一个100/30 Mb/s带SLA的光纤接入， 业务支付固定的互联网费率。 他们不使用的任何带宽都会浪费。 如果该商家开起了Skywire路由器。 路由器有3个端口。 第一个端口是他们的WAN连接，第二个端口是他们的内部网络，第三个端口到屋顶的Skywire wifi节点。 路由器缓冲并优先处理内部网络上的流量，并为Skywire流量分配未使用的容量。 该用户就能通过转发流量来接收天空币，以补贴光纤接入的成本。

## Skywire守护进程服务架构：


* 每个Skycoin节点都有一个Secpk256k1的公钥地址
* 每个Skycoin节点都有一个标识它的Skycoin地址。 该地址是节点公钥的哈希值。 该公共密钥哈希值等同于网络上的IP地址。
* 每个Skycoin节点都具有连接到的对等体的连接池。 这些可以是通过TCP，UDP 明网连接的对等体，通过直接以太网和Wifi对等体（meshnet操作）的物理连接。 连接也可以是通过物理或明网连接隧道传输的“虚拟连接”，并将在后面描述。
* 具有对等体的每个连接实例具有“通道”。 一个通道是一个16位整数，类似于TCP中的“端口”
* 发送和接收的所有消息具有32位长度前缀和16位通道。
* 通道0保留用于Skywire守护进程之间的通信，显示有关守护程序上运行的服务的元信息和网络操作所需的其他数据。
* Skywire守护进程可能会在某个频道上暴露“服务”。 服务是处理在信道上接收的数据消息并发送到远程对等体和服务的数据消息的过程。

### 示例服务：区块链同步

此示例用于Golang守护程序实现，但守护程序体系结构是语言无关的。
您想要使用公钥A和B同步两个不同的个人区块链。您启动两个“区块链同步服务”实例，使用各自的公钥配置它们，并将其与Skycoin守护程序相关联。 这些服务在本地守护程序上运行，每个守护进程都在特定通道上运行

#### 查找Peers：
区块链同步程序将哈希公钥加密，并执行DHT（分布式散列表）查找，以查找同步区块链的其他对等体。 一旦找到对等体，对等体可以通过PEX（对等体交换）彼此引入另外的对等体。


#### 发送接收消息。
创建服务时，注册他们响应并可以发送的消息列表。 消息是Golang结构体。 消息结构数据被填写然后发送。 数据到达并在相应的消息结构上调用.Handle（）方法。


## 多主路由和链路聚合：

如果您有2 Mb/s电缆调制解调器，并且您的邻居有2 Mb/s的电缆调制解调器，并且每个都运行Skywire节点，那么您的Skywire节点可以连接到他的节点，并在两个连接之间聚合带宽。 数据包现在可以通过你的电缆调制解调器进行路由，也可以通过他的电缆调制解调器进行路由 。电缆调制解调器是阻塞点，要获得4 Mb/s连接，流量必须通过两个调制解调器并行路径。

像Bittorrent这样的应用将能够在所有可用的连接之间聚合带宽，因为它们本地打开了大量连接，这将占用区域路由。



## Meshnet路由：存储和转发


对于通过网络通信的网络边缘处的节点，存在一些问题。

如果您的WiFi网络有八跳网络，每跳都会丢弃50％的数据包，那么256个数据包中只有一个将通过。 数据包丢弃在Wifi上是正常的，但传统的TCP将数据包丢弃作为拥塞并阻止连接速度。
在网络边缘，Skywire将沿着路线使用存储和转发。 这对Skywire节点施加了内存需求，但显着提高了网络性能。


对于路线A-> B-> C

* 每个路由都有一个缓冲区
* 每个节点继续发送消息，直到被收到并确认
* 如果B -> C的缓冲区已满，路由A将会知道这一点，并且将停止发送数据，直到发送的数据被确认，缓冲区空出来

因此，在链路层的节点之间有两个确认。 一个是传输的数据片段的收到和确认。 另一个是确认来自缓冲器的数据已被发送到路由中的下一个节点并被其确认。


## 存储和转发：容量利用率

在传统IP网络中，随着网络链路利用率上升，网络效率会下降。 以80％容量运行的网络面临着短期数据突发导致路由器超过容量并丢弃网络数据包的风险。

TCP对于由于任何原因丢弃的数据包，解释拥塞并控制速度。 在TCP规范里，丢弃的数据包还需要进行重传，并在应用程序处理数据包流的其余部分之前等待超时和重传，这引入了延迟。

通过使用存储和转发操作，路由缓冲区填满，没有额外操作。 当缓冲区填满时，发送数据节点停止发送数据，直到通知缓冲区有可用空间。

这种存储和转发操作对于实际的WiFi网状网络尤其重要。 在2.4GHz频带中只有三个不重叠的信道。 与无线网络的带宽饱和点相比，数据包丢失增加非常快，非常早。 Wifi分组丢失是不可避免的，不能可靠地指示拥塞或容量限制。

存储和转发允许我们以全容量运行Wifi节点，并使所有可用带宽，而不触发TCP拥塞控制。


实际网络将要求：

* 软件定义wRadio
* MIMO
* Beam Forming
* 定线天线
* 协调时间和地理传输时间，协调广播功率和频率使用
* 801.11af空白频率


## 存储和转发：示例

每个路由的每个节点都跟踪

- 用于路由的接收节点的缓冲区大小
- 预测的缓冲区大小（被传输的确认和未确认的数据）
- 确认缓冲区大小
- 每个已发送未确认的消息的偏移量，大小和顺序
- 未接收到确认的发出数据报的字节的循环缓冲区

链路层上的数据段可以包含来自寻址到同一节点的多条路由的级联消息。 这阻碍了流量分析，并通过在支持更高MTU的网络上允许较大的数据报来提高性能。

对于每个传送的消息，有两个确认。 第一个确认是数据报已被路由中的下一个节点接收。 这是数据报的一个确认，可能包含多个消息，每个消息对应不同的路由。 收到这个确认后，节点不再需要保留数据报。 如果数据报没有被确认，则需要重新发送。




第二个确认是关于路由的入站缓冲区中剩余空闲字节的更新。 如果路由缓冲区中的空闲字节足够大，则可以传输该路由的附加消息。

另一种可能的方法是为每个发送者而不是每个路由维护一个缓冲区，其中接收者向发送者发送阻塞消息以使拥塞的路由。 这减少了发送者所需的路由哈希查找的数量，并且可能需要进行实验。


### 正常运行示例


路由: `A->B->C`

* B 有 1024 KB 的路由缓存区
* A 发送 512 KB 给 B
* B 确认收到 512 KB 给 A
* < A 收到确认 (清除掉这512 KB,不再需要缓存) >
* B 转发 512 KB 给 C
* C 确认收到 512 KB
* C 给 A 确认 512 KB 已经被转发

### 拥塞的例子

路由: `A->B->C`

* B 有1024 KB 路由缓冲区
* A 向B发送512 KB
* A 向B发送256 KB
* A 向B发送256 KB
* <A停止发送，挂起，已经足够填满B的缓冲区>
* B 向A确认收到512 KB和512 KB
* B 向C发送256 KB
* C 确认收到256 KB给B
* B 向A确认256 KB给C
* < A现在可以发送，最多256 KB >

数据被假定以按照发送的顺序接收，并且是Wifi和以太网连接


### 丢包的例子


路由: `A->B->C`

* B有1024KB路由缓冲区
* A向B发送512 KB
* A向B发送256 KB
* B确认256 KB
* A推断B未收到512 KB
* A重发512 KB
* B确认512 KB
* < B现在可以继续顺序发送流给C >



## 存储和转发：带宽延迟产品


在存储和转发中，等效于往返延迟和传输速率乘以往返延迟的发射节点施加存储要求。 1 GB的RAM足以以1 Gb / s的传输速率进行8000 ms的往返延迟。

存储和转发应为默认值，但可选。

## 存储和转发：容量利用，质量和服务

视频，音频和文件下载被缓冲。 在几秒钟的时间窗口内的绝对平均吞吐量很重要，而延迟是无关紧要的。 其他流量，如网站请求，视频游戏和voip是实时的，应该尽快交付。
凭借两项服务水平，“实时”和“批量”，我们可以首先传输VOIP，网站和视频游戏流量，从而减少此流量的延迟。 延迟不敏感的流量，如视频，音乐和文件共享只会在实时流量缓冲区为空之后流过链路。

我们能够利用接近100％容量的链路，同时降低实时流量的延迟。 因此，我们提出支持两条路线的服务质量水平。


## 源路由：多路由移动连接


如果节点之间的连接稳定，低延迟并具有高带宽，那么单个路由对于大多数应用来说就足够了。 一些应用程序，如Bitorrent，打开大量的连接，本机可以使用所有可用路由的带宽。

如果节点之间的链路较慢，不可靠或连接正在发生变化，则可靠性和性能需要通过多条冗余路由进行复用。

如果在手机上运行的Skywire节点正在汽车上行驶，那么可访问的网络将会发生变化。 一些网络节点将进入可服务范围，其他网络节点将离开可服务范围。 节点应该在应用层具有连续的连接性，即使物理连接被创建和销毁。

一种方法是在网络骨干网上选择一组可靠的节点作为路由的终点，然后通过一组多个短期路由代理通过这些节点的流量。

## 源路由：多路可靠性

如果链路不可靠或具有高度可变延迟，则期望通过多个路径对应用数据进行编码，使得如果接收到来自任何路径的数据，则可以恢复数据。 存在涌泉码和其他可能在这里适用的编码方法。


## 源路由：Guard节点
对于隐私，如果用户想要进一步削弱他们的Skywire节点地址（公共密钥哈希）与其IP地址之间的可链接性，则它们可以将固定的一组节点注销为被指定为其地址的流量的传输点，或者作为从他地址路由上的所需节点。


## 源路由：BGP的限制

边界网关协议，当前的主要路由协议，通过不保持数据包的任何状态来处理路由问题。 相反，BGP允许每个网络为查看分组的源和目的地的每个路由器创建一系列特别规则，并决定将数据包转发到哪个网络接口。 路由器通过连接信息彼此发送消息，另一种路由算法用于网络域内的路由。


BGP设计用于连接一系列独立的自治网络。 BGP具有同质性假设，假定自治域内的路由是集中管理的，并且在域内具有均匀路由可靠性高。 网状网络和社区ISP将与异构设备连接和路由特征。


网状网络中的连通性，自组织配置和具有冗余多家庭路由路由的密集互连网络完全违反BGP的分层假设。

BGP的下一代协议应该解决的几个问题

* BGP不是自配置的。基于BGP的网络需要广泛的技术专长来配置和操作
* BGP系统通常需要手动配置来绕过损坏，并且不会对坏配置有弹性
* BGP需要手动创建自组织路由过滤规则，并增加具有多家庭连接的网络的复杂性
* BGP网络需要高度集中的规划
* 国家安全局在BGP中利用有缺陷的路由将目标流量路由到拦截点
* BGP的假设变得越来越紧张，特别是对于ad-hoc，mesh和移动网络
* BGP的层次式单路假设实现了多归属和其他下一代网络的需求非常困难
* 当网络链路不可靠（如路由振荡）时，BGP会遇到严重问题。
* 随着互联子网的增长，BGP路由表大小呈指数增长。
* 多宿主引起BGP路由表大小的巨大爆炸。
* BGP具有负载均衡和多家庭路由的难度。 BGP限制了实际网络中利用位置间并行连接的能力。
* BGP创造了一种激励，让ISP尽快将网络流量转储到其他网络（“Hot Potato Routing”），降低性能并延长延迟

没有其他的BGP。 BGP是其设计限制内的最佳解决方案。
BGP的后继者必须
* 是非层次的
* 自我配置（zero-conf）
* 在密集的ad-hoc网络上运行良好，冗余互连


## 虚拟路由：Skywire网络拓扑扩展性

Skywire路由实现需要一个节点来维护通过它的每个路由的信息。 单个节点无法处理数十万条单独的路由，并且通过另一种机制实现可扩展性。

Skywire正在尝试一种非层次化的自组织路由，可以有效地缩放，同时支持多重和非分层网络拓扑。

随着网络通过虚拟路由的扩展，Skywire可以最大限度地减少网络直径。 虚拟路由允许成千上万的连接通过高带宽主干连接与单个路由的开销捆绑在一起。

“虚拟路由”在现有路由上创建隧道

`A -> B -> C -> D`

虚拟路由显示为A-> D， B和C可能是高带宽长距离连接。 B和C只会导致单路由的开销，而A和D会导致在A-> D隧道上维护路由的开销。


虚拟路由可能包含从数百个从A到D的捆绑路由的流量，而B和C只会遇到单个路由的开销。 虚拟路由还可以在源和目的地之间捆绑多个冗余网络路径以实现性能，吞吐量和冗余。

虚拟路由允许网络容量大致分层地聚集，每个层上的节点具有恒定的扇区和开销。

网络边缘的节点进入聚合节点。 边缘聚合节点连接到高带宽域内传输，并馈送到网络之间的网关节点， 网关节点进入高带宽和长途运输。

虚拟路由是现有域间路由关系的表示，原生支持

* 非分层路由（数据中心）
* 多主
* 不同级别的域之间的密集网络互连
* 网络域内和之间的多路径路由

虚拟路由服从三角形平等。 如果路线A-> B的成本是C（A-> B）那么

`C(A->B->C) >= C(A->B) + C(B->C)`

原始偏好低延迟，低成本和低跳路由，创造了一种有效的网络拓扑结构的经济刺激。 网络是非层次和自组织的。 创建的虚拟路由是自然地反映流量流的路由摘要。


在BGP中，网络尝试尽可能快地消除流量（hot potato路由）。 在Skywire，网络竞争提供运输（接收天空币奖励）。 Skywire客户端将偏好，低成本，低跳数和低延迟路由。 源和目的地之间具有直接长途容量的网络具有较低的延迟和较低的跳数，会接收偏好。

为了效率，网络层次结构的每个级别的带宽容量和扇入（每个虚拟路由绑定的路由数）必须是恒定的，以便实现主机数量恒定的网络直径和对数路由表增长。


## 源路由：虚拟路由，SONET拓扑

多输入多输出虚拟路由可以物理地实现为SONET环，SONET拓扑通过每个城市中的Skywire节点，Skywire节点充当Skywire网络和SONET拓扑之间的网关路由器。

节点能够将大数据报排队，将多个消息从同一个源连接到同一个目标，以提高效率。

消息进入一个城市的托管中心的SONET环的Skywire节点。 读取消息目的地或路由，并将消息编码为通过SONET段进行传输。 消息到达SONET分段上的目的地Skywire节点，并继续其路由路径。
因此，多输入多输出虚拟路由是具有传输成本的Skywire节点的列表，描述SONET环或完全连接的拓扑，其中列表中的任何节点已经能传送数据到列表中的任何其他节点。

## 源路由：不对称连接

下一代wifi系统将在相控阵列MIMO布置中具有4x4和8x8天线。 这样的系统能够投射高度集中的定向光束。 这些系统显着增加了接收机的功率和信号强度，但不对称地提高返回信号的天线增益。

类似地，通过定向天线的高功率放大的WiFi信号可以在十五英里远的地方接收，但是从现场接收的信号不能像传输中的功率提升一样容易地被放大。

对于可以由节点接收消息但节点无法直接通信的情况，我们提出了非对称路由。 在非对称路由确认消息通过路由通过网络进行中继，从而能够通过单向通信信道充分利用非对称连接。

这种情况会变得越来越重要

* 通过定向天线放大Wifi的农村SONET部署
* 在相同功率级别广播的高方向天线和非定向天线之间的城市连接
*  802.11af系统中的混凝土渗透
* 非视线LiFi传播可以传输超过200 Mb/s，但其高度不对称
* RONJA型Li-Fi系统具有超过10 Gb/s视距的理论容量限制，并且对于不对称连接有成本/设置优势

利用不对称连接和路由，只允许节点之间直接数据传输的方式有一些进展，特别是对于农村发展，降低了下一代技术集成度的成本。

## 源路由：路由发现
用于社区ISP的IPv4网关和网状网只需要在通过明网连接的路径上进行广度优先搜索。 最好，最可靠，最高吞吐量的路线具有非常小的深度。 因此，我们考虑为这种情况解决路由。 稍后会看一般路由。
