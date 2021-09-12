# Important notes for ROS2
* ROS2 uses term `Workspace` to indicate your devel location - [link](https://docs.ros.org/en/foxy/Tutorials/Configuring-ROS2-Environment.html#background)
* No more 'roscd' - [Why?](https://answers.ros.org/question/277801/ros2-roscd-feature/)
> **_NOTE:_** If needed, refer to [colcon_cd](https://github.com/colcon/colcon-cd)
* ROS2 use [DDS](http://en.wikipedia.org/wiki/Data_Distribution_Service)
* Replace `ROS_HOSTNAME/ROS_MASTER_URI` with `ROS_DOMAIN_ID` (0-101 and 215-232) - [see more](https://docs.ros.org/en/foxy/Concepts/About-Domain-ID.html)
> **_NOTE 1:_** Running more than 120 ROS2 processes on one computer may spill over into other domain IDs or the ephemeral ports

> **_NOTE 2:_** Maximum number of processes that should be created when using domain ID 101 on Linux is 54

