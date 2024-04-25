# ROS1 Gazebo

- [ROS1 Gazebo](#ros1-gazebo)
  - [For opening:](#for-opening)
  - [For closing:](#for-closing)
  - [For resetting:](#for-resetting)

## For opening:
```
gazebo
```

## For closing:
```
sudo pkill -f gzserver
sudo pkill -f gzclient
```

## For resetting:
```
rosservice call /gazebo/reset_world "{}"
```