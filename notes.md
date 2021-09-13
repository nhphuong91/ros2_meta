# Important notes for ROS2
* ROS2 uses term `Workspace` to indicate your devel location - [link](https://docs.ros.org/en/foxy/Tutorials/Configuring-ROS2-Environment.html#background)
* No more 'roscd' - [Why?](https://answers.ros.org/question/277801/ros2-roscd-feature/)
> **_NOTE:_** If needed, refer to [colcon_cd](https://github.com/colcon/colcon-cd)
* ROS2 use [DDS](http://en.wikipedia.org/wiki/Data_Distribution_Service)
* Replace `ROS_HOSTNAME/ROS_MASTER_URI` with `ROS_DOMAIN_ID` (0-101 and 215-232) - [see more](https://docs.ros.org/en/foxy/Concepts/About-Domain-ID.html)
> **_NOTE 1:_** Running more than 120 ROS2 processes on one computer may spill over into other domain IDs or the ephemeral ports

> **_NOTE 2:_** Maximum number of processes that should be created when using domain ID 101 on Linux is 54

* Message type is structured as `<pkg>/<type (msg/srv/act)>/<name>` - see [sample here](https://docs.ros2.org/foxy/api/test_msgs/index-msg.html)
# Architecture
## Node
* ROS comprised of nodes
* Each node do 1 or more specific functions
* Nodes communicate with each other using various type of messages
![Node architecture](./images/Nodes-TopicandService.gif)
## Message
* 3 types of messages: Topic, Service, Action
### Topic
* Working in Publisher-Subcriber manner
![Topic message](./images/Topic-MultiplePublisherandMultipleSubscriber.gif)
### Service
* Working in Server-Client manner
![Service message](./images/Service-MultipleServiceClient.gif)
### Action
* Mix of Pub-Sub & Ser-Cli
![Action message](./images/Action-SingleActionClient.gif)