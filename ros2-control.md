# ROS2 Control

- [ROS2 Control](#ros2-control)
  - [For checking controllers:](#for-checking-controllers)
  - [For managing controllers:](#for-managing-controllers)
- [CONTROL FIELD](#control-field)
  - [Derivation](#derivation)
  - [Integration](#integration)

## For checking controllers:
```
ros2 control list_controller_types
ros2 control list_controllers # list active controllers
ros2 contro list_hardware_interfaces # list joint measurements
```

## For managing controllers:
```
ros2 control set_controller_state <CONTROLLER_NAME> <start/stop/configure>
ros2 control unload_controller <CONTROLLER_NAME>
ros2 control load_controller <CONTROLLER_NAME>

ros2 service list | grep controller_manager
ros2 run controller_manager spawner <CONTROLLER_NAME> --controller-type <CONTROLLER_TYPE>
```

# CONTROL FIELD

## Derivation
$$
\text{{derivative}} = \frac{{\text{{error}} - \text{{previous\_error}}}}{{\text{{step\_time}}[s]}}
$$

## Integration
$$
\text{{integral}} = \text{{integral}} + \text{{error}} \times \text{{step\_time}}[s]
$$