### rosgraph.rosenv

几乎是`rosgraph`中最简单的模块，它只实现了`get_master_uri`方法，用于从命令行参数或者环境变量中获取Master节点的URI。

`rosgraph.rosgraph`中只实现了一个函数，`get_master_uri`，它以

> 命令行参数 > 环境变量 > 真实地址

的顺序获取Master节点的URI。
