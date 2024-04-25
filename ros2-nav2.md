# ROS2 Nav2

- [ROS2 Nav2](#ros2-nav2)
  - [MAPPING](#mapping)
  - [LOCALIZATION](#localization)
  - [PLANNING](#planning)
  - [OBSTACLE AVOIDANCE](#obstacle-avoidance)
- [API commander](#api-commander)
- [COSTMAP FILTERS](#costmap-filters)
  - [Keep Out Zone](#keep-out-zone)
  - [Speed Limit](#speed-limit)

## MAPPING

For start mapping:
```
ros2 cartographer_ros cartographer_node
ros2 cartographer_ros occupancy_grid_node
```

For saving map:
```
ros2 run nav2_map_server map_saver_cli -f map
```

For providing map:
```
ros2 run nav2_map_server map_server
ros2 run nav2_lifecycle_manager lifecycle_manager
```

## LOCALIZATION
*(Particle Cloud | Pose with covariance)*

For start localization:
```
ros2 run nav2_map_server map_server
ros2 run nav2_amcl amcl
ros2 run nav2_lifecycle_manager lifecycle_manager
```

Others:
```
ros2 service call /reinitialize_global_localization std_srvs/srv/Empty
```

## PLANNING
*(Path)*

For start planning:
```
ros2 run nav2_planner planner_server
ros2 run nav2_controller controller_server
ros2 run nav2_bt_navigator bt_navigator
ros2 run nav2_recoveries recoveries_server
ros2 run nav2_lifecycle_manager lifecycle_manager
```

Main content in .yaml files:
```
- planner -> astar
- controller -> velocities, goal, tolerances
- behavior_tree -> behavior.xml
- recovery -> plugins
```
> Note: controller and recovery mus have the same FREQUENCY

Others:
```
ros2 action send goal /navigate_to_pose nav2_msgs/action/NavigateToPose "{pose: {header: {frame_id: 'map'}, pose: {position: {x: 0.0, y: 0.0, z: 0.0}, orientation: {x: 0.0, y: 0.0, z: 0.0, w: 1.0}}}"
ros2 topic pub /goal_pose geometry_msgs/PoseStamped "{header: {frame_id: 'map'}, pose: {position: {x: 0.0, y: 0.0, z: 0.0}, orientation: {x: 0.0, y: 0.0, z: 0.0, w: 1.0}}}"
```

## OBSTACLE AVOIDANCE
*(Global Map, Local Map)*

Main content in .yaml files:
```
- planner -> layers of map (global)
- controller -> layers costmap
```

# API commander

For installation:
```
sudo apt-get update
sudo apt-get install ros-<DISTRO>-nav2-simple-commander
```

Others:
```
- Navigate to pose = start -> end
- Navigate through poses = start -> goal -> ... -> goal -> end
- Waypoint follower = start -> goal -> ... -> goal -> end (use .yaml file)
```

# COSTMAP FILTERS

## Keep Out Zone

For applying mask:
```
ros2 run nav2_map_server filter_mask_server
ros2 run nav2_map_server costmap_filter_info_server
```

Costmaps applyed:
```
- global -> planner.yaml
- local -> controller.yaml
```

## Speed Limit

For applying speed limit:
```
ros2 run nav2_map_server filter_mask_server
ros2 run nav2_map_server costmap_filter_info_server
```

Costmaps applyed:
```
- global -> planner.yaml
```
