### rosgraph.network

#### 概况

`rosgraph.network`是处理ROS中IP地址和ROS TCP首部的库，混合支持Python 2/3，所有的操作均在`字节`级别进行，未提供任何必要的文本编解码。
主要的功能包括：

+ 获取本机IP地址
+ 从环境变量中获取本机地址
+ 解析URL
+ 从阻塞的Socket中读写ROS Handshake Header
+ 解码/编码ROS Handshake Header

其中地址获取遵循以下优先规则：
> 命令行参数 > 环境变量 > 真实地址。

#### 潜在问题

本地地址识别有潜在BUG，`127.0.0.0/8`均被识别为本地IP，IPv6则是`::1`均被识别为本地IP。

内部的`_is_unix_like_platform`方法的逻辑使得仅仅将FreeBSD和Linux视作类Unix平台，这将导致在其他类Unix平台上，获取本地地址时，仅仅能获取primary interface的IP。这在安装了多块网卡的机器上运行时有潜在问题。

ROS Handshake Header见于本章的[公共概念][ch1-concepts]。

[ch1-concepts]: https://oopsno.gitbooks.io/a-glance-of-ros/content/chapter1/concepts.html

