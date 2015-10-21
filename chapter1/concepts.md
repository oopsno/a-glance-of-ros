## 公共概念

### ROS Handshake Header

这是一种极其类似HTTP 1.1首部的结构，但针对字节传送进行了调整。具体结构如下：

> (4-byte length + [4-byte field length + field=value ]\*)

其中length字段为32为无符号整数。

Python实现中，仅仅通过字符串（字节）复制实现，未提供必要的Unicode支持。
每条键值对中的第一个`=`生效且**`=`无法转义**。


