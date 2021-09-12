# Containerize ROS2
1. Using [osrf/rocker](https://github.com/osrf/rocker)
2. For multiple input to the same container: using `docker exec` to run new `bash`
``` bash
docker exec -it <container ID> bash
source ./ros_entrypoint.sh
```
