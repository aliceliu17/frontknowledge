# HTTP 协议

HTTP = HyperText Transfer Protocol, 是网络中的应用层协议， http 是建立在 TCP 协议之上的
**此处需要了解下 ISO 七层模型**
ISO 于 1978 年开发的一套标准架构 ISO 模型，被引用来说明数据通信协议的结构和功能。

OSI 在功能上可以划分为两组：

- 网络群组：物理层、数据链路层、网络层

- 使用者群组：传输层、会话层、表示层、应用层

- OSI:

* 物理层：EIA/TIA-232, EIA/TIA-499, V.35, V.24, RJ45, Ethernet, 802.3, 802.5, FDDI, NRZI, NRZ, B8ZS
* 数据链路层：Frame Relay, HDLC, PPP, IEEE 802.3/802.2, FDDI, ATM, IEEE 802.5/802.2
* 网络层：IP，IPX，AppleTalk DDP
* 传输层：TCP，UDP，SPX
* 会话层：RPC,SQL,NFS,NetBIOS,names,AppleTalk,ASP,DECnet,SCP
* 表示层:TIFF,GIF,JPEG,PICT,ASCII,EBCDIC,encryption,MPEG,MIDI,HTML
* 应用层：FTP,WWW,Telnet,NFS,SMTP,Gateway,SNMP

**容易混淆概念**
SSH： SSH 为 Secure Shell 的缩写，由 IETF 的网络小组（Network Working Group）所制定；SSH 为建立在应用层基础上的安全协议。来自百科复制，个人理解是应用层，在 ENSP 上测试，过滤 TCP 的 SYN 头部的包无法通信 SSH，所以需要依赖传输层 TCP 封装, TCP 的上面一层
Socket: 套接字（socket）是通信的基石，是支持 TCP/IP 协议的网络通信的基本操作单元。它是网络通信过程中端点的抽象表示，包含进行网络通信必须的五种信息：连接使用的协议， 本地主机的 IP 地址，本地进程的协议端口， 远地主机的 IP 地址，远地进程的协议端口。
![图示理解](images/sockethttp.png)

**HTTP 本身进化**

- 1）在 HTTP 1.0 中，客户端的每次请求都要求建立一次单独的连接，在处理完本次请求后，就自动释放连接。

- 2）在 HTTP 1.1 中则可以在一次连接中处理多个请求，并且多个请求可以重叠进行，不需要等待一个请求结束后再发送下一个请求。
