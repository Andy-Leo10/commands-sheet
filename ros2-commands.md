# ROS2 commands

- [ROS2 commands](#ros2-commands)
  - [For general use:](#for-general-use)
  - [Update dependencies](#update-dependencies)
  - [Set environment variables](#set-environment-variables)
  - [For compiling:](#for-compiling)
  - [For compiling certain package:](#for-compiling-certain-package)
  - [For nodes:](#for-nodes)
  - [For messages:](#for-messages)
  - [Useful tools:](#useful-tools)

## For general use:
```
ros2 pkg create <PKG_NAME> --build-type ament_cmake --dependencies <DEPENDENCIES>
ros2 pkg list
colcon_cd
ros2 topic list
ros2 topic info <TOPIC_NAME>
ros2 topic hz <TOPIC_NAME>
```

## Update dependencies
```
cd ~/ros2_ws/;
rosdep init && rosdep update;
sudo apt update;
rosdep install --from-paths src --ignore-src -r -y --skip-keys='ros-humble-warehouse-ros-mongo' || true
```

## Set environment variables
```
echo 'export IGN_GAZEBO_RESOURCE_PATH=$IGN_GAZEBO_RESOURCE_PATH:/<PATH>' >> /etc/bash.bashrc
source /etc/bash.bashrc 
echo $IGN_GAZEBO_RESOURCE_PATH
```

## For compiling:
Normal
```
cd ~/ros2_ws/;
colcon build;
source install/setup.bash
```
Hiding logs
```
colcon build --packages-select <PKG> 2> /dev/null
```

## For compiling certain package:
```
cd ~/ros2_ws/;
colcon build --packages-select <PKG_NAME>;source install/setup.bash
```

## For nodes:
```
ros2 run <PKG_NAME> <NODE_NAME> --ros-args
ros2 run <PKG_NAME> <NODE_NAME> --log-level debug
ros2 run <PKG_NAME> <NODE_NAME> --ros-args <ARGUMENT>:=<VALUE>
ros2 launch <PKG_NAME> <LAUNCH_FILE_NAME> --show-args
ros2 launch <PKG_NAME> <LAUNCH_FILE_NAME> <ARGUMENT>:=<VALUE>
ros2 node list
ros2 node info <NODE_NAME>
ros2 doctor --report
```

## For messages:
```
ros2 topic echo <TOPIC_NAME>
ros2 topic pub <TOPIC_NAME> <MSG_TYPE> <MSG_DATA>
ros2 interface show <INTERFACE_NAME>
ros2 interface proto <INTERFACE_NAME>

ros2 service list
ros2 service info <SERVICE_NAME>
ros2 service type <SERVICE_NAME>
ros2 service call <SERVICE_NAME> <SERVICE_TYPE> <SERVICE_DATA>

ros2 action list
ros2 action info <ACTION_NAME>
ros2 action type <ACTION_NAME>
ros2 action send_goal <ACTION_NAME> <ACTION_TYPE> <ACTION_GOAL>
ros2 action send_goal <ACTION_NAME> <ACTION_TYPE> <ACTION_GOAL> --feedback
ros2 action send_goal -f <ACTION_NAME> <ACTION_TYPE> <ACTION_GOAL>
ros2 action send_goal <ACTION_NAME> <ACTION_TYPE> <ACTION_GOAL> --result

## For parameters:
ros2 param list /<NODE_NAME>
ros2 param describe /<NODE_NAME> <PARAM_NAME>
ros2 param get /<NODE_NAME> <PARAM_NAME>
ros2 param set /<NODE_NAME> <PARAM_NAME> <VALUE>
ros2 param dump /<NODE_NAME> # For copying parameters in .yaml file
ros2 param load /<NODE_NAME> <PARAM_FILE>
```

## Useful tools:
```
ros2 run tf2_tools view_frames # For visualizing the frames in .pdf file
ros2 run tf2_tools tf2_echo <FRAME_REFERENCE> <FRAME_TARGET> # For getting the transform between two frames
ros2 run tf2_tools tf2_monitor <FRAME_REFERENCE> <FRAME_TARGET> # For monitoring the transform between two frames
ros2 run rqt_tf_tree rqt_tf_tree # For visualizing the tf tree
```
