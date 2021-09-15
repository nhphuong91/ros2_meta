FROM osrf/ros:foxy-desktop

# setup keys
RUN apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys C1CF6E31E6BADE8868B172B4F42ED6FBAB17C654

RUN apt update && \
    apt upgrade -y && \
    apt install -y python3-rosdep2 \
        ros-foxy-gazebo-* \
        ros-foxy-cartographer \
        ros-foxy-cartographer-ros \
        ros-foxy-navigation2 \
        ros-foxy-nav2-bringup \
        ros-foxy-dynamixel-sdk \
        ros-foxy-turtlebot3-msgs \
        ros-foxy-turtlebot3

ENTRYPOINT ["/ros_entrypoint.sh"]
CMD ["bash"]
