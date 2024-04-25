# ROS1 commands

- [ROS1 commands](#ros1-commands)
  - [For general use:](#for-general-use)
  - [For compiling:](#for-compiling)
  - [For compiling certain package:](#for-compiling-certain-package)
  - [For nodes:](#for-nodes)
  - [For messages:](#for-messages)
  - [For parameters:](#for-parameters)
  - [For packages:](#for-packages)

## For general use:
```
roscd <PKG_NAME>
catkin create pkg <PKG_NAME> --catkin-deps <DEPENDENCIES>
roscore
rostopic list
rostopic info <TOPIC_NAME>
rostopic hz <TOPIC_NAME>
```

## For compiling:
```
roscd;cd ..;catkin_make;source devel/setup.bash
```

## For compiling certain package:
```
roscd;cd ..;catkin_make --only-pkg-with-deps <PKG_NAME>;source devel/setup.bash
```

## For nodes:
```
rosrun <PKG_NAME> <NODE_NAME>
roslaunch <PKG_NAME> <LAUNCH_FILE>
roslaunch <PKG_NAME> <LAUNCH_FILE> <VARIABLE_NAME>:=<VALUE>
rosnode list
rosnode info <NODE_NAME>
rosnode kill <NODE_NAME>
```

## For messages:
```
rostopic echo <TOPIC_NAME>
rostopic pub <TOPIC_NAME> <MSG_TYPE> <MSG_DATA>
rosmsg list
rosmsg show <MSG_TYPE>

rosserve list
rosserve call <SERVICE_NAME> <SERVICE_DATA>
rosservice list
rosservice info <SERVICE_NAME>
rosservice call <SERVICE_NAME> <SERVICE_DATA>
rosservice show <SERVICE_MSG_TYPE>

rosrun actionlib axclient.py <ACTION_NAME>
```

## For parameters:
```
rosparam list
rosparam get <PARAM_NAME>
rosparam set <PARAM_NAME> <VALUE>
```

## For packages:
```
rospack list
rospack find <PKG_NAME>
rospack profile
```
