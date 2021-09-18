Dockerfile here is used to build image at: https://hub.docker.com/r/nhphuong91/ros2_turtlebot

This image contain all necessary pkgs for running turtlebot3 sim

For running it, follow through below steps:
1. Setup `osrf/rocker`: https://github.com/osrf/rocker/
2. Pull `nhphuong91/ros2_turtlebot` image
3. Run docker using below command (remove `--nvidia` if unnecessary)
```bash
rocker --nvidia --x11 --volume <PATH>/<TO>/ros2_meta -- nhphuong91/ros2_turtlebot:0.1
```
> **_NOTE 1:_** For intel IGP, follow this section: https://github.com/osrf/rocker/#intel-integrated-graphics-support

> **_NOTE 2:_** See here for further info: https://github.com/osrf/rocker/#volume-mount

4. For convenience, replace defaults [`.bashrc`](./.bashrc) file (shortkeys) & [`.gazebo`](./.gazebo) (model files) within container