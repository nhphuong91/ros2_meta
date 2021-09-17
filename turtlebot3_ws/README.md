# Step to rebuild this repo
1. Clone https://github.com/ROBOTIS-GIT/turtlebot3_simulations & place it under `src` dir
2. Checkout branch `foxy-devel`
3. Navigate to same dir level as this `README` file and run `colcon build --symlink-install`
4. Source overlay: `. install/local_setup.sh` (ros2 overlay sourced) or `. install/setup.sh` (ros2 overlay NOT sourced)
5. Run demo
``` bash
export TURTLEBOT3_MODEL=waffle_pi (or burger/waffle)
ros2 launch turtlebot3_gazebo empty_world.launch.py
ros2 launch turtlebot3_gazebo turtlebot3_world.launch.py
ros2 launch turtlebot3_gazebo turtlebot3_house.launch.py
```
> **__NOTE:__** It may take a while for gazebo to download map components
6. Manual control
``` bash
ros2 run turtlebot3_teleop teleop_keyboard
```
7. Self-driving
``` bash
ros2 run turtlebot3_gazebo turtlebot3_drive
```
8. Visualize data
``` bash
ros2 launch turtlebot3_bringup rviz2.launch.py
```
9. SLAM
``` bash
ros2 launch turtlebot3_cartographer cartographer.launch.py use_sim_time:=True
```
10. Save map
``` bash
ros2 run nav2_map_server map_saver_cli -f ~/map
```
> **__NOTE:__** If there is an error, add `--ros-args -p save_map_timeout:=10000`
11. Load map
``` bash
ros2 launch turtlebot3_navigation2 navigation2.launch.py use_sim_time:=True map:=$HOME/map.yaml
```
12. Navigation 2 - read [more](https://navigation.ros.org/)
> **__NOTE:__** If loaded doesn't show tf of map origin, then init current pose may fail => reload map until it works
13. Use fake node in stead of simulation
``` bash
ros2 launch turtlebot3_fake_node turtlebot3_fake_node.launch.py
```
# ROS graph (SLAM + self-driving)
![ROS graph](../images/rosgraph_turtlebotslam.svg)