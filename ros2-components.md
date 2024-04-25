# ROS2 Components
*(in ROS1 are called NODE LETS)*

- [ROS2 Components](#ros2-components)
  - [For general use:](#for-general-use)
  - [some annotations:](#some-annotations)

## For general use:
ros2 component types
ros2 component list
ros2 run rclcpp_components component_container
ros2 component load /ComponentManager <PKG_NAME> <COMPONENT_NAME>
ros2 component unload /ComponentManager <COMPONENT_ID>

## some annotations:
- RUN TIME: not allows multithreading
- COMPILE TIME: allows multithreading