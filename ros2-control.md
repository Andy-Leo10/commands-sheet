# ROS2 Control

- [ROS2 Control](#ros2-control)
  - [General](#general)
  - [For checking controllers:](#for-checking-controllers)
  - [For managing controllers:](#for-managing-controllers)
  - [Ignition gazebo systems](#ignition-gazebo-systems)
- [CONTROL FIELD](#control-field)
  - [Derivation](#derivation)
  - [Integration](#integration)

## General
- [Documentation](https://control.ros.org/iron/doc/ros2_control/hardware_interface/doc/joints_userdoc.html)
- [Examples](https://github.com/ros-controls/gz_ros2_control/blob/humble/doc/index.rst)
- Installation alongside Gazebo Classic
```bash
sudo apt-get install ros-humble-ros2-control
sudo apt-get install ros-humble-ros2-controllers
sudo apt-get install ros-humble-gazebo-ros2-control
```
- Installation alongside Ignition
```bash
sudo apt-get install ros-humble-ros2-control
sudo apt-get install ros-humble-ros2-controllers
sudo apt-get install ros-humble-ign-ros2-control
```
- Installation alongside Gazebo Sim
```bash
sudo apt-get install ros-jazzy-ros2-control
sudo apt-get install ros-jazzy-ros2-controllers
sudo apt-get install ros-jazzy-gz-ros2-control
```

## For checking controllers:
```bash
ros2 control list_controller_types
ros2 control list_controllers # list active controllers
ros2 control list_hardware_interfaces # list joint measurements
```

## For managing controllers:
```bash
ros2 control set_controller_state <CONTROLLER_NAME> <start/stop/configure>
ros2 control unload_controller <CONTROLLER_NAME>
ros2 control load_controller <CONTROLLER_NAME>

ros2 service list | grep controller_manager
ros2 run controller_manager spawner <CONTROLLER_NAME> --controller-type <CONTROLLER_TYPE>
```

## Ignition gazebo systems
- [Systems](https://gazebosim.org/api/gazebo/6/namespaceignition_1_1gazebo_1_1systems.html)

# CONTROL FIELD

## Derivation
$$
\text{derivative} = \frac{\text{error} - {\text{previous}}_\text{error}} {\text{step}\text{time}[s]}
$$

## Integration
$$
\text{integral} = \text{integral} + \text{error} \times {\text{step}}_{\text{time}}[s]
$$
