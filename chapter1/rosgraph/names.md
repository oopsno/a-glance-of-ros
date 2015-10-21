### rosgraph.names

> ROS的Names机制详见于[Names - ROS Wiki](http://wiki.ros.org/Names)。

本模块设计用于维护ROS中的Names。

#### 简表

本模块中的公共函数一共有14个，遗憾的是其中一部分命名比较混乱，整理如下：

|函数名|功能|
|`get_ros_namespace`|按默认优先级顺序获取ROS Namespace|
|`make_caller_id`|生成指定Name在ROS Namespace下的版本|
|`make_global_ns`|生成指定Name在全局命名空间下的版本|
|`is_global`|判断是否属于全局命名空间|
|`is_private`|判断名字是否私有|
|`namespace`|__从名字中获取命名空间__|
|`ns_join`|如果可能，连接命名空间，否则返回原名|
|`load_mappings`|从命令行参数列__解析__命名映射|
|`is_legal_name`|合法性检查|
|`is_legal_base_name`|Base Name的合法性检查|
|`canonicalize_name`|规范化一个名字|
|`resolve_name`|__构造__一个规范的、带命名空间的名字|
|`script_resolve_name`|__构造__一个脚本的名字|
|`anonymous_name`|随机生成一个Name|

#### 潜在问题

`namespace`的实现对空字符串返回全局命名空间：
```python
if not name:
    return SEP
```

`is_legal_name`对空字符串返回`True`。

`load_mappings`没有默认参数，需要手动指定。

`anonymous_name`的生成算法有小概率引发冲突。
```python
def anonymous_name(id):
    """
    Generate a ROS-legal 'anonymous' name

    @param id: prefix for anonymous name
    @type  id: str
    """
    import socket, random
    name = "%s_%s_%s_%s"%(id, socket.gethostname(), os.getpid(), random.randint(0, sys.maxsize))
    # RFC 952 allows hyphens, IP addrs can have '.'s, both
    # of which are illegal for ROS names. For good
    # measure, screen ipv6 ':'. 
    name = name.replace('.', '_')
    name = name.replace('-', '_')                
    return name.replace(':', '_')
```






