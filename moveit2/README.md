Source: http://moveit2_tutorials.picknik.ai/doc/getting_started/getting_started.html

Quick commands to setup this directory:
```bash
sudo apt install python3-rosdep
rosdep update
sudo apt install python3-colcon-common-extensions python3-colcon-mixin
colcon mixin add default https://raw.githubusercontent.com/colcon/colcon-mixin-repository/master/index.yaml
colcon mixin update default
sudo apt install python3-vcstool
cd src
git clone https://github.com/ros-planning/moveit2_tutorials.git -b foxy
vcs import < moveit2_tutorials/moveit2_tutorials.repos
rosdep install -r --from-paths . --ignore-src --rosdistro $ROS_DISTRO -y
cd ..
colcon build --mixin release
# source install/setup.bash or install/local_setup.bash
```
> **_NOTE:_** If issue occurs, checking for failed pkgs installation (ex: `ros-foxy-graph-msgs`)