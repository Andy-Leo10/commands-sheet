# ROS2 Moveit2

- [ROS2 Moveit2](#ros2-moveit2)
  - [General](#general)
  - [For installation:](#for-installation)
  - [For setup assistance:](#for-setup-assistance)
  - [For GUI of sliders:](#for-gui-of-sliders)
  - [For checking joint positions:](#for-checking-joint-positions)
  - [For checking end effector positions:](#for-checking-end-effector-positions)
  - [For general use:](#for-general-use)

## General
- [Documentation](https://moveit.picknik.ai/main/index.html)
- [Documentation Humble](https://moveit.picknik.ai/humble/index.html)

## For installation:
```
sudo apt-get update
sudo apt-get install ros-<DISTRO>-moveit
```

## For setup assistance:
```
ros2 launch moveit_setup_assistant setup_assistant.launch.py
```

## For GUI of sliders:
```
ros2 run rqt_joint_trajectory_controller rqt_joint_trajectory_controller
```

## For checking joint positions:
```
ros2 topic echo /joint_states
```

## For checking end effector positions:
```
ros2 run tf2_ros tf2_echo <BASE_FRAME> <END_EFFECTOR_FRAME>
```

## For general use:
```
ros2 launch <MOVEIT_CONFIG_PKG> move_group.launch.py
ros2 launch <MOVEIT_CONFIG_PKG> moveit_rviz.launch.py
```
