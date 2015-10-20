# ROS通信机制

ROS的通信机制主要实现在Github仓库[`ros/ros_comm`][repo_ros_comm]中。

> ROS communications-related packages, including core client libraries (roscpp, rospy, roslisp) and graph introspection tools (rostopic, rosnode, rosservice, rosparam).

该仓库主要包含C++、Python和CommonLisp下的ROS的客户端

+ [`rospy`][src_rospy]
+ [`roscpp`][src_roscpp]
+ [`roslisp`][repo_roslisp]

和一些列的关键的工具，如

+ [`rostopic`][src_rostopic]
+ [`rosnode`][src_rosnode]
+ [`rosservice`][src_rosservice]
+ [`rosparam`][src_rosparam]

这一章的主要分析对象是`ros_comm`中的Python实现。

<!-- GitHub Repos -->
[repo_ros_comm]: https://github.com/ros/ros_comm
[repo_roslisp]: https://github.com/ros/roslisp
[repo_genpy]: https://github.com/ros/genpy
[repo_gencpp]: https://github.com/ros/gencpp
<!-- SRC -->
[src_rospy]: https://github.com/ros/ros_comm/tree/indigo-devel/clients/rospy
[src_roscpp]: https://github.com/ros/ros_comm/tree/indigo-devel/clients/rospy
[src_rostopic]: https://github.com/ros/ros_comm/tree/indigo-devel/tools/rostopic
[src_rosnode]: https://github.com/ros/ros_comm/tree/indigo-devel/tools/rosnode
[src_rosservice]: https://github.com/ros/ros_comm/tree/indigo-devel/tools/rosservice
[src_rosparam]: https://github.com/ros/ros_comm/tree/indigo-devel/tools/rosparam
