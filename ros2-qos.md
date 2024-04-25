# ROS2 QOS

- [ROS2 QOS](#ros2-qos)
- [For changing:](#for-changing)
- [QOS attributes:](#qos-attributes)

# For changing:
```
export RMW_IMPLEMENTATION=rmw_fastrtps_cpp
ros2 run demo_nodes_cpp talker --ros-args -p /use_sim_time:=true
ros2 run demo_nodes_cpp listener --ros-args -p /use_sim_time:=true
```

# QOS attributes:
- **reliability**: BEST_EFFORT if messages can be lost, RELIABLE if messages must be delivered
- **durability**: TRANSIENT_LOCAL if only the last message is needed, VOLATILE if messages can be lost
- **history**: KEEP_LAST if only the last messages are needed, KEEP_ALL if all messages are needed
- **depth**: number of messages to keep in history
- **deadline**: maximum time between sending and receiving a message
- **lifespan**: maximum time a message is valid
- **liveliness**: KEEP_LAST if only the last liveliness messages are needed, KEEP_ALL if all liveliness messages are needed
- **liveliness_lease_duration**: maximum time between sending liveliness messages