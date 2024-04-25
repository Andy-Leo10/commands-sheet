# Testing

- [Testing](#testing)
  - [GTest (c++)](#gtest-c)
    - [For ROS2:](#for-ros2)
  - [UnitTest (python)](#unittest-python)
    - [For ROS1:](#for-ros1)

## GTest (c++)

### For ROS2:
```
colcon test --packages-select <PKG_NAME> --event-handler=console_direct+
colcon test-result --test-result-base build/<PKG_NAME>
colcon test-result --verbose
```

## UnitTest (python)

### For ROS1:
```
rostest <PKG_NAME> <TEST_FILE> --reuse-master
```
